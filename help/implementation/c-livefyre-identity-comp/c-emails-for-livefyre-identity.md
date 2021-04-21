---
title: Livefyre ID用電子メール
description: Livefyre ID用電子メール
exl-id: c8127eef-8fb8-4703-ba34-ef12453f1754
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---

# Livefyre ID用の電子メール{#emails-for-livefyre-identity}

Livefyre Identityから次の電子メールが送信されます。

* [パスワードリセット用電子メール](#c_emails_for_livefyre_identity/section_nd1_whs_p1b)
* [検証用電子メール](#c_emails_for_livefyre_identity/section_ak5_xhs_p1b)
   * [ユーザーに電子メールの検証を送信](#c_emails_for_livefyre_identity/section_vyv_yhs_p1b)

* [お知らせメール](#c_emails_for_livefyre_identity/section_z2v_zhs_p1b)
   * [ユーザーにお知らせメールを送信](#c_emails_for_livefyre_identity/section_kjp_c3s_p1b)

**[!UICONTROL Integration Settings > Email Notifications.]**&#x200B;内のすべてのLivefyre ID電子メールのルック&amp;フィールをカスタマイズできます

## パスワードリセット用電子メール{#section_nd1_whs_p1b}

Livefyreは、ユーザーがパスワードのリセットを試みると、パスワードリセット用の電子メールを自動的に送信します。

パスワードのリセット用の電子メールは次のようになります。

**Subject:** Reset Password

**本文：**

*&lt;ユーザ名>*、

*&lt;network name>*&#x200B;でプロファイルのパスワードを変更する要求が発生しました。

これを要求した場合は、次のリンクをクリックして新しいパスワードを選択してください。*&lt;パスワードリセットURL>*。

*&lt;username>*、 *&lt;network name=&quot;&quot;>* *&lt;password reset=&quot;&quot; URL=&quot;&quot;>* およびはすべて、サイトの訪問者とネットワークに基づいて動的に生成されます。

## 検証用電子メール{#section_ak5_xhs_p1b}

ユーザーの電子メールアドレスを確認する電子メールを送信できます。 検証用の電子メールを送信するには、**統合設定/Livefyre ID**&#x200B;でこのオプションを有効にする必要があります。

検証用の電子メールは次のようになります。

**件名：** 電子メールの検証

**本文：**

こんにちは&#x200B;*&lt;ユーザ名>*

次のリンクをクリック（またはブラウザに貼り付け）してアカウントを確認してください。*&lt;検証URL>*.

このリンクは24時間で有効期限が切れます。

ありがとう

*&lt;顧客名>*&#x200B;チーム

*&lt;username>*、 *&lt;network name=&quot;&quot;>* *&lt;verification URL=&quot;&quot;>* およびはすべて、サイトの訪問者とネットワークに基づいて動的に生成されます。

## ユーザーへの電子メールの検証{#section_vyv_yhs_p1b}

ユーザーに電子メールを送信して、アカウントのサインアップに使用する電子メールアドレスを確認できます。 検証用の電子メールを送信するには：

1. Studioで、歯車アイコンをクリックして、ネットワーク設定を変更します。
1. **統合設定/Livefyre IDをクリックします。**

1. **ログインタイプ**&#x200B;に移動します。
1. 「**電子メールの検証を要求**」をクリックして、アカウントのサインアップに使用する電子メールアドレスを確認する電子メールをユーザーに送信します。
1. **Network Email**&#x200B;に移動して、電子メール&#x200B;**の**&#x200B;ロゴ、送信元アドレス（**電子メール送信元**）、送信元電子メールアドレス（**電子メール表示名**）を設定します。

## お知らせメール {#section_z2v_zhs_p1b}

ユーザーにご案内の電子メールを送信できます。 お知らせメールを送信するには、**統合設定**/**Livefyre ID**&#x200B;でオプションを有効にする必要があります。

ご案内の電子メールは次のようになります。

**件名：** ようこそ  *&lt;customer name=&quot;&quot;>*

**本文：**

こんにちは&#x200B;*&lt;ユーザ名>*

*&lt;顧客名>*&#x200B;にアカウントが作成されました。

このアカウントは、IPアドレス&#x200B;*&lt;IPアドレス>*&#x200B;から&#x200B;*&lt;リファラルURL>*&#x200B;に作成されました。

この場合、この電子メールを無視しても問題ありません。

これを行わなかった場合は、`support@livefyre.com`にお問い合わせください。

ありがとう

*&quot;顧客名&quot;*&#x200B;チーム

*「ユーザー名」、「顧客名」、「リファラルURL」* および「IPアドレス」は、すべてサイトの訪問者とネットワークに基づいて動的に生成されます。

## ユーザーへお知らせメールの送信{#section_kjp_c3s_p1b}

ユーザーがアカウントにサインアップした後、そのユーザーにご案内の電子メールを送信できます。 検証用の電子メールを設定した場合、Studioは、検証用の電子メールを送信した後にこの電子メールを送信します。 お知らせメールを送信するには：

1. Studioで、歯車アイコンをクリックして、ネットワーク設定を変更します。
1. クリック **[!UICONTROL Integration Settings > Livefyre Identity]**

1. **[!UICONTROL Email Settings]**&#x200B;に移動します。

1. **[!UICONTROL Send Welcome Emails To New Users]**&#x200B;をクリックして電子メールの送信を有効にします。
1. **[!UICONTROL Network Email]**&#x200B;に移動して、電子メール&#x200B;*の*&#x200B;ロゴ、送信元アドレス（**電子メール送信者**）として使用する電子メールアドレス、送信元電子メールアドレス（**電子メール表示名**）を設定します。
