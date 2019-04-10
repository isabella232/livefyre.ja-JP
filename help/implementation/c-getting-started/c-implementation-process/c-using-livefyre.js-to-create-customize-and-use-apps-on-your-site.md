---
seo-title: アプリの埋め込み
solution: Experience Manager
title: アプリの埋め込み
uuid: e75cab0e-04ea-4b04-89ed- fea1183ecf63
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# アプリの埋め込み{#embed-an-app}

Livefyre. js埋め込みコード構造を使用して、LivefyreアプリをWebページに追加します。

このドキュメントは、技術的なオーディエンスを対象としています。アプリケーションに関する技術的でない情報について [](/help/using/c-about-apps/c-about-apps.md)説明します。

ここでは、サイトにLivefyreアプリを埋め込むために必要なコード構造について説明します。

1. Livefyreプレースホルダを使用して.htmlファイルを作成します。

   選択したテキストエディターで新しい.htmlファイルを作成します。アプリケーションを埋め込むプレースホルダLivefyre `<div>` 要素を作成します。

   ```
   <html> 
      <head> </head> 
      <body> 
         <div id='livefyre'> </div> 
      </body> 
   </html>
   ```

1. Livefyre. jsライブラリを含めます。

   その後、Livefyre JSライブラリをインクルードします。要素内の `<script>` 要素に次の参照を配置 `<head>` します。次に、ブラウザーでページを開き、ブラウザーのWebインスペクタを使用してLivefyreが読み込まれていることを確認します。

   ```
   <head> 
      <script src='@{livefyre_js}'></script> 
   </head> 
   ```

1. Livefyreアプリを作成します。

   使用するLivefyreパッケージを渡すことで、コアアプリとSDKアプリケーションの両方を構築するために使用 `Livefyre.require` します。

   1. コアアプリの作成を参照してください。

      コアアプリ（コメント、ライブブログまたはチャット）を作成するには、次の構造を使用します。

      ```
      Livefyre.require(['fyre.conv#@{fyre_conv_version_prod}'], function(Conv) { 
           new Conv(networkConfig, [convConfig], function(widget) {});  
      });  
      ```

   1. SDKアプリを作成します。

      メディアウォールやフィードなどのSDKアプリを作成するには、次の構造を使用します。

      ```
             Livefyre.require(['app#{version_number}'], 
         function (App, SDK) { 
            var app = new App({ 
            el: document.getElementById('app'), 
         }); 
         var collection = new SDK.Collection({ 
            network: "`labs.fyre.co`", 
            environment: "livefyre.com", 
            siteId: "315833", 
            articleId: 'livefyre-tweets' 
         }); 
         collection.pipe(feed); 
      }); 
      ```

      詳しく [は、特定のアプリ](/help/using/c-about-apps/c-about-apps.md)を参照してください。予期しない統合を避けるために、最新バージョンのパッケージ（Livefyre. require経由で [](https://cdn.livefyre.com/packages.html)見つけることができる）に固定することをお勧めします。

次へ:ユーザーがコメントを投稿できるようにするには、サイトに認証を追加します。
