---
description: リスナー数は、あるページ上のアプリの訪問者数を追跡し、この数を表示するカウンターです。
seo-description: リスナー数は、あるページ上のアプリの訪問者数を追跡し、この数を表示するカウンターです。
seo-title: リスナー数
solution: Experience Manager
title: リスナー数
uuid: fdd7cfe4- ae69-4d31- baa2-8978368fc3e8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# リスナー数{#listener-count}

リスナー数は、あるページ上のアプリの訪問者数を追跡し、この数を表示するカウンターです。

「リスナー数」は、アプリケーションがインスタンス化されたページを開くブラウザーを持つサイト訪問者の数です。これにより、いつでもページにあるサイト訪問者数を把握できるので、ストリーミングコンテンツやライブコンテンツをリアルタイムで視聴しながら追跡できます。

Livefyreのリスナー数は次のように機能します。

1. アプリケーションが60秒ごとにLivefyreサーバーにpingを含むサイト。
1. Livefyreサーバーは、アプリを表示するページの訪問者数とともに応答します（そのページへのブラウザーでの訪問者の数として定義されたサイト訪問者数）。
1. アプリに表示されているページ訪問者の数がアプリに表示されます。

この機能を使用するアプリ:

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)

## リスナーアバター {#section_wcn_kxp_vz}

リスナー数には、最大10個のアバターが表示され、会話をクリック **[!UICONTROL Follow]** した人のアバターのみが表示されます。

>[!NOTE]
>
>スペース制約により、モバイルインターフェイスでは、リスナーの数のみが表示され、小さい「人」アイコンが表示されます。

LivefyreリスナーCountには、特定の時点でのページ上の訪問者数と、会話後の人の数が表示されます。誰かがページにいて会話の後にある場合、そのユーザーは二重にカウントされません。例えば、ユーザーがページにいてクリック **[!UICONTROL Follow]** した場合、リスナー数は増えません。そのユーザーがクリック **[!UICONTROL Unfollow]** した場合、カウントは減少しません。

この機能を使用するアプリ:

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify2](../c-about-apps/c-storify2/c-storify2.md#c_storify2)

