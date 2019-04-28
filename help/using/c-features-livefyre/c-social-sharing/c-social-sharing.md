---
description: 別のユーザーのコンテンツまたはコンテンツをFacebook、Twitter、LinkedInに共有します。
seo-description: 別のユーザーのコンテンツまたはコンテンツをFacebook、Twitter、LinkedInに共有します。
seo-title: ソーシャルシェア
solution: Experience Manager
title: ソーシャルシェア
uuid: 3fd8a628-2414-45b5- b91c-2ad33aad2634
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# ソーシャルシェア{#social-sharing}

別のユーザーのコンテンツまたはコンテンツをFacebook、Twitter、LinkedInに共有します。

ソーシャルシェアを使用すると、コミュニティでは、Facebook、Twitter、LinkedInなどのソーシャルネットワーク上の友達にアプリから自分のアイデアを共有し、他のユーザーのコンテンツをFacebookやTwitterに共有できます。ソーシャルシェアを有効にすると、コミュニティはコンテンツに最適な反応を分散し、サイトにより多くのトラフィックをもたらすことができます。

## ソーシャルネットワークへのコンテンツの共有 {#section_t1q_mz2_wy}

ネットワークを設定して、コンテンツをLivefyreアプリに投稿する際に、ユーザーがTwitter、FacebookまたはLinkedInと共有できるようにすることができます。デフォルトのLivefyre **[!UICONTROL Share Modal]** には、3つのサイトすべてへのリンクが含まれています。このモーダルをカスタマイズAPIでカスタマイズしてLivefyreのデフォルトをオーバーライドし、独自のものを実装することができます。詳しくは、高度なトピック/ソーシャルシェアの有効化を参照してください。

ユーザーがソーシャル **[!UICONTROL Share]** ネットワーク（Facebook、TwitterまたはLinkedIn）にコメントを投稿する場合、ソーシャルアプリからログインするように促すメッセージが表示されます。（使用可能な共有オプションのリストはカスタマイズできます。デフォルトでは、FacebookおよびTwitter共有のチェックボックスはすべてのアプリに表示されます。）カスタムネットワークの場合、ソーシャルアプリはソーシャルアプリに設定する必要があります。統合プロセスの一部として、Studioの統合設定ページからアプリの資格情報を追加します。

>[!NOTE]
>
>LinkedInはデフォルトでLivefyreコミュニティコメントに含まれています。アプリを埋め込むときに、コメントツールバーのLinkedInボタンを有効にするには、カスタムネットワークが&quot;li&quot;値を渡す必要があります。（詳しくは、開発者ドキュメントのソーシャルシェアの有効化を参照してください）。

## 他のユーザーのコンテンツをソーシャルネットワークに共有 {#section_blw_vy2_wy}

別のユーザーの投稿 **[!UICONTROL Share]** をクリックすると、共有コメントペインが開きます。このペインには、編集可能なテキストフィールド、有効になっている共有オプション、投稿への固定リンクが含まれます。

投稿をクリック **[!UICONTROL Share]** すると、次のことができます。

* ユーザーは、TwitterまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページを認証してユーザーのソーシャルネットワークに投稿すると、TwitterボタンまたはFacebookボタンが点灯して、ユーザーがアクティブであることを知らせることができます。
* ユーザーは共有投稿ボックス内でコンテンツをパーソナライズできます。
* クリック **[!UICONTROL Share]** すると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信されます。リンクをクリックすると、ユーザーが共有したい正確な投稿に移動します。
* 電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けることで、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合時に、ユーザーが共有できるソーシャルネットワークを指定できます。また、カスタムのPermalinkを統合して、現在のメディアリンクとの統一を実現することもできます。

別のユーザーの投稿 **[!UICONTROL Share]** をクリックすると **[!UICONTROL Share Comment]**、編集可能なテキストフィールド、有効になっている共有オプション、投稿への固定リンクなどのペインが開きます。

投稿をクリック **[!UICONTROL Share]** すると、次のことができます。

* ユーザーは、TwitterまたはFacebookアイコンをクリックして、ソーシャルネットワークに接続できます。
* ページを認証してユーザーのソーシャルネットワークに投稿すると、TwitterボタンまたはFacebookボタンが点灯して、ユーザーがアクティブであることを知らせることができます。
* ユーザーは共有投稿ボックス内でコンテンツをパーソナライズできます。
* クリック **[!UICONTROL Share]** すると、ユーザーのアクティブなソーシャルネットワークにコンテンツが送信されます。リンクをクリックすると、ユーザーが共有したい正確な投稿に移動します。
* 電子メール、ブログ投稿またはソーシャルネットワーク内にPermalinkを貼り付けることで、特定のコメントへのリンクを共有することもできます。

>[!NOTE]
>
>統合時に、ユーザーが共有できるソーシャルネットワークを指定できます。また、カスタムのPermalinkを統合して、現在のメディアリンクとの統一を実現することもできます。



この機能を使用するアプリ:

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [ポール](/help/using/c-about-apps/c-polls-app/c-polls-app.md#c_polls_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Ssiindes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)

