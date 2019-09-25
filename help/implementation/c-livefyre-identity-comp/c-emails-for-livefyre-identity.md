---
description: 'null'
seo-description: 'null'
seo-title: Livefyre ID用電子メール
solution: Experience Manager
title: Livefyre ID用電子メール
uuid: 4e807803-687e-4df0-94d1-b18a48d024e8
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Livefyre ID用電子メール{#emails-for-livefyre-identity}

Livefyre Identityは次の電子メールを送信します。

* [パスワードリセット電子メール](#c_emails_for_livefyre_identity/section_nd1_whs_p1b)
* [検証用電子メール](#c_emails_for_livefyre_identity/section_ak5_xhs_p1b)
   * [ユーザーに電子メールの検証を送信](#c_emails_for_livefyre_identity/section_vyv_yhs_p1b)

* [お知らせメール](#c_emails_for_livefyre_identity/section_z2v_zhs_p1b)
   * [ユーザーへのお知らせメールの送信](#c_emails_for_livefyre_identity/section_kjp_c3s_p1b)

Livefyre ID電子メールの外観は、 **[!UICONTROL Integration Settings > Email Notifications.]**

## パスワードリセット電子メール {#section_nd1_whs_p1b}

Livefyreは、ユーザーがパスワードをリセットしようとすると、パスワードリセット用の電子メールを自動的に送信します。

パスワードのリセット用の電子メールは次のようになります。

**** 件名：パスワードのリセット

**本文：**

&lt;ユーザ *名&gt;*、

&lt;network name&gt;で、プロファイルのパスワードを変更する要求が *ありました*。

これを要求した場合は、次のリンクをクリックして新しいパスワードを選択してください。 *&lt;パスワードのリセットURL&gt;*。

*&lt;Username&gt;*、&lt;network name&gt; *、*** &lt;password reset URL&gt;は、すべてサイト訪問者とネットワークに基づいて動的に生成されます。

## 検証用電子メール {#section_ak5_xhs_p1b}

ユーザーの電子メールアドレスを確認する電子メールを送信できます。 検証電子メールを送信するには、統合設定/Livefyre IDでこのオプシ **ョンを有効にする必要があります**。

検証用の電子メールは次のようになります。

**** 件名：電子メールの検証

**本文：**

こんにちは、&lt; *ユーザー名&gt;*、

次のリンクをクリックして（またはブラウザに貼り付けて）、アカウントを確認してください。 *&lt;検証URL&gt;*.

このリンクは24時間で有効期限が切れます。

ありがとう

&lt;顧 *客名&gt;チーム*

*&lt;Username&gt;*、&lt;network name&gt; *、*** &lt;verification URL&gt;はすべて、サイトの訪問者とネットワークに基づいて動的に生成されます。

## ユーザーへの電子メールの確認 {#section_vyv_yhs_p1b}

ユーザーに電子メールを送信して、アカウントのサインアップに使用する電子メールアドレスを確認できます。 検証用電子メールを送信するには：

1. Studioで、歯車アイコンをクリックして、ネットワーク設定を変更します。
1. 統合設 **定/Livefyre IDをクリックします。**

1. 「ログインタ **イプ」に移動しま**&#x200B;す。
1. 「電子メ **ールの確認が必要」をクリックして** 、アカウントのサインアップに使用した電子メールアドレスを確認する電子メールをユーザーに送信します。
1. 「 **Network Email** 」に移動して、「 **Email**」のロゴ、「From address」(「Email From **」)、「Email address」(「****** Email Display Name Name」)の表示名を「Email」（電子メール表示名）に設定します。

## お知らせメール {#section_z2v_zhs_p1b}

ユーザーにご案内の電子メールを送信できます。 お知らせメールを送信するには、統合設定/ **Livefyre IDのオプションをオンにする必要** があります ****。

ご案内の電子メールは次のようになります。

**** 件名：&lt;お客様 *名&gt;へようこそ*

**本文：**

こんにちは、&lt; *ユーザー名&gt;*、

&lt;顧客名&gt;様のアカウントが作 *成されました*。

このアカウントはIPアドレス&lt;IPア *ドレス&gt;から* &lt;リファラルURL&gt; *に作成されました*。

これを行うと、この電子メールを無視しても問題ありません。

これを行わなかった場合は、 `support@livefyre.com`

ありがとう

「 *顧客名」チーム*

*「ユーザー名」、「顧客名」、「リファラルURL」* 、「IPアドレス」はすべて、サイト訪問者とネットワークに基づいて動的に生成されます。

## ユーザーへのお知らせメールの送信 {#section_kjp_c3s_p1b}

ユーザーがアカウントにサインアップした後で、そのユーザーにご案内の電子メールを送信できます。 検証用電子メールを設定した場合、Studioは、検証用電子メールを送信した後でこの電子メールを送信します。 お知らせメールを送信するには：

1. Studioで、歯車アイコンをクリックして、ネットワーク設定を変更します。
1. Click **[!UICONTROL Integration Settings > Livefyre Identity]**

1. に移動しま **[!UICONTROL Email Settings]**&#x200B;す。

1. 電子メール **[!UICONTROL Send Welcome Emails To New Users]** の送信を有効にする場合にクリックします。
1. 電子メー **[!UICONTROL Network Email]** ルのロゴ、送信者アドレスとして使用する電子メールアドレス( *Email From*)、送信元電子メールアドレスに使用する表示名(**Email Display Name******)を設定します。
