---
description: 参照トラフィックからページへのクリックを追跡します。
seo-description: 参照トラフィックからページへのクリックを追跡します。
seo-title: 照会トラッキング
solution: Experience Manager
title: 照会トラッキング
uuid: 5206cc16-9671-4b3d- a013- be1a3e8c029d
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 照会トラッキング{#referral-tracking}

参照トラフィックからページへのクリックを追跡します。

コメントがソーシャルネットワークに投稿または共有されたとき、およびLivefyre電子メールに含まれているpermalinkに対して、リファラー変数がURLに追加されます。この変数を使用して、Livefyreアプリからの照会トラフィックをSocialまたは所有するプロパティに追跡します。

Livefyreアプリを使用すると、照会トラフィックから得られたデータストリームを追跡し、サイトのトラフィックを分析できます。

## Livefyre照会トラフィックのトラッキング {#section_nsy_qp4_xz}

ソーシャルネットワークおよび電子メールからのLivefyre照会トラフィックは、ページのURL内のクエリ文字列パラメーターを調査し、ページにコードを導入して、分析プロバイダーから追跡することによって追跡できます。コメントがソーシャルネットワークに投稿または共有されたとき、およびLivefyre電子メールに含まれているpermalinkに対して、リファラーリンクが追加されます。

## 実装例 {#section_xvs_x44_xz}

トラフィックがStreamHubによる通知から送信された場合、電子メール、facebook、Twitter、LinkedInまたはpermalinkの値を持つHueRefSrcクエリ文字列パラメータがあります。HueFySrcパラメーター名はLivefyre配信チームによってネットワークレベルで設定できます。

Analyticsプラットフォームと統合するには、ページでロード時にHueFSrSrcを探し、そのトラフィックが存在する場合は記録する必要があります。

次に例を示します。

```
(function () { 
   var qs = document.location.search.substring(1), 
      param = 'hubRefSrc', 
      valueRegex = new RegExp(param+'=([^&]+)'), 
      match = qs.match(valueRegex), 
      referrer; 
   if (match) { 
      // StreamHub generated traffic! 
      referrer = match[1]; 
      console.log('StreamHub referred via', referrer); 
   } else { 
      // StreamHub did not refer this traffic 
   } 
}())
```

この機能を使用するアプリ:

* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md)
* [Ssiindes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)