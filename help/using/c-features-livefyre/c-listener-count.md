---
description: リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。
seo-description: リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。
seo-title: リスナー数
solution: Experience Manager
title: リスナー数
uuid: fdd7cfe4-ae69-4d31-baa2-8978368fc3e8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 1%

---


# リスナー数{#listener-count}

リスナーカウントは、ページ上のアプリのサイト訪問者数を追跡し、この数を表示するカウンターです。

Listener Countは、アプリがインスタンス化されたページに対してブラウザーが開くサイト訪問者の数です。 これにより、特定の時点でページ上にあるサイト訪問者の数を把握できるので、ストリーミングコンテンツやライブコンテンツをリアルタイムで視聴している間にユーザーを追跡できます。

Livefyreのリスナーカウントは次のように機能します。

1. アプリケーションを含むサイトが、60秒ごとにLivefyreサーバーにpingを送信する。
1. Livefyreサーバーは、アプリを表示するページ上のサイト訪問者数(そのページに開いているブラウザーを持つサイト訪問者の数として定義)で応答します。
1. アプリを含むページ上のサイト訪問者の数がアプリに表示されます。

この機能を使用するアプリ：

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)

## リスナーアバター{#section_wcn_kxp_vz}

リスナー数は最大10個のアバターを表示し、会話用に&#x200B;**[!UICONTROL Follow]**&#x200B;をクリックした人のアバターのみを表示します。

>[!NOTE]
>
>スペースの制約により、モバイルインターフェイスにはリスナーの数と小さな「人」アイコンのみが表示されます。

Livefyreリスナーカウントは、特定の時点でページ上でアクティブに操作している人の数と、会話をフォローしている人の数を表示します。 誰かがページを訪問し、会話をフォローしている場合、そのユーザーは重複としてカウントされません。 例えば、ユーザーがページを表示中に&#x200B;**[!UICONTROL Follow]**&#x200B;をクリックした場合、リスナー数は増えません。そのユーザーが&#x200B;**[!UICONTROL Unfollow]**&#x200B;をクリックしても、カウントは減少しません。

この機能を使用するアプリ：

* [チャット](../c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [レビュー](../c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Storify 2](../c-about-apps/c-storify2/c-storify2.md#c_storify2)

