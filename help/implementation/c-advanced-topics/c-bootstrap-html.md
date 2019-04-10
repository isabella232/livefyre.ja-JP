---
description: コミュニティコンテンツを検索エンジンのクローラーで利用できるようにします。
seo-description: コミュニティコンテンツを検索エンジンのクローラーで利用できるようにします。
seo-title: ブートストラップHTML
solution: Experience Manager
title: ブートストラップHTML
uuid: 137e4382-4e7b-4124-9d35-1d872a497bc7
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# ブートストラップHTML

コミュニティコンテンツを検索エンジンのクローラーで利用できるようにします。

使用可能なエンドポイントの一覧については、"Livefyre [APIリファレンス](https://api.livefyre.com/docs) 」の節を参照してください。

Livefyreアプリでは、ページ上でJavaScriptを実行してコレクションのコンテンツを表示する必要があります。ほとんどの検索エンジンクローラーはJavaScriptを実行できないので、コミュニティの投稿でコンテンツを表示できません。Bootstrap HTML APIを使用して、このコンテンツの検索可能なフラグメントをページのHTTP応答に追加し、コンテンツとキーワードを使用して検索エンジン最適化を改善します。

>[!NOTE]
>
>このAPIは、コメントおよびライブブログコレクションタイプでのみ使用できます。

## 統合

LivefyreのブートストラップHTML APIは、ページのHTTP応答に含まれる可能性のある、ユーザーコンテンツのHTMLフラグメントを返します。この応答は、JavaScriptを実行せずに検索エンジンクローラーによって読み取り可能になります。ページがユーザーのブラウザーに表示されると、HTMLフラグメントは完全なインタラクティブウィジェットに置き換えられ、ユーザーはコンテンツを投稿できるようになります。

ブートストラップHTML APIを実装するには:

1. 後述のBootstrap HTMLエンドポイントにサーバーをサーバーAPIリクエストに追加します。

   >[!NOTE]
   >
   >まだ存在しない会話用にBootstrap HTMLを取得しようとする（つまり、アプリを埋め込むかコレクションを作成する必要がある場合）、200を受け取ると、次のようなコンテンツが表示されます。 `<!- HTTP 404 example.fyre.co/000000/MTEwMTo2NDEyOD1RS/bootstrap.html ->`

1. 返されるコンテンツに"404"という内容のコンテンツが含まれていない場合は、文字列に保存します。この応答をキャッシュして、すべてのページ広告でブートストラップHTML APIをリクエストしないようにすることができます。
1. コンテンツを表示するWebページにブートストラップHTML文字列を挿入します。
1. ブラウザー（または検索エンジンクローラー）にWebページを提供します。

## リソース

```
GET https://{networkName}.bootstrap.fyre.co/bs3/{networkName}.fyre.co/{siteId}/{base64 encoded article ID}/bootstrap.html 
```

## パラメーター

* **NetworkName** Livefyreによって提供されるネットワーク名。次に例を示します。 *ラボ*`labs.fyre.co`の
* **siteID** コレクションのサイトID。
* **b64articleID** base64URLエンコーディングを使用するコレクションの記事ID。

## 例

```
https://labs.bootstrap.fyre.co/bs3/labs.fyre.com/4/NTg0/bootstrap.html 
```

## 応答

```
https://gist.github.com/ec5c2457322faf9cf515 
```
