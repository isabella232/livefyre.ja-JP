---
description: リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。
seo-description: リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。
seo-title: リスナー数
solution: Experience Manager
title: リスナー数
uuid: fdd7cfe4-ae69-4d31-baa2-8978368fc3e8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# リスナー数{#listener-count}

リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。

Listener countは、アプリがインスタンス化されたページにブラウザーを開いているサイト訪問者の数です。 これにより、特定の時点でページ上にいるサイト訪問者の数を知ることができるので、ストリーミングやライブコンテンツをリアルタイムで視聴している間に訪問者を追跡できます。

Livefyreのリスナー数は次のように機能します。

1. アプリを含むサイトが、60秒ごとにLivefyreサーバーにpingを送信します。
1. Livefyreサーバーは、アプリを表示するページ上のサイト訪問者数（そのページを開いているブラウザーでのサイト訪問者数として定義）を返します。
1. アプリを含むページのサイト訪問者数がアプリに表示されます。

この機能を使用するアプリ：

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)

## リスナーアバター {#section_wcn_kxp_vz}

リスナー数は最大10個のアバターを表示し、会話をクリックした人のアバターのみ **[!UICONTROL Follow]** を表示します。

>[!NOTE]
>
>スペースの制約により、モバイルインターフェイスにはリスナーの数と小さな「人」アイコンのみが表示されます。

Livefyreリスナーカウントは、特定の時点でページ上でアクティブな人の数と、会話をフォローしている人の数を表示します。 誰かがページ上にいて会話をフォローしている場合、そのユーザーは二重にカウントされません。 例えば、ユーザーがページ上にいてクリックした場合、 **[!UICONTROL Follow]**&#x200B;リスナー数は増えません。そのユーザーがクリックし **[!UICONTROL Unfollow]**&#x200B;ても、カウントは減少しません。

この機能を使用するアプリ：

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify 2](../c-about-apps/c-storify2/c-storify2.md#c_storify2)

