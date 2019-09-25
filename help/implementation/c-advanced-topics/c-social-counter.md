---
description: キュレーションされたソーシャルアイテムの数をカウントします。
seo-description: キュレーションされたソーシャルアイテムの数をカウントします。
seo-title: ソーシャルカウンター
solution: Experience Manager
title: ソーシャルカウンター
uuid: fa9aa1a8-6a04-4bc1-9bfe-e42c1250fd48
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# ソーシャルカウンター{#social-counter}

キュレーションされたソーシャルアイテムの数をカウントします。 使用可能なエンドポイントの完全なリストについては、Livefyre [API Referenceの節を参照してください](https://api.livefyre.com/docs) 。

SocialカウンターAPIは、特定のコレクション内のキュレーションルールに一致した数を一定期間の間隔で返します。

>[!NOTE]
>
>このAPIは、Twitterのハッシュタグに対してのみ使用できます。

ソーシャルカウンターAPI:

* リソース
* ルールタイプ
* 応答

## リソース {#section_p2s_2hc_11b}

```
GET https://{networkName}.bootstrap.fyre.co/api/v3.0/stats.collections.curate/{query}.json
```

* **** networkName: Livefyreが提供するネットワーク名。 例：の *実習*`labs.fyre.co`。
* **** クエリ：カウント情報を取得する（事前にエンコードされる）すべてのサイト、記事ID、ルールタイプのタプルのURLセーフbase64エンコードされたハッシュ。

   ```
   {site ID}:{article ID};{rule-type},  {article ID};{rule-type}|{site ID}:{article ID};{rule-type}
   ```

   >[!NOTE]
   >クエリは10サイト、記事ID、ルールタイプのタプルに制限されます。 （前の例では、3つのタプルが含まれています）。

* **fromは**`(optional)` 、グラフに表示する相対期間または絶対期間を指定します。fromは先頭を指定し、省略した場合はデフォルトで24時間前に設定されます。
* **untilは**`(optional)` 、グラフに表示する相対期間または絶対期間を指定します。untilは開始を指定し、省略した場合は現在の時間（現在）をデフォルトにします。

### 相対時間

| 略語 | 単位 |
|---|---|
| s | 秒 |
| min | 分 |
| h | 時間 |
| d | 日 |
| w | 週間 |
| mon | 30日（月） |
| y | 365日（年） |

例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-7d&until=-6d
```

## 絶対時間 {#section_xqr_jgc_11b}

形式：HH:MM_YYYYMMDD

| 略語 | 意味 |
|---|---|
| HH | 時間（24時間形式） |
| MM | 分 |
| YYYY | 4桁表記の年 |
| MM | 月 |
| DD | 日 |

例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=04:00_20130709 
```

## ルールタイプ {#section_v53_xqb_11b}

| 値 | タイプ |
|---|---|
| 2 | Twitter |

例：

サイトと記事IDおよびルールタイプの最後の1分間 `123456` のカウントを取得するに `some-article-id` は、次のように `2`指定します。 `123456:some-article-id;2:`

```
curl -XGET "https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-1min" 
```

応答の例:

```
{ 
    "status": "ok", 
    "code": 200, 
    "data": { 
        "123456": { 
            "some-article-id": { 
                "2": [ 
                    [ 
                        2, 
                        1374770460 
                    ], 
                    [ 
                        4, 
                        1374770470 
                    ], 
                    [ 
                        3, 
                        1374770480 
                    ], 
                    [ 
                        1, 
                        1374770490 
                    ], 
                    [ 
                        0, 
                        1374770500 
                    ], 
                    [ 
                        7, 
                        1374770510 
                    ] 
                ] 
            } 
        } 
    } 
}
```
