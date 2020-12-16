---
description: LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-description: LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-title: Livefyre IDで使用するLinkedInアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するLinkedInアプリの作成
uuid: c5112f24-a4e0-4526-afe8-b8f27a3b2854
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---


# Livefyre IDと共に使用するLinkedInアプリを作成{#create-a-linkedin-app-for-use-with-livefyre-identity}

LinkedInとLivefyre IDを使用して、ユーザーがLinkedInのログインを使用してサイト上のアプリを操作できるようにすることができます。

LinkedInのログインを有効にするには、Livefyreで次のLinkedInアプリ情報が必要です。

* Consumer key（APIキー）
* Consumer secret（APIシークレット）

Livefyre Idで使用するLinkedInアプリを作成するには：

1. https://www.linkedin.com/secure/developerにアクセスし、LinkedInアカウントにサインインして、新規作成するか、Livefyre Idで使用する既存のアプリを選択します。
1. クリック **[!UICONTROL Create Application]**.
1. フォームに入力し、アプリを作成します。
1. **[!UICONTROL Default Application Permissions]**&#x200B;で、**[!UICONTROL r_basicprofile]**&#x200B;および&#x200B;**[!UICONTROL r_emailaddress]**&#x200B;アプリの権限を有効にします。
1. **[!UICONTROL OAuth 2.0 Authorized Redirect URL]**&#x200B;を`https://identity.livefyre.com/{network-name}.fyre.co/api/v1.0/public/profile/social/complete/linkedin_fyre`と入力します。
1. アプリを保存します。
1. **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > LinkedIn]**&#x200B;で、**[!UICONTROL Enable LinkedIn Login]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。
1. LinkedInのクライアントIDとLinkedInのクライアントシークレットを入力します。
1. クリック **[!UICONTROL Save Settings]**.

完了すると、LinkedInのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのAPIキー(Consumer key)とAPIシークレット(Consumer secret)がリストされます。
