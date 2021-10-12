---
description: Livefyre アプリでBootstrapおよびストリーム API を使用する。
title: アカウントの詳細の表示
exl-id: b8458954-3727-4c4d-93dd-d21a4328e069
source-git-commit: 3091db9d7b9611e26ad65c1432856c9465694e92
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Livefyre アプリでのBootstrapおよびストリーム API の使用 {#bootstrap-stream-api}

## BootstrapAPI {#bootstrap-api}

### 最新の 50 個より古いコンテンツを取得するにはどうすればよいですか？ {#howcontentolder}

Bootstrapは、Livefyre アプリのすべてのコンテンツです。 これはキャッシュされたデータで、通常は 12 ～ 20 分後です。 50 個のチャンクで配信され、ページ付けされるので、50 個を超える古いコンテンツを取得できます。

[API リファレンス](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:bootstrap:operations:bs3:v3.1:network:site:article:init:method=get)

[リクエストの例](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

上記の例のリクエストでは、コレクション設定と最新のコンテンツの初期セットが 50 個まで含まれる `init` ページが読み込まれます。 古いコンテンツをポーリングするには、`N` をページ番号として使用して、以降のブートストラップページを読み込む必要があります。

リクエスト: `https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/N.json`

例えば、サンプルアプリに 120 個のコンテンツが含まれているとします。 コンテンツ「1」はコンテンツの最も古い部分で、コンテンツ「70」はコンテンツの最新の部分です。

* `Init` は、120 ～ 70 個のコンテンツを降順で読み込みます。 [https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

* `O.json` は、昇順で 1 ～ 50 個のコンテンツを読み込みます。  `https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json`
* `1.json` は、昇順で 51～100 個のコンテンツを読み込みます。  `https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json`
* `2.json` は、101 ～ 120 個のコンテンツを昇順で読み込みます。`https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json`

[ここをクリックして、投票フローチャートBootstrapを表示します。](https://marketing-resource-help.s3.amazonaws.com/resources/help/en_US/livefyre/bootstrap-poll-flowchart.pdf)

## ストリーム API {#stream-api}

ストリーム API とは
ストリームは長いポーリングで、設計によって約 30 秒間開いたままにすることを意図しています。 ロングポーリング手法の説明は、次の場所にあります。[https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet)

この長いポーリングエンドポイントは、新しいコンテンツ（ユーザーがコメントを投稿するなど）、コンテンツステータスの変更（ユーザーがコメントを削除した、「いいね！」）、コンテンツへのモデレートの変更（モデレーターがコンテンツの一部を承認するなど）を Livefyre App にストリーミングします。

ストリーム API へのリクエストは、約 30 秒（長いポーリング）で、新しいコンテンツがストリームインしない場合、30 秒後に予期されたタイムアウトを返す必要があります。

API リファレンス：[https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get)

リクエストの例：

`{"timeout":true,"parked":true,"h":"ct245.dsr.livefyre.com"}`

注意：ストリーム API 応答の `maxEventId` は、この応答での更新のイベント ID の最も高い値です。 次の Stream API リクエストの URL を作成する際に、この値を `lastEventId` path パラメーターとして使用し、この応答のすべての更新の後に更新が発生するようにします。

次の例は、コメントアプリに基づいています。

最初にコメント「最初のコメント」が投稿されました。 その後、「2 番目のコメント」が投稿されました。

最初のコメントストリーム API 応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答内の `maxEventId` は「1520289700953369」です。これは、この応答内のすべての更新の後に発生する更新（2 番目のコメント）を取得するためにエンドポイントをポーリングする `lastEventId` として使用されます。

2 番目のコメントストリーム API 応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答内の `maxEventID` &quot;1520289700953369&quot;を `lastEventID` として使用し、次回の更新で Stream API 応答を作成する必要があります。
