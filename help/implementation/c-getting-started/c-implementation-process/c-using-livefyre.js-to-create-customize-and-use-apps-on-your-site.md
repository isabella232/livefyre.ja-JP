---
title: アプリを埋め込む
description: アプリを埋め込む
exl-id: 12f75093-1b4d-4cf1-8593-dbd17ff33872
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# アプリを埋め込む{#embed-an-app}

追加Livefyre.jsの埋め込みコード構造を使用して、LivefyreアプリをWebページに公開します。

このドキュメントは、技術オーディエンスを対象としています。 [Apps](/help/using/c-about-apps/c-about-apps.md)に関する技術的でない情報の場合。

この節では、Livefyre Appsをサイトに埋め込むためにページテンプレートに含める必要があるコード構造について説明します。

1. Livefyreプレースホルダーを使用して.htmlファイルを作成します。

   任意のテキストエディターで新しい.htmlファイルを作成します。 アプリを埋め込むプレースホルダーLivefyre `<div>`要素を作成します。

   ```
   <html> 
      <head> </head> 
      <body> 
         <div id='livefyre'> </div> 
      </body> 
   </html>
   ```

1. Livefyre.jsライブラリを含めます。

   次に、Livefyre JSライブラリを含めます。 `<head>`要素の`<script>`要素に次の参照を配置します。 次に、ブラウザーでページを開き、ブラウザーのWebインスペクターを使用して、Livefyreが読み込まれていることを確認します。

   ```
   <head> 
      <script src='@{livefyre_js}'></script> 
   </head> 
   ```

1. Livefyreアプリを作成します。

   `Livefyre.require`を使用して、使用するLivefyreパッケージを渡して、コアアプリとSDKアプリの両方を作成します。

   1. コアアプリの作成を参照してください。

      コアアプリ（コメント、ライブブログ、またはチャット）を作成するには、次の構造を使用します。

      ```
      Livefyre.require(['fyre.conv#@{fyre_conv_version_prod}'], function(Conv) { 
           new Conv(networkConfig, [convConfig], function(widget) {});  
      });  
      ```

   1. SDKアプリを作成します。

      Media WallやFeedなどのSDKアプリを作成するには、次の構造を使用します。

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

      [特定のアプリに関する詳細](/help/using/c-about-apps/c-about-apps.md)を参照してください。 予期しない統合の破損を防ぐため、パッケージの最新のメジャーバージョン（[Livefyre.require](https://cdn.livefyre.com/packages.html)を通じて入手可能）にピン留めすることをお勧めします。

次：ユーザーが追加コメントを投稿できるようにするための認証。
