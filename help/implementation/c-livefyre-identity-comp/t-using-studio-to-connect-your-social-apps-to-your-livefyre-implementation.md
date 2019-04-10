---
description: ソーシャルログインを有効にするには、Studioを使用して、Socialアプリの資格情報をLivefyre統合に追加し、ログインモーダルをカスタマイズします。
seo-description: ソーシャルログインを有効にするには、Studioを使用して、Socialアプリの資格情報をLivefyre統合に追加し、ログインモーダルをカスタマイズします。
seo-title: Studioを使用したソーシャルアプリのLivefyre実装への接続
title: Studioを使用したソーシャルアプリのLivefyre実装への接続
uuid: be14869c- e0df-48cd- a1f3-99eb953dd9ce
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Studioを使用したソーシャルアプリのLivefyre実装への接続{#using-studio-to-connect-your-social-apps-to-your-livefyre-implementation}

ソーシャルログインを有効にするには、Studioを使用して、Socialアプリの資格情報をLivefyre統合に追加し、ログインモーダルをカスタマイズします。

## ログインモーダルのカスタマイズ {#section_v4c_hv2_3z}

ログインモーダルを使用すると、ユーザーがアプリにログインする際に表示する情報をカスタマイズできます。モーダルウィンドウをカスタマイズできます。

* **ロゴ:** ログインモデリングで使用するロゴをアップロードします。
* **フォントファミリー:** ブランディングに一致するフォントを選択します。
* **ブランドカラー:** モーダル内の特定のテキストに使用する16進数のカラーを入力します。
* **利用条件URL:** 会社の取引条件ページのURLを入力します。このフィールドはLivefyre IDで使用する必要があります。

## Livefyre IDの変換 {#section_xxt_z52_3z}

Livefyre IDのテキスト文字列の変換セットを作成および変更できます。

Livefyre IDによる翻訳セットの使用について詳しくは、変換セットを参照してください。

Livefyre ID用にカスタマイズできる特定の文字列について詳しくは、Livefyre Identityを参照してください。

## 電子メールでログインを有効にする {#section_dlv_wzt_bbb}

ユーザーが自分の電子メールアドレスを使用して、サイト上のアプリケーションにログインし、操作することができます。

Livefyreネイティブアカウントを使用してログインを有効にするには:

1. Livefyre Studio **[!UICONTROL Integration Settings]** に移動します。
1. 切り替えを **[!UICONTROL Enable Login with Email]** に切り替え **[!UICONTROL On]**ます。

## Facebookアカウントを使用したログインの有効化 {#section_ph3_515_bbb}

FacebookアカウントをLivefyreに接続して、ユーザーがFacebookログインを使用してサイト上のアプリとやり取りできるようにします。

Facebookアカウントを使用してログインを有効にするには:

1. 切り替えを **[!UICONTROL Enable Login with Facebook]** に切り替え **[!UICONTROL ON]**ます。

1. Facebookアプリ **[!UICONTROL App ID]** を追加 **[!UICONTROL App Secret]**します。

   これらの値は、https://developers.facebook.com/apps/から [利用可能なアプリ用のFacebook開発者ダッシュボードに表示](https://developers.facebook.com/apps/675503539257343/dashboard/)されます。

## Googleでログインを有効にする {#section_fq3_kb5_bbb}

Google+アカウントをLivefyreに接続して、ユーザーが自社のGoogle+ログインを使用してサイト上のアプリとやり取りできるようにします。

Google+アカウントを使用してログインを有効にするには:

1. 切り替えを **[!UICONTROL Enable Login with Google]** に切り替え **[!UICONTROL ON]**ます。

1. Googleアプリ **[!UICONTROL Client ID]** を追加 **[!UICONTROL Client secret]**します。

   これらの値は、https://console.cloud.google.com/から [利用可能な、Google Cloudプラットフォームのプロジェクトインターフェイスに一覧](https://console.cloud.google.com/apis/library)表示されます。この情報を取得するには、先 **[!UICONTROL API Manager > Credentials]**に移動してプロジェクト名をクリックします。

## Twitterアカウントを使用したログインの有効化 {#section_iyz_wb5_bbb}

TwitterアカウントをLivefyreに接続して、ユーザーがサイト上のアプリとのやりとりにTwitterログインを使用できるようにします。

Twitterアカウントを使用してログインを有効にするには:

1. 切り替えを **[!UICONTROL Enable Login with Twitter]** に切り替え **[!UICONTROL ON]**ます。

1. Twitterアプリ **[!UICONTROL Consumer Key (API Key)]** を追加 **[!UICONTROL Consumer Secret (API Secret)]**します。

   これらの値は、https://apps.twitter.com/から利用可能なTwitterアプリ **[!UICONTROL Keys and Access Tokens]**[のページに表示](https://apps.twitter.com/)されます。

## Yahoo!を使用してログインを有効にするアカウント {#section_s1q_3c5_bbb}

Yahoo!に接続!アカウントをLivefyreに移行し、ユーザがYahoo!を使用できるようにするログインを参照してください。

Yahoo!を使用してログインを有効にするにはアカウント:

1. 切り替えを **[!UICONTROL Enable Login with Yahoo!]** に切り替え **[!UICONTROL ON]**ます。

1. Yahoo!を追加します。app’s **[!UICONTROL Client ID]** and **[!UICONTROL Client Secret]**.

   これらの値はYahoo!に一覧表示されます。アプリの詳細ページ [](https://developer.yahoo.com/apps)を参照してください。

## Microsoft Liveアカウントを使用したログインの有効化 {#section_z42_4c5_bbb}

Microsoft Live IDアカウントをLivefyreに接続して、ユーザーがMicrosoft Live IDログインを使用してサイト上のアプリケーションとやり取りできるようにします。

Microsoft Live IDアカウントを使用してログインを有効にするには:

1. で **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > Microsoft Live]****[!UICONTROL Enable Microsoft Live Login]** 、切り替えをに切り替え **[!UICONTROL On]**ます。

1. および **[!UICONTROL Microsoft Live Client ID (Private Key)]** を入力 **[!UICONTROL Microsoft Live Client Secret (Password)]**します。

1. **[!UICONTROL Save Settings]**をクリックします。

   および **[!UICONTROL Microsoft Live Client ID (Private Key)]****[!UICONTROL Microsoft Live Client Secret (Password)]** 値は、Microsoft Live IDアプリケーションの詳細ページに一覧表示されます。

## SocialアプリのLivefyre IDへの接続 {#section_on2_vc5_bbb}

サイト上のアプリにLivefyre Identity実装を使用できるようにします。

1. アプリの作成を参照してください。
1. **[!UICONTROL Studio]** > **[!UICONTROL Settings]** > **[!UICONTROL Integration Settings]**>に移動 **[!UICONTROL Livefyre Identity]**します。

1. 作成したアプリに必要なアプリの資格情報を入力します。