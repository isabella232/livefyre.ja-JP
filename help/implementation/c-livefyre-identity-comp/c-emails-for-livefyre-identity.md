---
description: 'null'
seo-description: 'null'
seo-title: Livefyre IDの電子メール
solution: Experience Manager
title: Livefyre IDの電子メール
uuid: 4e807803-687e-4df0-94d1- b18a48d024e8
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Livefyre IDの電子メール{#emails-for-livefyre-identity}

Livefyre Identityが次の電子メールを送信します。

* [パスワードリセット電子メール](#c_emails_for_livefyre_identity/section_nd1_whs_p1b)
* [Verification Email](#c_emails_for_livefyre_identity/section_ak5_xhs_p1b)
   * [ユーザーの電子メール検証を送信](#c_emails_for_livefyre_identity/section_vyv_yhs_p1b)

* [お知らせメール](#c_emails_for_livefyre_identity/section_z2v_zhs_p1b)
   * [お知らせメールのユーザへの送信](#c_emails_for_livefyre_identity/section_kjp_c3s_p1b)

すべてのLivefyre ID電子メールのルック&amp;フィールを **[!UICONTROL Integration Settings > Email Notifications.]** 

## パスワードリセット電子メール {#section_nd1_whs_p1b}

ユーザーがパスワードをリセットしようとすると、パスワードリセット電子メールが自動的に送信されます。

パスワードリセットの電子メールは次のようになります。

**件名:** パスワードをリセット

**Body:**

Yahhere *&lt; username&gt;*，

&lt; network name&gt;に *プロファイルのパスワードを変更するリクエストがあり*ました。

If you requested this, please click the following link to choose a new password: *&lt;password reset URL&gt;*.

*&lt;ユーザー名&gt;*、 *&lt;ネットワーク名&gt;*、 *&lt;パスワードリセットURL&gt;* は、サイト訪問者とネットワークに基づいて動的に生成されます。

## Verification Email {#section_ak5_xhs_p1b}

ユーザーの電子メールアドレスを確認する電子メールを送信できます。電子メールを送信するには、統合設定/Livefyre IDの **オプションをオンにする必要**があります。

確認電子メールは次のようになります。

**件名:** 電子メールの検証

**Body:**

Hello *&lt; username&gt;*，

アカウントを確認するには、次のリンクをクリックしてください（またはブラウザに貼り付けてください）。 *&lt;検証URL&gt;*.

このリンクは24時間で有効期限が切れます。

ありがとうございました。

*&lt;顧客名&gt;* チーム

*&lt;ユーザー名&gt;*、 *&lt;ネットワークネーム&gt;*、 *&lt;検証URL&gt;* は、サイト訪問者とネットワークに基づいて動的に生成されます。

## ユーザーへの電子メールの検証の送信 {#section_vyv_yhs_p1b}

ユーザーに電子メールを送信して、アカウントへのサインアップに使用する電子メールアドレスを確認できます。確認電子メールを送信するには:

1. Studioで、ギアアイコンをクリックしてネットワーク設定を変更します。
1. **統合設定/Livefyre IDをクリックします。**

1. **「ログインタイプ**」に移動します。
1. 「 **電子メールの検証** を要求」をクリックして、アカウントへのサインアップに使用する電子メールアドレスを検証するユーザーに電子メールを送信します。
1. **ネットワーク電子メール** に移動して、電子メールの **ロゴ、アドレス（**電子メールからの**電子メールアドレス**）として使用する電子メールアドレス、電子メールアドレス（**電子メール表示名**）に使用する表示名を設定します。

## お知らせメール {#section_z2v_zhs_p1b}

ユーザーにお知らせメールを送信できます。お知らせメールを送信するには **、統合設定** / **Livefyre IDのオプションをオンにする必要**があります。

お知らせメールは次のようになります。

**件名:** &lt;顧客名&gt;へ *ようこそ*

**Body:**

Hello *&lt; username&gt;*，

&lt; customer name&gt;に *アカウントが作成され*ました。

このアカウントは *、&lt;参照URL&gt;* のIPアドレス *&lt; IPアドレス&gt;から作成されまし*た。

これを行った場合、この電子メールを安全に無視できます。

これを行わなかった場合は、 `support@livefyre.com`

感謝する

*「顧客名」* チーム

*&quot;Username&quot;, &quot;customer name&quot;, &quot;referral URL&quot;,* and &quot;IP Address&quot; are all dynamically generated based on the site visitor and your network.

## ユーザーへのお知らせメールの送信 {#section_kjp_c3s_p1b}

ユーザーがアカウントにサインアップした後、ユーザーにお知らせメールを送信できます。Studioは、検証電子メールを設定した場合、検証電子メールの送信後にこの電子メールを送信します。お知らせメールを送信するには:

1. Studioで、ギアアイコンをクリックしてネットワーク設定を変更します。
1. クリック **[!UICONTROL Integration Settings > Livefyre Identity]** 

1. 先に移動 **[!UICONTROL Email Settings]** します。

1. をクリック **[!UICONTROL Send Welcome Emails To New Users]** して電子メールの送信を有効にします。
1. 電子メール **[!UICONTROL Network Email]** の *ロゴ、電子メールアドレス*として使用する電子メールアドレス、**電子メール**アドレス（**電子メール表示名**）に使用する表示名の設定に移動します。
