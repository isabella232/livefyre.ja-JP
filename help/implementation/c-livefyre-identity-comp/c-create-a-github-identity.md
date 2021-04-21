---
description: Livefyre IDをGitHub IDと共に使用して、ユーザーがGitHubログインを使用してサイト上のアプリを操作できるようにすることができます。
title: Livefyre IDで使用するGitHub IDアプリを作成する
exl-id: f25ffd0e-ea4f-42ac-abfc-c02018421b85
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '182'
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
