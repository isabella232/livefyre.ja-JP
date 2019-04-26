---
description: LivefyreアプリでBootstrapおよびStream APIを使用します。
seo-description: LivefyreアプリでBootstrapおよびStream APIを使用します。
seo-title: LivefyreアプリケーションとのBootstrapおよびStream APIの使用
solution: Experience Manager
title: アカウントの詳細の表示
uuid: bace558f- ade8-49d6- abda-9ee754ce4ac0
translation-type: tm+mt
source-git-commit: d615705ccf5e4511cc735ce91d95c3e15d0c0160

---


# LivefyreアプリケーションとのBootstrapおよびStream APIの使用 {#bootstrap-stream-api}

## ブートストラップAPI {#bootstrap-api}

### 最新50個より古いコンテンツを取得するにはどうすればよいですか? {#howcontentolder}

BootstrapはLivefyreアプリケーションのすべてのコンテンツです。キャッシュされたデータです。通常は12~20分です。50個の部分で配信され、ページ分割されるので、50個より古いコンテンツを取得できます。

[APIリファレンス](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:bootstrap:operations:bs3:v3.1:network:site:article:init:method=get)

[リクエストの例](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

上記のリクエストの例では、コレクション設定と、最新の50個分の最新コンテンツのセットのみを含む `init` ページを読み込みます。古いコンテンツをポーリングするには、ページ番号と共 `N` に後続のブートストラップページを読み込む必要があります。

リクエスト: `https://{networkName}.bootstrap.fyre.co/bs3/v3.1/{network}/{siteId}/{b64articleId}/N.json`

例えば、サンプルアプリケーションに120のコンテンツがあるとします。コンテンツ"1"はコンテンツの最も古い部分で、コンテンツ"70"は最新のコンテンツです。

* `Init` を指定すると、コンテンツの120~70部分が降順で読み込まれます。 [https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init](https://data.livefyre.com/bs3/v3.1/dharam.fyre.co/384931/NTU1NQ==/init)

* `O.json` を指定すると、1~50のコンテンツが昇順で読み込まれます。 [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/0.json)

* `1.json` を指定すると、コンテンツの51~100部分が昇順で読み込まれます。 [https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/1.json)

* `2.json` を指定すると、コンテンツの101~120部分が昇順で読み込まれます。[https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json](https://data.livefyre.com/bs3/v3.1//dharam.fyre.co/384931/NTU1NQ==/2.json)

[ブートストラップポーリングフローチャートを表示するには、ここをクリックしてください。](https://marketing-resource-help.s3.amazonaws.com/resources/help/en_US/livefyre/bootstrap-poll-flowchart.pdf)

## ストリームAPI {#stream-api}

Stream APIとは何ですか。
ストリームは、約30秒間開いておくことを意図したロングポーリングです。ロングポーリング手法の説明については、こちらを参照してください。 [https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet)

この長期間のポーリングエンドポイントは、新しいコンテンツ（例えば、ユーザーがコメントを投稿した場合など）をストリーミングします。コンテンツのステータス変更（例えば、モデレーターは、コンテンツのコメント、「いいね!"など）やモデレートの変更をLivefyreアプリに変更します。

新しいコンテンツストリームがない場合、ストリームAPIへのリクエストは、30秒後に予測タイムアウトを持つ30秒（ロングポーリング）にする必要があります。

APIリファレンス: [https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get](https://api.livefyre.com/docs/apis/by-category/collections#operation=urn:livefyre:apis:stream1:operations:v3.1:collection:updates:method=get)

リクエストの例:

`{"timeout":true,"parked":true,"h":"ct245.dsr.livefyre.com"}`

注意事項:ストリームAPI応答 `maxEventId` は、この応答の更新の最も高いイベントIDです。この値を `lastEventId` パスパラメーターとして使用して、次のストリームAPIリクエストのURLを作成すると、この応答のすべての更新後に更新が発生します。

以下の例は、Comments Appに基づいています。

最初のコメント「最初のコメント」が最初に投稿されました。"2番目のコメント」が後に投稿された。

First Comment Stream API応答:

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答 `maxEventId` は"1520289700953369"です。これは、エンドポイントをポーリングして更新を取得する `lastEventId` ために使用されるものです（2番目のコメント）は、この応答のすべての更新後に発生します。

2番目のコメントストリームAPI応答:

`{"timeout":true,"parked":true,"h":"ct239.dsr.livefyre.com"}`

応答の `maxEventID` "1520289700953369"が、次のアップデートのストリームAPI応答を構築 `lastEventID` するために使用されます。