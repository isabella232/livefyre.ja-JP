---
seo-title: アプリの埋め込み
solution: Experience Manager
title: アプリの埋め込み
uuid: e75caf0e-04ea-4b04-89ed-fea1183ecf63
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# アプリの埋め込み{#embed-an-app}

Livefyre.js埋め込みコード構造を使用して、LivefyreアプリをWebページに追加します。

このドキュメントは、技術者を対象としています。 アプリ [に関する技術的な情報以外](/help/using/c-about-apps/c-about-apps.md)。

ここでは、Livefyreアプリをサイトに埋め込むためにページテンプレートに含める必要があるコード構造について説明します。

1. Livefyreプレースホルダーを使用して.htmlファイルを作成します。

   任意のテキストエディターで新しい.htmlファイルを作成します。 アプリが埋め込まれるプ `<div>` レースホルダーLivefyre要素を作成します。

   ```
   <html> 
      <head> </head> 
      <body> 
         <div id='livefyre'> </div> 
      </body> 
   </html>
   ```

1. Livefyre.jsライブラリを含めます。

   次に、Livefyre JSライブラリを含めます。 要素内の要素に次の参照 `<script>` を配置し `<head>` ます。 次に、ブラウザーでページを開き、ブラウザーのWebインスペクターを使用して、Livefyreが読み込まれていることを確認します。

   ```
   <head> 
      <script src='@{livefyre_js}'></script> 
   </head> 
   ```

1. Livefyreアプリの作成を参照してください。

   使用す `Livefyre.require` る予定のLivefyreパッケージを渡して、コアアプリとSDKアプリの両方を作成するために使用します。

   1. コアアプリの作成を参照してください。

      コアアプリ（コメント、ライブブログまたはチャット）を作成するには、次の構造を使用します。

      ```
      Livefyre.require(['fyre.conv#@{fyre_conv_version_prod}'], function(Conv) { 
           new Conv(networkConfig, [convConfig], function(widget) {});  
      });  
      ```

   1. SDKアプリを作成します。

      Media wallやFeedなどのSDKアプリを作成するには、次の構造を使用します。

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

      特定のア [プリに関する詳細を参照してください](/help/using/c-about-apps/c-about-apps.md)。 予期しない統合の破損を防ぐため、パッケージの最新のメジャーバージョン( [Livefyre.require](https://cdn.livefyre.com/packages.html))にピン留めすることをお勧めします。

次：ユーザーがコメントを投稿できるように、サイトに認証を追加します。
