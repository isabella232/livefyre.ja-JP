---
description: 他のユーザーからFacebook、Twitter、LinkedInにコンテンツやコンテンツを共有します。
seo-description: 他のユーザーからFacebook、Twitter、LinkedInにコンテンツやコンテンツを共有します。
seo-title: ソーシャルシェア
solution: Experience Manager
title: ソーシャルシェア
uuid: 3fd8a628-2414-45b5-b91c-2ad33aad2634
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 1%

---


# ソーシャルシェア{#social-sharing}

他のユーザーからFacebook、Twitter、LinkedInにコンテンツやコンテンツを共有します。

ソーシャルシェア機能を使用すると、アプリからFacebook、Twitter、LinkedInなどのソーシャルネットワーク上の友達に自分の考えを共有したり、他のユーザーのコンテンツをFacebookやTwitterに共有したりできます。 ソーシャルシェアを有効にすると、コミュニティがコンテンツに対する最適な反応を広げ、より多くのトラフィックをサイトに送り込むことができます。

## ソーシャルネットワークへのコンテンツの共有{#section_t1q_mz2_wy}

Livefyre Appsにコンテンツを投稿する際に、ユーザーがTwitter、FacebookまたはLinkedInと共有できるようにネットワークを設定できます。 初期設定のLivefyre **[!UICONTROL Share Modal]**&#x200B;には、3つのサイトすべてへのリンクが含まれます。 「投稿先API」を使用してこのモーダルをカスタマイズし、Livefyreのデフォルト設定を上書きして、独自のモーダルを実装できます。 詳しくは、高度なトピック/ソーシャルシェアを有効にするを参照してください。

ユーザーが&#x200B;**[!UICONTROL Share]**&#x200B;をクリックしてソーシャルネットワーク（Facebook、TwitterまたはLinkedIn）にコメントを投稿すると、ソーシャルアプリを使用してログインするように求められます。 (利用可能な共有オプションのリストはカスタマイズできます。 デフォルトでは、FacebookとTwitterの共有チェックボックスはすべてのアプリに表示されます)。 カスタムネットワークの場合、ソーシャルアプリは、ソーシャルアプリとして設定する必要があります。 統合プロセスの一環として、Studioの統合設定ページでアプリケーションの資格情報を追加します。

>[!NOTE]
>
>LinkedInは、Livefyreコミュニティコメントにデフォルトで含まれています。 カスタムネットワークで、コメントツールバーのLinkedInボタンを有効にするには、アプリを埋め込む際に「li」値を渡す必要があります。 （詳しくは、開発者向けドキュメントのソーシャルシェアを有効にするを参照してください）。

## 他のユーザーのコンテンツをソーシャルネットワークに共有する{#section_blw_vy2_wy}

別のユーザーの投稿で&#x200B;**[!UICONTROL Share]**&#x200B;をクリックすると、共有コメントパネルが開きます。このパネルには、編集可能なテキストフィールド、有効な共有オプション、投稿へのパーマリンクが含まれます。

投稿の&#x200B;**[!UICONTROL Share]**&#x200B;をクリックすると、次のようになります。

* ユーザーは、TwitterアイコンまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページの投稿をユーザーのソーシャルネットワークに承認すると、TwitterまたはFacebookのボタンが点灯し、アクティブであることがユーザーに通知されます。
* ユーザーは、投稿の共有ボックス内のコンテンツをパーソナライズできます。
* **[!UICONTROL Share]**&#x200B;をクリックすると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信され、そのリンクを使用して、ユーザーが共有したい正確な投稿に他のユーザーが移動します。
* また、電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けて、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合中に、どのソーシャルネットワークをユーザーが共有できるかを指定できます。 また、カスタムのパーマリンクを統合して、現在のメディアリンクとの統一性を確保することもできます。

別のユーザーの投稿で&#x200B;**[!UICONTROL Share]**&#x200B;をクリックすると、**[!UICONTROL Share Comment]**&#x200B;ペインが開きます。このペインには、編集可能なテキストフィールド、有効な共有オプション、および投稿へのパーマリンクが含まれます。

投稿の&#x200B;**[!UICONTROL Share]**&#x200B;をクリックすると、次のようになります。

* ユーザーは、TwitterアイコンまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページの投稿をユーザーのソーシャルネットワークに承認すると、TwitterまたはFacebookのボタンが点灯し、アクティブであることがユーザーに通知されます。
* ユーザーは、投稿の共有ボックス内のコンテンツをパーソナライズできます。
* **[!UICONTROL Share]**&#x200B;をクリックすると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信され、そのリンクを使用して、ユーザーが共有したい正確な投稿に他のユーザーが移動します。
* また、電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けて、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合中に、どのソーシャルネットワークをユーザーが共有できるかを指定できます。 また、カスタムのパーマリンクを統合して、現在のメディアリンクとの統一性を確保することもできます。



この機能を使用するアプリ：

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [投票](/help/using/c-about-apps/c-polls-app/c-polls-app.md#c_polls_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenots](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)

