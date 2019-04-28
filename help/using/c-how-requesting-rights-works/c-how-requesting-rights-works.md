---
description: 権限リクエストの機能について説明します。ユーザ生成コンテンツ（UGC）をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙的な権限が含まれます。TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-description: 権限リクエストの機能について説明します。ユーザ生成コンテンツ（UGC）をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙的な権限が含まれます。TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-title: 権限の要求
title: 権限の要求
uuid: d3194afa- f3c6-44ed- b03f-9b1ecb50c1d3
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 権限の要求{#requesting-rights}

権限リクエストの機能について説明します。ユーザ生成コンテンツ（UGC）をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙的な権限が含まれます。TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。

ライブラリ、アプリケーションコンテンツ、MOQおよびAEMコマースから利用できる権限ステータスは次のとおりです。

* **[!UICONTROL Granted]**. 作成者がコンテンツの再利用権を付与すると、アセットのステータスが変更 **[!UICONTROL Granted]** されます。

* **[!UICONTROL Expired]**. 作成者の返信用にInstagramストリームとTwitterストリームを14日間監視します。14日後にリクエストが期限切れになると、権限リクエストのステータスが変更され、 **[!UICONTROL Expired]** 2回目のリクエストを送信したり、ライブラリからアイテムを削除したりできます。
* **[!UICONTROL Requested]**. ライブラリからのコンテンツの要求権限。一度に1つ以上のアセットに対してこれを実行できます。権限を要求すると、アセットステータスがLivefyreによって設定 **[!UICONTROL Requested]** されます。
* **[!UICONTROL Needs Review]**. 作成者が# ApprovalHashTagを含まないメモを返信した場合、アセットのステータスが変更 **[!UICONTROL Needs Review]** されます。

* **[!UICONTROL Request Failed]**. 要求が送信できませんでした（期限切れトークンなど）。
* **[!UICONTROL Request Pending]**. &quot;Rights Request&quot;をキューに一度に送信しないようにキューに入れます。

TwitterおよびInstagramから取得したアセットに対する権限を要求できます。権限をリクエストするには、アセットをライブラリに保存する必要があります。

部分的に自動化されたワークフローを使用してInstagramからのアセットの権限をリクエストするには *、Instagramのビジネスアカウント* を設定する必要があります。

この機能は、ビジネスアカウントで検索またはストリーム検索から取得したコンテンツにのみ使用できます。個人用Instagramアカウントから取得したコンテンツの権限をリクエストするには、権限リクエストを手動で送信する必要があります。

>[!NOTE]
>
>Instagramアカウントの種類と使用方法について詳しくは、Instagramアカウント [について](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。For information on how to request rights for Instagram accounts, see [Send Manual Rights Requests](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md#c_send_instagram_manual_rights_request) and [Send Partially-Automated Rights Requests](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md#c_send_an_instagram_rights_request_from_the_library).

