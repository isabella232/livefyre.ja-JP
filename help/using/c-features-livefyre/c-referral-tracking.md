---
description: 照会トラフィックからページに戻るクリックを追跡します。
seo-description: 照会トラフィックからページに戻るクリックを追跡します。
seo-title: 照会の追跡
solution: Experience Manager
title: 照会の追跡
uuid: 7daf615d-0c07-49d1-adb2-1ac67ea563e7
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 照会の追跡{#referral-tracking}

照会トラフィックからページに戻るクリックを追跡します。

Livefyreは、ソーシャルネットワークにコメントが投稿または共有された場合、およびLivefyreの電子メールに含まれるパーマリンクに対して、URLにリファラル変数を追加します。 この変数を使用して、Livefyre Appsからソーシャルまたは所有するプロパティへのリファラルトラフィックを追跡します。

Livefyreアプリでは、参照トラフィックに起因するデータストリームを追跡し、サイトのトラフィックを分析できます。

## Livefyre照会トラフィックの追跡 {#section_nsy_qp4_xz}

ソーシャルネットワークや電子メールからのLivefyreリファラルトラフィックは、ページのURL内のクエリ文字列パラメーターを調べ、ページにコードを導入して、分析プロバイダーを通じて追跡することで追跡できます。 Livefyreは、ソーシャルネットワークにコメントが投稿または共有されるとき、およびLivefyreの電子メールに含まれる永続的なリンクに対して、URLにリファラルリンクを追加します。

## 導入例 {#section_xvs_x44_xz}

トラフィックがStreamHubを使用した通知から送信された場合、hubRefSrcクエリ文字列パラメーターが存在し、値はemail、facebook、twitter、linkedinまたはpermalinkになります。 hubRefSrcパラメーター名は、Livefyre配信チームがネットワークレベルで設定できます。

解析プラットフォームと統合するには、ページで読み込み時にhubRefSrcを探し、トラフィックが存在する場合は記録する必要があります。

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



この機能を使用するアプリ：

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [サイデン](../c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)

