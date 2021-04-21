---
description: 照会トラフィックからページに戻るクリックを追跡します。
title: 照会の追跡
exl-id: 44cc221c-1603-4e6e-ae4a-1b993f7dc446
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# 参照の追跡{#referral-tracking}

照会トラフィックからページに戻るクリックを追跡します。

Livefyreは、ソーシャルネットワークにコメントが投稿または共有されるとき、およびLivefyre電子メールに含まれる永続的なリンクに対して、URLに参照変数を追加します。 この変数を使用して、Livefyre AppsからSocialまたは所有するプロパティへの参照トラフィックを追跡します。

Livefyreアプリを使用すると、照会トラフィックから生じるデータストリームを追跡し、サイトのトラフィックを分析できます。

## Livefyre参照トラフィックの追跡{#section_nsy_qp4_xz}

ソーシャルネットワークや電子メールからのLivefyre参照トラフィックは、ページのURL内のクエリ文字列パラメーターを検査し、ページにコードを導入して、分析プロバイダー経由で追跡することで追跡できます。 Livefyreは、ソーシャルネットワークにコメントが投稿または共有されるとき、およびLivefyre電子メールに含まれる永続的なリンクに対して、URLにリファラルリンクを追加します。

## 導入例 {#section_xvs_x44_xz}

トラフィックがStreamHubを使用した通知から送信された場合、hubRefSrcクエリ文字列パラメーターが存在し、値はemail、facebook、twitter、linkedinまたはpermalinkになります。 hubRefSrcパラメーター名は、Livefyre配信チームがネットワークレベルで設定できます。

分析プラットフォームと統合するには、ページでhubRefSrcの読み込み時に探し、トラフィックが存在する場合は記録する必要があります。

例：

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
* [Sidenots](../c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
