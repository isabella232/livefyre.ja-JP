---
description: ソーシャルログインを有効にするには、Studioを使用してLivefyre統合にソーシャルアプリの資格情報を追加し、ログインモーダルをカスタマイズします。
seo-description: ソーシャルログインを有効にするには、Studioを使用してLivefyre統合にソーシャルアプリの資格情報を追加し、ログインモーダルをカスタマイズします。
seo-title: Using Studio to Connect Your Social Apps to Your Livefyre Implementation
title: Studioを使用したSocialアプリケーションのLivefyre実装への接続
uuid: be14869c-e0df-48cd-a1f3-99eb953dd9ce
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Using Studio to Connect Your Social Apps to Your Livefyre Implementation{#using-studio-to-connect-your-social-apps-to-your-livefyre-implementation}

To enable a social login, use Studio to add your social apps’ credentials to your Livefyre integration, and customize the Login Modal.

## Customizing the Login Modal {#section_v4c_hv2_3z}

The Login Modal allows you to customize the information your users will see when logging into your apps. You can customize the modal window.

* **** Logo: Upload a logo for use in your login modals.
* **** Font Family: Select a font to match your branding.
* **** Brand Color: Enter a hex color to be used for specific text within the modal.
* **** 利用条件URL:会社の利用条件ページのURLを入力します。 このフィールドは、Livefyre idで使用する場合に必須です。

## Livefyre IDの変換 {#section_xxt_z52_3z}

Livefyre idでテキスト文字列の翻訳セットを作成および変更できます。

Livefyre idでの翻訳セットの使用について詳しくは、翻訳セットを参照してください。

Livefyre ID用にカスタマイズできる特定の文字列について詳しくは、Livefyre IDを参照してください。

## 電子メールでのログインを有効にする {#section_dlv_wzt_bbb}

ユーザーが自分の電子メールアドレスを使用して、サイト上のアプリにログインし、やり取りすることを許可します。

Livefyreネイティブアカウントを使用したログインを有効にするには：

1. Livefyre studioでに移 **[!UICONTROL Integration Settings]** 動します。
1. 切り替えを **[!UICONTROL Enable Login with Email]** に切り替えま **[!UICONTROL On]**&#x200B;す。

## Facebookアカウントを使用したログインの有効化 {#section_ph3_515_bbb}

FacebookアカウントをLivefyreに接続して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにします。

Facebookアカウントを使用したログインを有効にするには：

1. 切り替えを **[!UICONTROL Enable Login with Facebook]** に切り替えま **[!UICONTROL ON]**&#x200B;す。

1. Facebookアプリのおよびを追加し **[!UICONTROL App ID]** ます **[!UICONTROL App Secret]**。

   これらの値は、Facebook開発者ダッシュボードに表示され、https://developers.facebook.com/apps/から入手でき [ます](https://developers.facebook.com/apps/675503539257343/dashboard/)。

## Googleでのログインを有効にする {#section_fq3_kb5_bbb}

Google+アカウントをLivefyreに接続し、ユーザーがGoogle+ログインを使用してサイト上のアプリとやり取りできるようにします。

Google+アカウントを使用したログインを有効にするには：

1. 切り替えを **[!UICONTROL Enable Login with Google]** に切り替えま **[!UICONTROL ON]**&#x200B;す。

1. Googleアプリのおよびを追加し **[!UICONTROL Client ID]** ます **[!UICONTROL Client secret]**。

   これらの値は、Google Cloud Platformプロジェクトインターフェイスに表示され、https://console.cloud.google.com/から入手で [きます](https://console.cloud.google.com/apis/library)。 この情報を取得するには、に進み、 **[!UICONTROL API Manager > Credentials]**&#x200B;プロジェクト名をクリックします。

## Twitterアカウントを使用したログインの有効化 {#section_iyz_wb5_bbb}

TwitterアカウントをLivefyreに接続して、ユーザーがTwitterログインを使用してサイト上のアプリとやり取りできるようにします。

Twitterアカウントを使用したログインを有効にするには：

1. 切り替えを **[!UICONTROL Enable Login with Twitter]** に切り替えま **[!UICONTROL ON]**&#x200B;す。

1. Twitterアプリのおよびを追加し **[!UICONTROL Consumer Key (API Key)]** ます **[!UICONTROL Consumer Secret (API Secret)]**。

   これらの値は、Twitterアプリのページ(https://apps.twitter.com/から入手 **[!UICONTROL Keys and Access Tokens]** 可能)に一覧表示さ [れます](https://apps.twitter.com/)。

## Yahoo！を使用したログインの有効化 アカウント {#section_s1q_3c5_bbb}

Yahoo！を接続します。 ユーザーがYahoo! ログインして、サイト上のアプリを操作します。

Yahoo！を使用したログインを有効にするには account:

1. 切り替えを **[!UICONTROL Enable Login with Yahoo!]** に切り替えま **[!UICONTROL ON]**&#x200B;す。

1. Yahoo! アプリの」と「」 **[!UICONTROL Client ID]** が表示され **[!UICONTROL Client Secret]**&#x200B;ます。

   これらの値はYahoo! アプリの詳細ページ(developer.yahoo.com/appsから入手 [可能](https://developer.yahoo.com/apps))

## Microsoft liveアカウントを使用したログインの有効化 {#section_z42_4c5_bbb}

Microsoft Live IDアカウントをLivefyreに接続して、ユーザーがMicrosoft Live IDログインを使用してサイト上のアプリとやり取りできるようにします。

Microsoft Live IDアカウントを使用したログインを有効にするには：

1. で、切 **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > Microsoft Live]**&#x200B;り替えをに **[!UICONTROL Enable Microsoft Live Login]** 切り替えま **[!UICONTROL On]**&#x200B;す。

1. と入力し **[!UICONTROL Microsoft Live Client ID (Private Key)]** ます **[!UICONTROL Microsoft Live Client Secret (Password)]**。

1. Click **[!UICONTROL Save Settings]**.

   との値 **[!UICONTROL Microsoft Live Client ID (Private Key)]** は、Microsoft Live IDア **[!UICONTROL Microsoft Live Client Secret (Password)]** プリの詳細ページに一覧表示されます。

## SocialアプリをLivefyre IDに接続する {#section_on2_vc5_bbb}

ユーザーがサイト上のアプリでLivefyre ID実装を使用できるようにします。

1. アプリを作成.
1. ///に移 **[!UICONTROL Studio]** 動し **[!UICONTROL Settings]** ます **[!UICONTROL Integration Settings]****[!UICONTROL Livefyre Identity]**。

1. 作成したアプリに必要なアプリの資格情報を入力します。