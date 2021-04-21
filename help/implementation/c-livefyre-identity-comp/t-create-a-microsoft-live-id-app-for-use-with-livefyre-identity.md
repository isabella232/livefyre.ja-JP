---
description: Livefyre IDをMicrosoft Live Identityと共に使用すると、ユーザーはFacebookログインを使用してサイト上のアプリを操作できます。
title: Livefyre Idで使用するMicrosoft Live Identityアプリケーションの作成
exl-id: 7702c956-ecb5-424a-9866-d6f73d4d4bc9
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Livefyre Identityと共に使用するMicrosoft Live Identityアプリケーションの作成{#create-a-microsoft-live-identity-app-for-use-with-livefyre-identity}

Livefyre IDをMicrosoft Live Identityと共に使用すると、ユーザーはFacebookログインを使用してサイト上のアプリを操作できます。

ユーザーがMicrosoft Live Idの資格情報を使用してログインできるようにするには、Livefyreに次のMicrosoft Live Identity情報が必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre Identityで使用するMicrosoft Live Identityアプリを作成するには：

1. [https://apps.dev.microsoft.com](https://apps.dev.microsoft.com/)でMicrosoft Liveアカウントを作成するか、Microsoft Liveアカウントにサインインします。
1. Livefyre IDで使用する新しいアプリを作成するか、既存のアプリを選択します。
1. **[!UICONTROL Add Platform]**&#x200B;をクリックし、プラットフォームの種類として「Web」を選択します。
1. **[!UICONTROL Allow Implicit Flow]**&#x200B;オプションがチェック済みであることを確認し、{network-name}ではなく、お使いのネットワーク名を使用して、リダイレクトURLを入力します。`https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/mslive_fyre`.
1. 新しいパスワードとキーのペアを生成して、秘密鍵を取得します。
1. **[!UICONTROL Livefyre Integration Settings Livefyre Identity Microsoft Live]**&#x200B;で、**[!UICONTROL Enable Microsoft Live Login]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。
1. Microsoft Live Client IDとMicrosoft Live Client Secretを入力します。
1. クリック **[!UICONTROL Save Settings]**.

完了すると、Microsoft Live Idのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID(Consumer key)とクライアントシークレット(Consumer secret)がリストされます。
