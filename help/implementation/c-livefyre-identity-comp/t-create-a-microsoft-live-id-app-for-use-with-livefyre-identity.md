---
description: Livefyre IDをMicrosoft Live Identityと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-description: Livefyre IDをMicrosoft Live Identityと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-title: Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成
solution: Experience Manager
title: Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成
uuid: 0c13e1bc-817f-43ed-85d5-09c9e95b6234
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成{#create-a-microsoft-live-identity-app-for-use-with-livefyre-identity}

Livefyre IDをMicrosoft Live Identityと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。

ユーザーがMicrosoft Live idの資格情報を使用してログインできるようにするには、Livefyreに次のMicrosoft Live id情報が必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre idで使用するMicrosoft Live Identityアプリを作成するには：

1. https://apps.dev.microsoft.comでMicrosoft liveアカウントを作成するか、Microsoft liveアカウントにサインインし [ます](https://apps.dev.microsoft.com/)
1. Livefyre IDで使用する新しいアプリを作成するか、既存のアプリを選択します。
1. をクリック **[!UICONTROL Add Platform]**&#x200B;し、プラットフォームのタイプとして「Web」を選択します。
1. このオプションがオ **[!UICONTROL Allow Implicit Flow]** ンになっていることを確認し、{network-name}ではなく、ネットワーク名を使用してリダイレクトURLを入力します。 `https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/mslive_fyre`.
1. 新しいパスワードとキーのペアを生成して、秘密鍵を取得します。
1. で、切 **[!UICONTROL Livefyre Integration Settings Livefyre Identity Microsoft Live]**&#x200B;り替えをに **[!UICONTROL Enable Microsoft Live Login]** 切り替えま **[!UICONTROL On]**&#x200B;す。
1. Microsoft Live Client IDとMicrosoft Live Client Secretを入力します。
1. Click **[!UICONTROL Save Settings]**.

完了すると、Microsoft Live Identityのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID（コンシューマーキー）とクライアントシークレット（コンシューマーシークレット）が表示されます。
