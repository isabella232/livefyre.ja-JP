---
description: キュレーションされたソーシャルアイテムの数をカウントします。
title: ソーシャルカウンター
exl-id: def7fba4-1c2e-4c7b-84f7-f9ede592d675
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 12%

---

# ソーシャルカウンタ{#social-counter}

キュレーションされたソーシャルアイテムの数をカウントします。 使用可能なエンドポイントの完全なリストについては、Livefyre [APIリファレンス](https://api.livefyre.com/docs)の節を参照してください。

SocialカウンターAPIは、特定のコレクション内の一致したキュレーションルールに対するカウントを一定期間の間隔で返します。

>[!NOTE]
>
>このAPIは、Twitterのハッシュタグに対してのみ利用できます。

ソーシャルカウンタAPI:

* リソース
* ルールタイプ
* 応答

## リソース {#section_p2s_2hc_11b}

```
GET https://{networkName}.bootstrap.fyre.co/api/v3.0/stats.collections.curate/{query}.json
```

* **networkName:Livefyre** が提供するネットワーク名。次に例を示します。*labs* in `labs.fyre.co`.
* **クエリ:** すべてのサイトのURLセーフベース64エンコードされたハッシュ。記事ID、ルールタイプのタプル。カウント情報を取得（事前にエンコード）

   ```
   {site ID}:{article ID};{rule-type},  {article ID};{rule-type}|{site ID}:{article ID};{rule-type}
   ```

   >[!NOTE]
   >クエリは、10個のサイト、記事ID、ルールタイプのタプルに制限されます。 （前の例では、3つのタプルが含まれています）。

* **** `(optional)` fromグラフに対する相対期間または絶対期間を指定します。fromは最初を指定し、省略した場合はデフォルトで24時間前に設定します。
* **グラフの相対期間または絶対期間を** `(optional)` untill：指定します。untilは開始を指定し、省略した場合は現在時間（現在）をデフォルトにします。

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

## 絶対時間{#section_xqr_jgc_11b}

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

## ルールタイプ{#section_v53_xqb_11b}

| 値 | タイプ |
|---|---|
| 2 | Twitter |

例：

サイト`123456`、記事ID `some-article-id`、ルールタイプ`2`の直近の1分間のカウントを取得するには、次のように指定します。`123456:some-article-id;2:`

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
