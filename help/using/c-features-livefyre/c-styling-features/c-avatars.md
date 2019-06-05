---
description: ユーザーがコンテンツと共に表示する画像をカスタマイズできます。
seo-description: ユーザーがコンテンツと共に表示する画像をカスタマイズできます。
seo-title: アバター
title: アバター
uuid: bf20f3bc-3dcc-4e16- a629-3380d1a7a3f2
translation-type: tm+mt
source-git-commit: 7dc3ac6725a27460cecfa6051549da85370ca053

---


# アバター{#avatars}

ユーザーがコンテンツと共に表示する画像をカスタマイズできます。

すべてのアプリのコンテンツの横にユーザーアバターが表示され、実装で使用されているIDプロファイルシステムから取得されます。これらのアバターは、表示されるアプリに応じてサイズが異なります。

（アプリに表示しない場合は、Livefyreを無効にすることができます）。

>[!NOTE]
>
>アバターは、チャットの場合は25p x25p、他のほとんどのアプリでは50p x50pに表示されます。

## アバターストレージ {#section_zbh_x1f_wy}

AvatarreはLivefyreで非同期に読み込まれます。ユーザーが最初にアプリにサインインするか、関連付けられたアバター画像ファイルを変更すると、そのプロフィール画像がタスクキューに追加されます。（デフォルトのアバターは、ユーザーのユーザーがLivefyreアバターの保存場所にアップロードされると一時的に表示されます）。

## Gragatars {#section_mqh_p1f_wy}

LivefyreはGrilatarの使用をサポートしています。ユーザーがユーザープロファイルの一部としてカスタムアバターを持っていない場合、LivefyreはそのユーザーのGragatarをチェックします。Grilatarがない場合、デフォルトのアバターが使用されます。


この機能を使用するアプリ:

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)

