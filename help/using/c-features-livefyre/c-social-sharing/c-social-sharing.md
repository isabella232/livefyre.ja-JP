---
description: 別のユーザーからFacebook、TwitterまたはLinkedInにコンテンツやコンテンツを共有します。
seo-description: 別のユーザーからFacebook、TwitterまたはLinkedInにコンテンツやコンテンツを共有します。
seo-title: ソーシャルシェア
solution: Experience Manager
title: ソーシャルシェア
uuid: 3fd8a628-2414-45b5-b91c-2ad33aad2634
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# ソーシャルシェア{#social-sharing}

別のユーザーからFacebook、TwitterまたはLinkedInにコンテンツやコンテンツを共有します。

ソーシャルシェアを使用すると、アプリの思いをFacebook、Twitter、LinkedInなどのソーシャルネットワーク上の友達に共有したり、他のユーザーのコンテンツをFacebookやTwitterに共有したりできます。 ソーシャルシェアを有効にすると、コミュニティでコンテンツに対する最適な反応を広げ、より多くのトラフィックをサイトに送ることができます。

## ソーシャルネットワークへのコンテンツの共有 {#section_t1q_mz2_wy}

Livefyreアプリにコンテンツを投稿する際に、ユーザーがTwitter、FacebookまたはLinkedInと共有できるようにネットワークを設定できます。 デフォルトのLivefyreには、3つ **[!UICONTROL Share Modal]** のサイトへのリンクがすべて含まれます。 Post To APIを使用してこのモーダルをカスタマイズし、Livefyreのデフォルト設定を上書きして、独自のモーダルを実装できます。 詳しくは、高度なトピック/ソーシャルシェアを有効にするを参照してください。

ユーザーがクリックし **[!UICONTROL Share]** てソーシャルネットワーク（Facebook、TwitterまたはLinkedIn）にコメントを投稿すると、ソーシャルアプリを使用してログインするよう求められます。 (利用可能な共有オプションのリストはカスタマイズ可能です。 デフォルトでは、FacebookとTwitterの共有チェックボックスはすべてのアプリに表示されます)。カスタムネットワークの場合、ソーシャルアプリはソーシャルアプリに設定する必要があります。 統合プロセスの一環として、Studioの統合設定ページでアプリの資格情報を追加します。

>[!NOTE]
>
>LinkedInは、Livefyreコミュニティコメントにデフォルトで含まれています。 コメントツールバーのLinkedInボタンを有効にするには、アプリを埋め込む際に、カスタムネットワークで「li」値を渡す必要があります。 （詳しくは、開発者向けドキュメントでソーシャルシェアを有効にするを参照してください）。

## 他のユーザーのコンテンツをソーシャルネットワークに共有する {#section_blw_vy2_wy}

別のユ **[!UICONTROL Share]** ーザーの投稿をクリックすると、共有コメントパネルが開きます。このパネルには、編集可能なテキストフィールド、有効な共有オプション、投稿へのパーマリンクが含まれます。

投稿をクリ **[!UICONTROL Share]** ックすると、

* ユーザーは、TwitterアイコンまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページがユーザーのソーシャルネットワークに投稿することを承認すると、TwitterまたはFacebookのボタンが点灯し、アクティブであることがユーザーに通知されます。
* ユーザーは、投稿の共有ボックス内でコンテンツをパーソナライズできます。
* をクリ **[!UICONTROL Share]** ックすると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信され、ユーザーが共有したい正確な投稿に他のユーザーが移動するリンクが表示されます。
* また、電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けて、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合中に、ユーザーが共有できるソーシャルネットワークを指定できます。 また、カスタムのPermalinkを統合して、現在のメディアリンクとの統一性を実現することもできます。

別のユ **[!UICONTROL Share]****[!UICONTROL Share Comment]** ーザーの投稿をクリックすると、パネルが開きます。このパネルには、編集可能なテキストフィールド、有効な共有オプション、投稿へのパーマリンクが含まれます。

投稿をクリ **[!UICONTROL Share]** ックすると、

* ユーザーは、TwitterアイコンまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページがユーザーのソーシャルネットワークに投稿することを承認すると、TwitterまたはFacebookのボタンが点灯し、アクティブであることがユーザーに通知されます。
* ユーザーは、投稿の共有ボックス内でコンテンツをパーソナライズできます。
* をクリ **[!UICONTROL Share]** ックすると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信され、ユーザーが共有したい正確な投稿に他のユーザーが移動するリンクが表示されます。
* また、電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けて、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合中に、ユーザーが共有できるソーシャルネットワークを指定できます。 また、カスタムのPermalinkを統合して、現在のメディアリンクとの統一性を実現することもできます。



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
* [サイデン](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)

