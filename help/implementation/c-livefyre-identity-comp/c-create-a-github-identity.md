---
description: GitHub IDを使用してLivefyre IDを使用すると、ユーザーはGitHubログインを使用してサイトのアプリを操作できます。
seo-description: GitHub IDを使用してLivefyre IDを使用すると、ユーザーはGitHubログインを使用してサイトのアプリを操作できます。
seo-title: Livefyre IDで使用するGitHub IDアプリケーションの作成
title: Livefyre IDで使用するGitHub IDアプリケーションの作成
uuid: cf56164c-1521-4a42-89cb-39483764807e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するGitHub IDアプリケーションの作成{#create-a-github-identity-app-for-use-with-livefyre-identity}

GitHub IDを使用してLivefyre IDを使用すると、ユーザーはGitHubログインを使用してサイトのアプリを操作できます。

ユーザーがGitHub ID資格情報を使用してログインできるようにするには、Livefyreに以下のGitHub ID情報が必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre IDで使用するGitHub IDアプリケーションを作成するには:

1. GitHubアカウントに作成またはサインイン [](https://github.com/settings/developers)します。
1. 新しいアプリケーションを登録するか、Livefyre IDで使用する既存のアプリケーションを選択します。
1. フォームにすべての情報を入力します。ではなく、ネットワーク名を使用して、を **[!UICONTROL Authorization callback URL]**入力してください `{network-name}: {network-name}: https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/github_fyre`。

1. で **[!UICONTROL Livefyre Integration Settings Livefyre Identity GitHub]****[!UICONTROL Enable GitHub Login]** 、切り替えをに切り替え **[!UICONTROL On]**ます。

1. GitHubクライアントIDとGitHubクライアントシークレットを入力します。
1. **[!UICONTROL Save Settings]**をクリックします。

完了すると、GitHub IDのアプリケーションの詳細ページに、Studioの統合設定ページで使用するアプリケーションのクライアントID（Consumer Key）とクライアントシークレット（Consumer Secret）が一覧表示されます。
