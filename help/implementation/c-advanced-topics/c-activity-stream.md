---
description: ユーザーが生成したコンテンツをLivefyreシステムを介してストリーミングする方法を説明します。
seo-description: ユーザーが生成したコンテンツをLivefyreシステムを介してストリーミングする方法を説明します。
seo-title: アクティビティストリーム
solution: Experience Manager
title: アクティビティストリーム
uuid: f40deec1-58ab-41c9- aac4- d2d8c9192bb9
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# アクティビティストリーム {#activity-stream}

ユーザーが生成したコンテンツをLivefyreシステムを介してストリーミングする方法を説明します。

Activity Stream APIを使用して、ネットワークまたはサイト上のLivefyreシステムを介して生成されるデータをユーザーが生成します。次に例を示します。このAPIからデータを使用して、評価に基づいて検索インデックスを更新したり、アクティビティに基づいてサードパーティシステムのユーザーバッジを管理したりします。

アクティビティストリームAPI:

使用可能なエンドポイントの一覧については、&quot;Livefyre APIリファレンス」の節を参照してください。

## リソース {#section_aql_n4l_b1b}

エンドポイントは2つあり、1つはステージング環境、もう1つは実稼動用です。

### ステージング

```
GET https://bootstrap.t402.livefyre.com/api/v3.1/activity/ 
```

### 実稼働環境

```
GET https://bootstrap.livefyre.com/api/v3.1/activity/ 
```

### パラメーター

* **リソース:***string* activityデータを要求するオブジェクトのURNです。

* **使用中:***integer* 最後に受け取ったイベントのIDを表す64ビット整数。前のデータがない場合は&quot;0&quot;を指定します。

## URN文字列 {#section_skl_q4l_b1b}

例：

* **urn:livehyre:**`example.fyre.co` アクティビティストリーム `example.fyre.co`。
* **urn:livehyre:**`example.fyre.co:site=54321``example.fyre.co` ネットワークの下のサイト54321のアクティビティストリーム。

## トークンポリシー {#section_nwh_c5j_11b}

