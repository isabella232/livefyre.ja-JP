---
description: コミュニティコンテンツを検索エンジンクローラーで使用できるようにします。
seo-description: コミュニティコンテンツを検索エンジンクローラーで使用できるようにします。
seo-title: Bootstrap HTML
solution: Experience Manager
title: Bootstrap HTML
uuid: 137e4382-4e7b-4124-9d35-1d872a497bc7
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Bootstrap HTML

コミュニティコンテンツを検索エンジンクローラーで使用できるようにします。

使用可能なエンドポイントの完全なリストについては、Livefyre [API Referenceの節を参照してください](https://api.livefyre.com/docs) 。

Livefyreアプリでは、コレクションのコンテンツを表示するために、ページ上でJavaScriptを実行する必要があります。 ほとんどの検索エンジンクローラーはJavaScriptを実行できないので、コミュニティが投稿するコンテンツを表示できません。 Bootstrap HTML APIを使用して、このコンテンツの検索可能なフラグメントをページの最初のHTTP応答に追加し、コンテンツとキーワードを使用して検索エンジンの最適化を改善します。

>[!NOTE]
>
>このAPIは、CommentsタイプとLive Blog Collectionタイプでのみ使用できます。

## 統合

LivefyreのBootstrap HTML APIは、ユーザーコンテンツのHTMLフラグメントを返します。このフラグメントはページのHTTP応答に含まれる場合があります。 この応答は、JavaScriptを実行せずに検索エンジンクローラーで読み取ることができます。 ページがユーザーのブラウザーでライブになると、HTMLフラグメントは完全なインタラクティブウィジェットに置き換えられ、ユーザーはコンテンツを投稿できるようになります。

Bootstrap HTML APIを実装するには：

1. 以下に説明するBootstrap HTMLエンドポイントに対するサーバーからサーバーへのAPIリクエストを作成します。

   >[!NOTE]
   >
   >まだ存在しない会話（つまり、まだアプリを埋め込んだりコレクションを作成したりしない会話）のBootstrap HTMLを取得しようとすると、200件のメッセージが届きますが、次のようなコンテンツが含まれます。 `<!- HTTP 404 example.fyre.co/000000/MTEwMTo2NDEyOD1RS/bootstrap.html ->`

1. 返される内容に「404」が含まれていない場合は、文字列に保存します。 この応答を後で使用するためにキャッシュして、すべてのページ読み込みでBootstrap HTML APIをリクエストしないようにすることができます。
1. コンテンツを表示するWebページにBootstrap HTML文字列を挿入します。
1. Webページをブラウザー（または検索エンジンクローラー）に提供します。

## リソース

```
GET https://{networkName}.bootstrap.fyre.co/bs3/{networkName}.fyre.co/{siteId}/{base64 encoded article ID}/bootstrap.html 
```

## パラメーター

* **networkName** Livefyreが提供するネットワーク名。 例：の *実習*`labs.fyre.co`。
* **siteId** ：コレクションのサイトID。
* **b64articleId** base64urlエンコードを使用したコレクションの記事ID。

## 例

```
https://labs.bootstrap.fyre.co/bs3/labs.fyre.com/4/NTg0/bootstrap.html 
```

## 応答

```
https://gist.github.com/ec5c2457322faf9cf515 
```
