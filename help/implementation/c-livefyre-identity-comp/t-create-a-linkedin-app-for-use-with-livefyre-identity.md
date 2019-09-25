---
description: LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-description: LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-title: Livefyre IDで使用するLinkedInアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するLinkedInアプリの作成
uuid: c5112f24-a4e0-4526-afe8-b8f27a3b2854
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するLinkedInアプリの作成{#create-a-linkedin-app-for-use-with-livefyre-identity}

LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリとやり取りできるようにすることができます。

LinkedInのログインを有効にするには、Livefyreで次のLinkedInアプリの情報が必要です。

* コンシューマーキー（APIキー）
* コンシューマシークレット（APIシークレット）

Livefyre idで使用するLinkedInアプリを作成するには：

1. https://www.linkedin.com/secure/developerにアクセスし、LinkedInアカウントにサインインして、新規作成するか、Livefyre IDで使用する既存のアプリを選択します。
1. Click **[!UICONTROL Create Application]**.
1. フォームに入力し、申込書を作成します。
1. で、およびア **[!UICONTROL Default Application Permissions]**&#x200B;プリの権限 **[!UICONTROL r_basicprofile]** を有 **[!UICONTROL r_emailaddress]** 効にします。
1. 「」に「」と入 **[!UICONTROL OAuth 2.0 Authorized Redirect URL]** 力しま `https://identity.livefyre.com/{network-name}.fyre.co/api/v1.0/public/profile/social/complete/linkedin_fyre`す。
1. アプリを保存します。
1. で、切 **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > LinkedIn]**&#x200B;り替えをに **[!UICONTROL Enable LinkedIn Login]** 切り替えま **[!UICONTROL On]**&#x200B;す。
1. LinkedInのクライアントIDとLinkedInのクライアントシークレットを入力します。
1. Click **[!UICONTROL Save Settings]**.

完了すると、LinkedInのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのAPIキー（コンシューマーキー）とAPIシークレット（コンシューマーシークレット）が表示されます。
