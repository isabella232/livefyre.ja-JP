---
description: LivefyreアプリでBootstrapとStream APIを使用します。
seo-description: LivefyreアプリでBootstrapとStream APIを使用します。
seo-title: LivefyreアプリでのBootstrapおよびStream APIの使用
solution: Experience Manager
title: アカウントの詳細の表示
uuid: bace558f-ade8-49d6-abda-9ee754ce4ac0
translation-type: tm+mt
source-git-commit: d615705ccf5e4511cc735ce91d95c3e15d0c0160

---


# LivefyreアプリでのBootstrapおよびStream APIの使用 {#bootstrap-stream-api}

## Bootstrap API {#bootstrap-api}

### 最新の50個より古いコンテンツを取得する方法を教えてください。 {#howcontentolder}

Bootstrapは、Livefyreアプリのすべてのコンテンツです。 キャッシュされたデータで、通常は作成後12 ～ 20分です。 50個の単位で配信され、ページ分割されて、50個より古いコンテンツを取得できます。

[API リファレンス](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:bootstrap:operations:bs3:v3.1:network:site:article:init:method=get)

[リクエストの例](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

上の例のリクエストでは、コレクシ `init` ョン設定と最新コンテンツの最初のセットが50個まで含まれるページが読み込まれます。 古いコンテンツをポーリングするには、次のブートストラップページを読み込み、ページ番号 `N` を指定する必要があります。

リクエスト: `https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/N.json`

例えば、サンプルアプリには120個のコンテンツが含まれています。 コンテンツ「1」はコンテンツの最も古い部分で、コンテンツ「70」はコンテンツの最も新しい部分です。

* `Init` は、120 ～ 70個のコンテンツを降順で読み込みます。https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init [](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

* `O.json` は、1 ～ 50個のコンテンツを昇順で読み込みます。https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json [](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json)

* `1.json` は、コンテンツを昇順で51 ～ 100個読み込みます。https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json [](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json)

* `2.json` は～101～120個のコンテンツを昇順で読み込みます：[https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json)

[ここをクリックして、ブートストラップ投票フローチャートを参照してください。](https://marketing-resource-help.s3.amazonaws.com/resources/help/en_US/livefyre/bootstrap-poll-flowchart.pdf)

## ストリームAPI {#stream-api}

ストリームAPIとは
Streamは長いポーリングで、意図的に約30秒間開いた状態を保つことを目的としています。 ロングポーリング手法の説明は、次を参照してください。https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet [](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet)

このロングポーリングエンドポイントは、新しいコンテンツ（ユーザーがコメントを投稿するなど）、コンテンツステータスの変更（ユーザーがコメントを削除した、「いいね！」）およびコンテンツへのモデレートの変更（モデレーターがコンテンツの承認など）をLivefyreアプリにストリーミングします。

ストリームAPIへの要求は、30秒（ロングポーリング）で、新しいコンテンツストリームが入っていない場合に30秒後に予期されるタイムアウトが発生する必要があります。

APIリファレンス：https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get [](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get)

リクエストの例：

`{"timeout":true,"parked":true,"h":"ct245.dsr.livefyre.com"}`

注意：ストリ `maxEventId` ームAPI応答内のは、この応答内の更新の最も高いイベントIDです。 次のStream APIリクエストのURL `lastEventId` を作成する際にこの値をpathパラメーターとして使用し、この応答内のすべての更新の後に発生する更新を取得します。

次の例は、コメントアプリに基づいています。

コメント「最初のコメント」が最初に投稿されました。 「2回目のコメント」は後に投稿されました。

最初のコメントストリームAPI応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答 `maxEventId``lastEventId` 内の値は「1520289700953369」で、この応答内のすべての更新の後に発生する更新（2番目のコメント）を取得するためにエンドポイントをポーリングするために使用されます。

2番目のコメントストリームAPI応答：

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答の「 `maxEventID` 1520289700953369」も、次回の更新でストリームAPI応答を構築するための「 `lastEventID` 152028970095369」として使用する必要があります。