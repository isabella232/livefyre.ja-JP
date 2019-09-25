---
description: 照会トラフィックからページに戻るクリックを追跡します。
seo-description: 照会トラフィックからページに戻るクリックを追跡します。
seo-title: 照会の追跡
solution: Experience Manager
title: 照会の追跡
uuid: 5206cc16-9671-4b3d-a013-be1a3e8c029d
translation-type: tm+mt
source-git-commit: bd989c97ae5cf06a5ac3deec215f865b0fe95d16

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

* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md)
* [サイデン](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)