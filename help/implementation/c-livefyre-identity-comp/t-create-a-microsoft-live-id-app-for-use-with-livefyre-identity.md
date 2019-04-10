---
description: Livefyre IDをMicrosoft Live IDと共に使用すると、ユーザーはFacebookログインを使用してサイト上のアプリをインタラクティブに操作できます。
seo-description: Livefyre IDをMicrosoft Live IDと共に使用すると、ユーザーはFacebookログインを使用してサイト上のアプリをインタラクティブに操作できます。
seo-title: Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成
solution: Experience Manager
title: Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成
uuid: 0c13e1bc-817f-43ed-85d5-09c9e95b6234
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyre IDで使用するMicrosoft Live Identityアプリケーションの作成{#create-a-microsoft-live-identity-app-for-use-with-livefyre-identity}

Livefyre IDをMicrosoft Live IDと共に使用すると、ユーザーはFacebookログインを使用してサイト上のアプリをインタラクティブに操作できます。

ユーザーがMicrosoft Live ID資格情報を使用してログインできるようにするには、Livefyreに次のMicrosoft Live Identity Informationが必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre IDで使用するMicrosoft Live Identityアプリケーションを作成するには:

1. Microsoft Liveアカウントにhttps://apps.dev.microsoft.comを [作成またはサインインします](https://apps.dev.microsoft.com/)
1. Livefyre IDで使用する既存のアプリケーションを作成するか、既存のアプリケーションを選択します。
1. をクリック **[!UICONTROL Add Platform]**し、プラットフォームタイプとして"Web"を選択します。
1. **[!UICONTROL Allow Implicit Flow]** このオプションがチェックされていることを確認し、"{network- name}"ではなくネットワーク名を使用してリダイレクトURLを入力します。 `https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/mslive_fyre`を参照してください。
1. 秘密鍵を取得するための新しいパスワード/キーペアを生成します。
1. で **[!UICONTROL Livefyre Integration Settings Livefyre Identity Microsoft Live]****[!UICONTROL Enable Microsoft Live Login]** 、切り替えをに切り替え **[!UICONTROL On]**ます。
1. Microsoft Live Client IDとMicrosoft Live Clientシークレットを入力します。
1. **[!UICONTROL Save Settings]**をクリックします。

Microsoft Live Identityのアプリケーションの詳細ページには、Studioの統合設定ページで使用するアプリケーションのクライアントID（Consumer Key）およびクライアントシークレット（Consumer Secret）が表示されます。
