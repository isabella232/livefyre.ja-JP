---
description: キュレーションされたソーシャルアイテムの数をカウントします。
seo-description: キュレーションされたソーシャルアイテムの数をカウントします。
seo-title: ソーシャルカウンター
solution: Experience Manager
title: ソーシャルカウンター
uuid: fa9aa1a8-6a04-4bc1-9bfe- e42c1250fd48
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# ソーシャルカウンター{#social-counter}

キュレーションされたソーシャルアイテムの数をカウントします。使用可能なエンドポイントの一覧については、&quot;Livefyre [APIリファレンス](https://api.livefyre.com/docs) 」の節を参照してください。

SocialカウンターAPIは、特定のコレクション内の一致するキュレーションルールのカウントを、一定期間の間隔で返します。

>[!NOTE]
>
>このAPIは、Twitterのハッシュタグでのみ使用できます。

SocialカウンターAPI:

* リソース
* ルールタイプ
* 応答

## リソース {#section_p2s_2hc_11b}

```
GET https://{networkName}.bootstrap.fyre.co/api/v3.0/stats.collections.curate/{query}.json
```

* **NetworkName:** Livefyreが提供するネットワーク名。次に例を示します。 *ラボ*`labs.fyre.co`の
* **query:** すべてのサイト、記事ID、ルールタイプの組のURLセーフベースのbase64エンコードハッシュ（事前エンコード済み）

   ```
   {site ID}:{article ID};{rule-type},  {article ID};{rule-type}|{site ID}:{article ID};{rule-type}
   ```

   >[!NOTE]
   >クエリは10サイト、記事ID、ルールタイプ組に制限されています。（前述の例には3組が含まれています）。

* **from**`(optional)` は、グラフの相対的または絶対的な期間を指定します。から開始する場合は、開始日を指定し、省略した場合は24時間前に指定します。
* **を指定**`(optional)` します。を指定するまで、開始を指定し、省略した場合は現在の時刻（現在は）を指定します。

### 相対時間

| 省略形 | 単位 |
|---|---|
| s | 秒 |
| min | Minutes |
| h | Hours |
| d | Days |
| w | 週 |
| mon | 30日（月） |
| y | 365Days（Year） |

例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-7d&until=-6d
```

## 絶対時間 {#section_xqr_jgc_11b}

FORMAT:HH:MM_ YYYYMMDD

| 省略形 | つまり、 |
|---|---|
| HH | Hours（24h時計形式） |
| MM | Minutes |
| YYYY | 4桁の年 |
| MM | 月 |
| DD | 日 |

例：

```
https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=04:00_20130709 
```

## ルールタイプ {#section_v53_xqb_11b}

| Value | タイプ |
|---|---|
| 2 | Twitter |

例：

サイト `123456` IDと記事ID `some-article-id` とルールタイプ `2`の最後の分を取得するには、次のようにします。 `123456:some-article-id;2:`

```
curl -XGET "https://labs-t402.bootstrap.fyre.co/api/v3.0/stats.collections.curate/MTIzNDU2OnNvbWUtYXJ0aWNsZS1pZDsy.json&from=-1min" 
```

応答例:

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
