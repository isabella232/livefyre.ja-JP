---
description: 権限リクエストの機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-description: 権限リクエストの機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。
seo-title: 権限の要求
title: 権限の要求
uuid: d3194afa-f3c6-44ed-b03f-9b1ecb50c1d3
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---


# 権限{#requesting-rights}の要求

権限リクエストの機能について説明します。 ユーザー生成コンテンツ(UGC)をLivefyreアプリに取り込むと、コンテンツには再利用のための暗黙の権限が含まれます。 TwitterまたはInstagramのコンテンツを使用するには、発言者の権限が必要です。

ライブラリ、アプリケーションコンテンツ、ModQ、AEMコマースでは、次の権限ステータスを使用できます。

* **[!UICONTROL Granted]**&#x200B;をインストールします。作成者がコンテンツを再利用する権限をユーザーに付与すると、アセットのステータスは&#x200B;**[!UICONTROL Granted]**&#x200B;に変わります。

* **[!UICONTROL Expired]**&#x200B;をインストールします。LivefyreはInstagramとTwitterのストリームを監視し、発言者の14日間の返信を確認します。 14日後に要求の有効期限が切れ、権限要求のステータスが&#x200B;**[!UICONTROL Expired]**&#x200B;に変わり、2つ目の要求を送信したり、ライブラリから項目を削除したりできます。
* **[!UICONTROL Requested]**&#x200B;をインストールします。ライブラリからコンテンツに対する権限を要求します。 これは、一度に1つ以上のアセットに対して実行できます。 権限を要求すると、Livefyreはアセットのステータスを&#x200B;**[!UICONTROL Requested]**&#x200B;に設定します。
* **[!UICONTROL Needs Review]**&#x200B;をインストールします。作成者が#approvalHashtagを含まないメモを使用して返信した場合、アセットのステータスは&#x200B;**[!UICONTROL Needs Review]**&#x200B;に変わります。

* **[!UICONTROL Request Failed]**&#x200B;をインストールします。要求を送信できませんでした（トークンの有効期限などが原因です）。
* **[!UICONTROL Request Pending]**&#x200B;をインストールします。権限要求をキューに入れ、一度に送信される権限が多くならないようにします。

TwitterおよびInstagramから取得したアセットの権限を要求できます。 アセットをライブラリに保存して、権限を要求する必要があります。

部分的に自動化されたワークフローを使用してInstagramのアセットの権限を要求するには、*Instagramビジネスアカウント*&#x200B;を設定する必要があります。

この機能は、ビジネスアカウントによる検索またはストリーム検索で取得したコンテンツに対してのみ使用できます。 個人のInstagramアカウントから取得したコンテンツに対する権限をリクエストするには、権限リクエストを手動で送信する必要があります。

>[!NOTE]
>
>様々な種類のInstagramアカウントとその使用方法について詳しくは、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。 Instagramアカウントの権限を要求する方法について詳しくは、[手動の権限要求の送信](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md#c_send_instagram_manual_rights_request)および[部分的に自動化された権限要求の送信](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md#c_send_an_instagram_rights_request_from_the_library)を参照してください。

