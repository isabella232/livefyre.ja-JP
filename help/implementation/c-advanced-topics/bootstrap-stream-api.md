---
description: Livefyre AppsでBootstrapとストリームAPIを使用します。
title: アカウントの詳細の表示
exl-id: b8458954-3727-4c4d-93dd-d21a4328e069
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Livefyre AppsでBootstrapとストリームAPIを使用する{#bootstrap-stream-api}

## BootstrapAPI {#bootstrap-api}

### 最新の50個より古いコンテンツを取得する方法を教えてください。{#howcontentolder}

Bootstrapは、Livefyreアプリのすべてのコンテンツです。 キャッシュされたデータで、通常は12 ～ 20分経過しています。 50個のチャンクで配信され、ページ番号が付けられ、50個を超える古いコンテンツを取得できます。

[API リファレンス](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:bootstrap:operations:bs3:v3.1:network:site:article:init:method=get)

[リクエストの例](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

上の例のリクエストでは、`init`ページが読み込まれます。このページにはコレクション設定と最新コンテンツの最初のセットは50個までです。 古いコンテンツをポーリングするには、`N`をページ番号として、以降のブートストラップページを読み込む必要があります。

リクエスト: `https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/N.json`

例えば、1つのサンプルアプリに120個のコンテンツが含まれているとします。 コンテンツ「1」はコンテンツの最も古い部分で、コンテンツ「70」はコンテンツの最も新しい部分です。

* `Init` は、最大120 ～ 70個のコンテンツを降順で読み込みます。 [https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

* `O.json` は、1 ～ 50個のコンテンツを昇順で読み込みます。 [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json)

* `1.json` は、～51 ～ 100個のコンテンツを昇順で読み込みます。 [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json)

* `2.json` は～101～120個のコンテンツを昇順で読み込みます。[https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json)

[ここをクリックすると、Bootstrap調査のフローチャートが表示されます。](https://marketing-resource-help.s3.amazonaws.com/resources/help/en_US/livefyre/bootstrap-poll-flowchart.pdf)

## ストリームAPI {#stream-api}

ストリームAPIとは
ストリームは長い調査で、設計上、約30秒間開いたままにすることを意図しています。 ロングポーリング手法の説明は、次を参照してください。[https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet)

このロングポーリングエンドポイントは、新しいコンテンツ（ユーザーがコメントを投稿するなど）、コンテンツステータスの変更（ユーザーがコメントを削除した、「いいね！」）およびコンテンツへのモデレートの変更（モデレーターがコンテンツの承認）をLivefyreアプリにストリーミングします。

ストリームAPIへのリクエストは、30秒（ロングポーリング）までで、新しいコンテンツがストリームインしない場合に30秒後に予想されるタイムアウトが発生します。

APIリファレンス：[https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get)

リクエストの例：

`{"timeout":true,"parked":true,"h":"ct245.dsr.livefyre.com"}`

注意：Stream API応答の`maxEventId`は、この応答の更新の最も高いイベントIDです。 次のStream APIリクエストのURLを作成する際は、この値を`lastEventId`パスパラメーターとして使用して、この応答のすべての更新の後に発生する更新を取得します。

以下の例は、コメントアプリに基づいています。

「最初のコメント」というコメントが最初に投稿されました。 「2回目のコメント」は、の後に投稿されました。

最初のコメントストリームAPIの応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答内の`maxEventId`は「1520289700953369」です。これは、この応答内のすべての更新の後に発生する更新（2番目のコメント）を取得するために`lastEventId`として使用されます。

2番目のコメントストリームAPIの応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答の`maxEventID` &quot;1520289700953369&quot;を`lastEventID`として使用し、次回の更新でストリームAPI応答を作成する必要があります。
