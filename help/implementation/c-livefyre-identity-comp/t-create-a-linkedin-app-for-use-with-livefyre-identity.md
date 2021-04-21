---
description: Livefyre IDとLinkedInを使用して、ユーザーがLinkedInログインを使用してサイト上のアプリを操作できるようにすることができます。
title: Livefyre IDと共に使用するLinkedInアプリを作成する
exl-id: e77eca6a-1698-414e-994e-1189f780ada1
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---

# Livefyre IDと共に使用するLinkedInアプリを作成{#create-a-linkedin-app-for-use-with-livefyre-identity}

Livefyre IDとLinkedInを使用して、ユーザーがLinkedInログインを使用してサイト上のアプリを操作できるようにすることができます。

LinkedInログインを有効にするには、Livefyreで次のLinkedInアプリ情報が必要です。

* Consumer key（APIキー）
* Consumer secret（APIシークレット）

Livefyre IDで使用するLinkedInアプリを作成するには：

1. https://www.linkedin.com/secure/developerにアクセスし、LinkedInアカウントにサインインして、Livefyre Idで使用する新規アプリを作成するか、既存のアプリを選択します。
1. クリック **[!UICONTROL Create Application]**.
1. フォームに入力し、アプリを作成します。
1. **[!UICONTROL Default Application Permissions]**&#x200B;で、**[!UICONTROL r_basicprofile]**&#x200B;および&#x200B;**[!UICONTROL r_emailaddress]**&#x200B;アプリの権限を有効にします。
1. **[!UICONTROL OAuth 2.0 Authorized Redirect URL]**&#x200B;を`https://identity.livefyre.com/{network-name}.fyre.co/api/v1.0/public/profile/social/complete/linkedin_fyre`と入力します。
1. アプリを保存します。
1. **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > LinkedIn]**&#x200B;で、**[!UICONTROL Enable LinkedIn Login]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。
1. LinkedInクライアントIDとLinkedInクライアントシークレットを入力します。
1. クリック **[!UICONTROL Save Settings]**.

完了すると、LinkedInのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのAPIキー(Consumer key)とAPIシークレット(Consumer secret)がリストされます。
