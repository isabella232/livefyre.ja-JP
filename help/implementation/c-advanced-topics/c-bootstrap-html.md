---
description: コミュニティコンテンツを検索エンジンクローラーで利用できるようにします。
seo-description: コミュニティコンテンツを検索エンジンクローラーで利用できるようにします。
seo-title: BootstrapHTML
solution: Experience Manager
title: BootstrapHTML
uuid: 137e4382-4e7b-4124-9d35-1d872a497bc7
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 1%

---


# BootstrapHTML

コミュニティコンテンツを検索エンジンクローラーで利用できるようにします。

使用可能なエンドポイントの完全なリストについては、Livefyre [APIリファレンス](https://api.livefyre.com/docs)の節を参照してください。

Livefyre Appsを使用するには、コレクションのコンテンツを表示するために、ページ上でJavaScriptを実行する必要があります。 ほとんどの検索エンジンクローラはJavaScriptを実行できないので、コミュニティが投稿するコンテンツを表示できません。 BootstrapHTML APIを使用して、このコンテンツの検索可能なフラグメントをページの最初のHTTP応答に追加し、コンテンツとキーワードを使用して検索エンジンの最適化を改善します。

>[!NOTE]
>
>このAPIは、コメントおよびライブブログコレクションタイプでのみ使用できます。

## 統合

LivefyreのBootstrapHTML APIは、ユーザーコンテンツのHTMLフラグメントを返します。このフラグメントはページのHTTP応答に含まれる場合があります。 この応答は、JavaScriptを実行せずに検索エンジンクローラーで読み取ることができます。 ページがユーザーのブラウザーにライブになると、HTMLフラグメントは完全なインタラクティブウィジェットに置き換えられ、ユーザーはコンテンツを投稿できます。

BootstrapHTML APIを実装するには：

1. 以下に説明するBootstrapのHTMLエンドポイントに、サーバーからサーバーへのAPIリクエストを行います。

   >[!NOTE]
   >
   >まだ存在しない会話（つまり、まだアプリを埋め込んだりコレクションを作成したりしていない会話）のためにBootstrapHTMLを取得しようとすると、200件が返されますが、コンテンツは次のようになります。`<!- HTTP 404 example.fyre.co/000000/MTEwMTo2NDEyOD1RS/bootstrap.html ->`

1. 戻り値に「404」を含むコンテンツが含まれない場合は、文字列に保存します。 この応答を後で使用するためにキャッシュして、すべてのページ読み込みでBootstrapHTML APIをリクエストするのを避けることができます。
1. コンテンツを表示するWebページにBootstrapHTML文字列を挿入します。
1. Webページをブラウザ（または検索エンジンクローラ）に提供します。

## リソース

```
GET https://{networkName}.bootstrap.fyre.co/bs3/{networkName}.fyre.co/{siteId}/{base64 encoded article ID}/bootstrap.html 
```

## パラメーター

* **** networkNameLivefyreが提供するネットワーク名。次に例を示します。*labs* in `labs.fyre.co`.
* **siteIdコレ** クションのサイトID。
* **b64**  articleIdbase64urlエンコーディングを使用するコレクションの記事ID。

## 例

```
https://labs.bootstrap.fyre.co/bs3/labs.fyre.com/4/NTg0/bootstrap.html 
```

## 応答

```
https://gist.github.com/ec5c2457322faf9cf515 
```
