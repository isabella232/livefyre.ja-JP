---
description: Livefyre IdentityをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-description: Livefyre IdentityをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-title: Livefyre IDで使用するGitHub IDアプリを作成する
title: Livefyre IDで使用するGitHub IDアプリを作成する
uuid: cf56164c-1521-4a42-89cb-39483764807e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するGitHub IDアプリを作成する{#create-a-github-identity-app-for-use-with-livefyre-identity}

Livefyre IdentityをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリとやり取りできるようにすることができます。

ユーザーがGitHub ID資格情報を使用してログインできるようにするには、Livefyreに次のGitHub ID情報が必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre idで使用するGitHub IDアプリを作成するには：

1. でGitHubアカウントを作成するか、サインインしま [](https://github.com/settings/developers)す。
1. Livefyre IDで使用する新しいアプリを登録するか、既存のアプリを選択します。
1. フォームにすべての情報を入力します。 の代わりに、ネ **[!UICONTROL Authorization callback URL]**&#x200B;ットワーク名を使用して、を入力しま `{network-name}: {network-name}: https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/github_fyre`す。

1. で、切 **[!UICONTROL Livefyre Integration Settings Livefyre Identity GitHub]**&#x200B;り替えをに **[!UICONTROL Enable GitHub Login]** 切り替えま **[!UICONTROL On]**&#x200B;す。

1. GitHubクライアントIDとGitHubクライアントシークレットを入力します。
1. Click **[!UICONTROL Save Settings]**.

完了すると、GitHub IDのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID（コンシューマーキー）とクライアントシークレット（コンシューマーシークレット）が表示されます。
