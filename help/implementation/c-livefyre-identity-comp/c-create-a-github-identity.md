---
description: Livefyre IDをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-description: Livefyre IDをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-title: Livefyre IDで使用するGitHub IDアプリを作成する
title: Livefyre IDで使用するGitHub IDアプリを作成する
uuid: cf56164c-1521-4a42-89cb-39483764807e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# Livefyre Identity{#create-a-github-identity-app-for-use-with-livefyre-identity}で使用するGitHub IDアプリを作成する

Livefyre IDをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリを操作できるようにすることができます。

ユーザーがGitHub ID資格情報を使用してログインできるようにするには、Livefyreに次のGitHub ID情報が必要です。

* クライアントID（秘密鍵）
* クライアントシークレット（パスワード）

Livefyre Idで使用するGitHub IDアプリを作成するには：

1. [](https://github.com/settings/developers)でGitHubアカウントを作成するか、アカウントにサインインします。
1. Livefyre IDで使用する新規アプリを登録するか、既存のアプリを選択します。
1. フォームにすべての情報を入力します。 `{network-name}: {network-name}: https://identy.livefyre.com/{network-name}.fyre.co/api/v.1.0/public/profile/social/complete/github_fyre`の代わりに、お使いのネットワーク名を使用して&#x200B;**[!UICONTROL Authorization callback URL]**&#x200B;を入力します。

1. **[!UICONTROL Livefyre Integration Settings Livefyre Identity GitHub]**&#x200B;で、**[!UICONTROL Enable GitHub Login]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。

1. GitHubクライアントIDとGitHubクライアントシークレットを入力します。
1. クリック **[!UICONTROL Save Settings]**.

完了すると、GitHub Identityのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID(Consumer key)とクライアントシークレット(Consumer secret)がリストされます。
