---
description: 権利要求の機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-description: 権利要求の機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-title: 権限の要求
title: 権限の要求
uuid: d3194afa-f3c6-44ed-b03f-9b1ecb50c1d3
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 権限の要求{#requesting-rights}

権利要求の機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。

ライブラリ、アプリコンテンツ、ModQおよびAEMコマースでは、次の権限ステータスを使用できます。

* **[!UICONTROL Granted]**. 作成者がコンテンツを再利用する権限をユーザーに付与すると、アセットのステータスがに変わりま **[!UICONTROL Granted]**&#x200B;す。

* **[!UICONTROL Expired]**. Livefyreは、InstagramとTwitterのストリームを監視し、発言者の14日間の返信を確認します。 14日が過ぎると、要求の期限が切れ、権限要求のステータスがに変わり、2 **[!UICONTROL Expired]**&#x200B;つ目の要求を送信したり、ライブラリからアイテムを削除したりできます。
* **[!UICONTROL Requested]**. ライブラリからコンテンツの権限を要求します。 これは、一度に1つ以上のアセットに対して実行できます。 権限を要求すると、Livefyreはアセットのステータスをに設定しま **[!UICONTROL Requested]**&#x200B;す。
* **[!UICONTROL Needs Review]**. 作成者が#approvalHashtagを含まないメモを返信すると、アセットのステータスがに変わります **[!UICONTROL Needs Review]**。

* **[!UICONTROL Request Failed]**. リクエストの送信に失敗しました（期限切れのトークンなどが原因です）。
* **[!UICONTROL Request Pending]**. 一度に送信される権限要求をキューに入れます。

TwitterおよびInstagramから取得したアセットの権限を要求できます。 権限を要求するには、アセットをライブラリに保存する必要があります。

部分的に自動化されたワークフ *ローを使用して* 、Instagramからアセットの権限を要求するようにInstagramビジネスアカウントを設定する必要があります。

この機能は、ビジネスアカウントによる検索またはストリーム検索から取得したコンテンツに対してのみ使用できます。 個人のInstagramアカウントから取得したコンテンツに対する権限を要求するには、権限要求を手動で送信する必要があります。

>[!NOTE]
>
>様々な種類のInstagramアカウントとその使用方法について詳しくは、Instagramアカウントについてを参照 [してください](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)。 Instagramアカウントの権限を要求する方法について詳しくは、「手動の権限要求の送信 [」および「部分的に自動化さ](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md#c_send_instagram_manual_rights_request) れた権限要求の送信」を参照してください [](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md#c_send_an_instagram_rights_request_from_the_library)。

