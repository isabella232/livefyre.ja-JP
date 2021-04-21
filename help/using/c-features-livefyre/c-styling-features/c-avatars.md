---
description: ユーザーがコンテンツと共に表示する画像をカスタマイズできるようにします。
title: アバター
exl-id: cff7f6be-3660-4d71-949b-6ac04379d68d
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 1%

---

# アバター{#avatars}

ユーザーがコンテンツと共に表示する画像をカスタマイズできるようにします。

ユーザーアバターは、（デフォルトでは）すべてのアプリ内のコンテンツの横に表示され、実装で使用されているIDプロファイルシステムから取得されます。 これらのアバターのサイズは、表示されるアプリに応じて異なります。

（Avatarをアプリで表示したくない場合は、Livefyreで無効にできます）。

>[!NOTE]
>
>アバターは、チャットの場合は25p x 25p、他のほとんどのアプリの場合は50p x 50pで表示されます。

## アバターストレージ{#section_zbh_x1f_wy}

アバターは、Livefyreでは非同期で読み込まれます。 ユーザーが最初にアプリにサインインしたとき、または関連付けられたアバター画像ファイルを変更したとき、プロファイル画像はタスクキューに追加されます。 (デフォルトのアバターは、ユーザーがLivefyreのアバターストレージの場所にアップロードされる間、一時的に表示されます)。

## 重力{#section_mqh_p1f_wy}

LivefyreはGravatarsの使用をサポートしています。 ユーザーがユーザープロファイルの一部としてカスタムアバターを持っていない場合、LivefyreはそのユーザーのGravatarをチェックします。 重力が存在しない場合は、デフォルトのアバターが使用されます。


この機能を使用するアプリ：

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
