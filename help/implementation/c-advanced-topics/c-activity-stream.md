---
description: Livefyreシステムを流れるユーザー生成コンテンツを監視し、保存する方法を説明します。
seo-description: Livefyreシステムを流れるユーザー生成コンテンツを監視し、保存する方法を説明します。
seo-title: アクティビティストリーム
solution: Experience Manager
title: アクティビティストリーム
uuid: f40deec1-58ab-41c9-aac4-d2d8c9192bb9
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# アクティビティストリーム {#activity-stream}

Livefyreシステムを流れるユーザー生成コンテンツを監視し、保存する方法を説明します。

Activity Stream APIを使用して、ネットワークまたはサイト上のLivefyreシステムを流れるユーザー生成データを使用します。 例：このAPIのデータを使用して、評価に基づいて検索インデックスを更新したり、ユーザーのアクティビティに基づいてサードパーティのシステムでユーザーのバッジを管理したりします。

アクティビティストリームAPI:

使用可能なエンドポイントの完全なリストについては、Livefyre APIリファレンスの節を参照してください。

## リソース {#section_aql_n4l_b1b}

エンドポイントは2つあり、1つはステージング環境用、もう1つは実稼働用です。

### ステージング

```
GET https://bootstrap.t402.livefyre.com/api/v3.1/activity/ 
```

### 実稼動

```
GET https://bootstrap.livefyre.com/api/v3.1/activity/ 
```

### パラメーター

* **** リソース： *string* ：アクティビティデータをリクエストする対象のオブジェクトのURN。

* **** since: *integer* ：最後に受け取ったイベントのIDを表す64ビットの整数です。 以前のデータがない場合は「0」を指定します。

## URN文字列 {#section_skl_q4l_b1b}

例：

* **** urn:livefyre:のア `example.fyre.co` クティビティストリー `example.fyre.co`ム。
* **** urn:livefyre:ネッ `example.fyre.co:site=54321` トワーク下のサイト54321のアクティビティストリ `example.fyre.co` ーム。

## トークンポリシー {#section_nwh_c5j_11b}

アクティビティストリームAPIは、認証にOAuth Bearer Tokenを使用します。 ベアラトークンはOAuth 2.0仕様の一部で、正式にここで説明し [ます](https://tools.ietf.org/html/rfc6750#section-1.2)。

トークンには、次のようなものが含まれます。

* トークンの作成者。
* 誰かに形跡が与えられた。
* 有効でなくなった時刻。
* 我々が取り組んでいるもの。
* 付与された権限のリストです。

### 手順

OAuth Bearer Tokenを作成する手順は次のとおりです。

* 発行者、オーディエンス、件名、有効期限、スコープを含むマップ/ディクショナリを作成します。
* JWTトークンをエンコードするには、JWTライブラリをシークレットと共に使用します。
* 「認証：「Bearer」をHTTPリクエストに送信します。

以下のコードサンプルは、Pythonでの上記の手順を示しています。

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

bearerトークンキーは次のように定義されます。

* **is** (Issuer)ト ** ークンを生成する権限を持つエンティティ。 これは、Livefyre、サイト、またはネットワークの場合があります。 （学校に遅刻するメモは、親の手紙です。）
* **aud** (オーデ *ィエンス)* ：このトークンが生成された人。 トークンを自分で作成する場合は、そのトークンはサイトまたはネットワークです。
* **sub** (Subject) ** 権限を付与する対象。 例えば、コレクションで操作している場合、件名はコレクションの識別子である必要があります。 （学校の例のメモでは、あなたです。）
* **exp** （有効期限） ** ：トークンが無効になった時点。
* **scope** (Scope) ** ：サブジェクトに対して付与された権限のリストです。 「学校に遅れる」が例です。 APIの名前も例です。

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

前回のリクエスト以降の新しいデータを含む応答：

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

* APIの呼び出しが成功すると、HTTP 200ステータスコードが生成されます。 その他のステータスコードはすべてエラーと見なされます。
* null以外の場合は、次のリクエストのパラメ `data.meta.cursor.next` ーターと `since` しての値を使用します。
* からの値がnullの場 `data.meta.cursor.next` 合、使用する新しいデータがないことを意味します。 新しいデータが届いたかどうかを確認するには、後で同じ `since` 値を使用して再リクエストする必要があります。
* 実際には、値がnull以外の場合は、すぐに追加のデータを `data.meta.cursor.next` リクエストする必要があります。
* このAPIを通じて、実稼働環境で約2時間分の最近のデータを利用できます。
* 不足するデータを避けるために、cronjobでこのエンドポイントを頻繁にポーリングするプロセスを設定する必要があります。 5分の間隔は、ほとんどの実装で十分に適しています。