アクティビティストリームAPIは、認証にOAuth Araberトークンを使用します。保留トークンはOAuth2.0仕様の一部であり、ここで正式に説明 [](https://tools.ietf.org/html/rfc6750#section-1.2)します。

トークンには、次のものが含まれています。

* トークンを作成したユーザー。
* トークンを付与されたユーザー。
* 有効になっていない時間。
* 操作しているもの。
* 許可された権限のリストです。

### 手順

OAuth Bearerトークンを作成する手順については、以下を参照してください。

* 発行者、オーディエンス、件名、有効期限およびスコープを含むマップ/ディクショナリを作成します。
* JWTトークンをエンコードするには、シークレットでJWTライブラリを使用します。
* 「認証」を追加します。&quot;Bearer&quot;をHTTPリクエストから取得します。

以下のコードサンプルでは、上記の手順をPythonで説明しています。

```
import time 
import jwt 
  
# network data goes here: 
network = "timeout-0.fyre.co" 
network_secret = "...replaceme..." 
  
# api URN 
api_urn = "urn:livefyre:api:core=GetActivityStream" 
  
# expires in 10 seconds 
expiration = int(time.time() + 10) 
  
network_urn = "urn:livefyre:" + network 
  
data = dict(iss=network_urn, aud=network_urn, sub=network_urn, scope=api_urn, exp=expiration) 
  
token = jwt.encode(data, key=network_secret)
```

スタザートークンキーは次のように定義されます。

* **iss***（発行者）* トークンを生成するエンティティを持つエンティティ。これはLivefyre、サイトまたはネットワークです。（学校に遅れている場合は、親になります）。
* **aaa***（オーディエンス）* このトークンが生成されたユーザー。トークンを作成する場合は、サイトまたはネットワークです。
* **sub***（Subject）* 許可される権限の件名。例えば、コレクションで操作している場合、サブジェクトはコレクションの識別子である必要があります。（学校の例のメモでは、
* **exp***（有効期限）* トークンが無効になった時点のポイント。
* **scope***（Scope）* これは、件名に付与された権限のリストです。「遅延」は一例です。APIの名前は別の例です。

## 例 {#section_dhl_ytj_11b}

```
curl -H "Authorization: Bearer <BEARER TOKEN>" https://bootstrap.livefyre.com/api/v3.1/activity/?resource=&since=
```

## 応答 {#section_gs2_stj_11b}

```
{ 
"code": 200,  
"data": { 
  "annotations": {},  
  "authors": {  
      /** "a set of every author who generated activity within this window" */ 
      "_up1770425@livefyre.com": { 
        "avatar": "https://gravatar.com/avatar/68c789597150d3e941769a5c0a0c4249/?s=50&d=https://avatars-qa.fyre.co/a/anon/50.jpg",  
        "displayName": "ross_pfahler",   
        "id": "_up1770425@livefyre.com",  
        "profileUrl": "https://www.qa-ext.livefyre.com/profile/1770425/",  
        "tags": [],  
        "type": 1 
      },  
  ... 
  },  
  "collections": {  
      /** "a set of every collection for which an activity was generated" */ 
      "2486601": { 
        "articleIdentifier": "75",  
        "id": "2486601",  
        "site": "290596",  
        "title": "Live Blog",  
        "url": "https://orangesaregreat.com/..." 
      }, 
  ... 
  },  
  /** "the maximum event ID for this window" */ 
  "maxEventId": 1383508243715211, 
  "states": {  
      /** "a set of messages (comments, reviews, etc) for which activity  
           was generated in this window, represents the compiled 
           'state' of the object including visible actions on that object 
           (up-votes, likes, and etc.)" */ 
      "3ad6480eb00c4895b29b7a972380f489@livefyre.com": { 
          "collectionId": "2486685",  
          "content": { 
              "annotations": { 
                "rating": [ 90 ], /** "this object is a Rating (4.5)" */ 
                "vote": [ 
                    { 
                      "author": "_up1792695@livefyre.com",  
                      "collectionId": "2486685",  
                      "value": 1 
                    } 
                ] 
              },  
              "attachments": [  
              /** "a list of oembeds; the body of this Rating included  
                  this Youtube video" */ 
                { 
                  "author_name": "mauricio890",  
                  "author_url": "https://www.youtube.com/user/mauricio890",  
                  "height": 480,  
                  "html": "<iframe width=\"854\" height=\"480\" src=\"https://www.youtube.com/embed/pmMAw5a7POU?autoplay=1&feature=oembed\" frameborder=\"0\" allowfullscreen></iframe>",  
                  "link": "https://www.youtube.com/watch?v=pmMAw5a7POU",  
                  "provider_name": "YouTube",  
                  "provider_url": "https://www.youtube.com/",  
                  "thumbnail_height": 360,  
                  "thumbnail_url": "https://i1.ytimg.com/vi/pmMAw5a7POU/hqdefault.jpg",  
                  "thumbnail_width": 480,  
                  "title": "Napoleon Dynamite dance scene",  
                  "type": "video",  
                  "url": "https://www.youtube.com/watch?v=pmMAw5a7POU",  
                  "version": "1.0",  
                  "width": 854 
                } 
              ],  
              // "who authored the content" 
              "authorId": "_up1793160@livefyre.com",  
              "bodyHtml": "<p><strong>Pros:</strong>Boom</p><p><strong>Cons:</strong>Goes</p><p><strong>Description:</strong>The dynamite:</p><p><a href=\"https://www.youtube.com/watch?v=pmMAw5a7POU\" target=\"_blank\" rel=\"nofollow\">https://www.youtube.com/watch?v=pmMAw5a7POU</a><br/></p>",  
              // "UNIX timestamp" 
              "createdAt": 1383257354,  
              "id": "3ad6480eb00c4895b29b7a972380f489@livefyre.com",  
              // "non-empty only if this were a reply" 
              "parentId": "", 
              // "UNIX timestamp"  
              "updatedAt": 1383257356  
          },  
          // "the event ID of this state." 
          "event": 1383369320554187,  
          "lastVis": 3,  
          "source": 0,  
          "type": 0,  
          // "Object visibility: 0 = deleted, 1 = everyone, 2 = bozo,  
          // 3 = owner + admins (e.g. premod)" 
          "vis": 1  
      },  
      "5943789": { 
          "collectionId": "2486688",  
          "content": { 
            "annotations": { 
                // "posted by a moderator" 
                "moderator": true  
            },  
            "authorId": "_up1792872@livefyre.com",  
            "bodyHtml": "<p>This is a regular comment from a moderator</p>",  
            "createdAt": 1383372338,  
            "id": "5943789",  
            "parentId": "",  
            "updatedAt": 1383372338 
          },  
          "event": 1383372338732492,  
          "lastVis": 0,  
          "source": 5,  
          "type": 0,  
          "vis": 1 
      },  
      "863c616a2c0c44239feed0914c282d7c@livefyre.com": { 
          "collectionId": "2486685",  
          "content": { 
              "id": "863c616a2c0c44239feed0914c282d7c@livefyre.com" 
          },  
          "event": 1383371303805767,  
          "lastVis": 1,  
          "source": 0,  
          "type": 0,  
          "vis": 0 // "0 = deleted; this object was removed" 
      },  
  ... 
},  
"meta": { 
  // "this describes position in the stream" 
  "cursor": {  
    // "maximum number of objects returned in a single call through this API" 
    "limit": 50,  
    // "the final position in the stream, and from where data should be requested" 
    "next": 1383508243715211, 
    // "the initial position (the 'since' parameter value in this request)" 
    "self": 0  
  } 
},  
"status": "ok" 
} 
```

前回のリクエスト以降の新しいデータの応答:

```
{ 
    "code": 200,  
    "data": { 
        "annotations": {},  
        "authors": {},  
        "collections": {},  
        "maxEventId": -1,  
        "states": {} 
    },  
    "meta": { 
        "cursor": { 
            "limit": 50, 
            /** "indicates there is no data beyond 1383508243715211" */  
            "next": null, 
            "self": 1383508243715211 
        } 
    },  
    "status": "ok" 
}
```

## メモ {#section_hj3_crj_11b}

* APIの呼び出しが成功すると、HTTP200のステータスコードが生成されます。その他のステータスコードはすべてエラーと見なされます。
* null以外の場合は、次のリクエストのパラメーターと `data.meta.cursor.next``since` して値を使用します。
* 値が `data.meta.cursor.next` nullの場合、使用する新しいデータはありません。新しいデータが届いているかどうかを確認するには、後で同じ `since` 値を使用して再要求する必要があります。
* 実際には、値が `data.meta.cursor.next` null以外の場合は、すぐにデータをリクエストする必要があります。
* 本番環境では、このAPIを通して約2時間の最新データを利用できます。
* データが見つからないようにするために、このエンドポイントをcronjobで頻繁にポーリングするようにプロセスを設定する必要があります。5分間隔は、ほとんどの実装に完全に適しています。
