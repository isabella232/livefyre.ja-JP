---
description: LinkedInのLivefyre IDを使用すると、ユーザーはLinkedInログインを使用してサイトのアプリを操作できます。
seo-description: LinkedInのLivefyre IDを使用すると、ユーザーはLinkedInログインを使用してサイトのアプリを操作できます。
seo-title: Livefyre IDで使用するLinkedInアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するLinkedInアプリの作成
uuid: c5112f24- a4e0-4526- afe8- b8f27a3b2854
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するLinkedInアプリの作成{#create-a-linkedin-app-for-use-with-livefyre-identity}

LinkedInのLivefyre IDを使用すると、ユーザーはLinkedInログインを使用してサイトのアプリを操作できます。

LinkedInのログインを有効にするには、Livefyreに以下のLinkedInアプリ情報が必要です。

* 消費者キー（APIキー）
* コンシューマーシークレット（APIシークレット）

Livefyre IDで使用するLinkedInアプリを作成するには:

1. https://www.linkedin.com/secure/developerに移動し、LinkedInアカウントにサインインして新規作成するか、Livefyre IDで使用する既存のアプリを選択します。
1. **[!UICONTROL Create Application]**をクリックします。
1. フォームを完成させてアプリケーションを作成します。
1. で **[!UICONTROL Default Application Permissions]**、および **[!UICONTROL r_basicprofile]****[!UICONTROL r_emailaddress]** アプリの権限を有効にします。
1. **[!UICONTROL OAuth 2.0 Authorized Redirect URL]** 「名前 `https://identity.livefyre.com/{network-name}.fyre.co/api/v1.0/public/profile/social/complete/linkedin_fyre`」を入力します。
1. アプリを保存します。
1. で **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > LinkedIn]****[!UICONTROL Enable LinkedIn Login]** 、切り替えをに切り替え **[!UICONTROL On]**ます。
1. LinkedInクライアントIDとLinkedInクライアントシークレットを入力します。
1. **[!UICONTROL Save Settings]**をクリックします。

完了すると、LinkedInのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのAPIキー（消費者キー）とAPIシークレット（消費者シークレット）が一覧表示されます。
