---
description: ソーシャルログインを有効にするには、Studioを使用してLivefyre統合にソーシャルアプリケーションの資格情報を追加し、ログインモーダルをカスタマイズします。
title: Studioを使用したSocialアプリケーションのLivefyre実装への接続
exl-id: 2ccb9737-8c59-4c1d-93d3-61f913b3cdd6
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 1%

---

# Studioを使用したLivefyre実装へのソーシャルアプリケーションの接続{#using-studio-to-connect-your-social-apps-to-your-livefyre-implementation}

ソーシャルログインを有効にするには、Studioを使用してLivefyre統合にソーシャルアプリケーションの資格情報を追加し、ログインモーダルをカスタマイズします。

## ログインモーダルのカスタマイズ{#section_v4c_hv2_3z}

ログインモーダルを使用すると、ユーザーがアプリにログインする際に表示される情報をカスタマイズできます。 モーダルウィンドウはカスタマイズできます。

* **ロゴ：ログインモデルで使用するロゴを** アップロードします。
* **フォントファミリー：ブランドに一致するフォントを** 選択します。
* **ブランド色：モーダル内の特定のテキストに使用する16進数の色を** 入力します。
* **利用条件URL:会社の利用条件ページのURLを** 入力します。このフィールドは、Livefyre Idで使用する場合に必須です。

## Livefyre IDの変換{#section_xxt_z52_3z}

Livefyre ID内のテキスト文字列の翻訳セットを作成および変更できます。

Livefyre Idでの翻訳セットの使用について詳しくは、翻訳セットを参照してください。

Livefyre ID用にカスタマイズできる特定の文字列について詳しくは、Livefyre IDを参照してください。

## 電子メールでのログインを有効にする{#section_dlv_wzt_bbb}

ユーザーが自分の電子メールアドレスを使用してログインし、サイト上のアプリとやり取りできるようにします。

Livefyreネイティブアカウントを使用したログインを有効にするには：

1. Livefyre Studioの&#x200B;**[!UICONTROL Integration Settings]**&#x200B;に移動します。
1. **[!UICONTROL Enable Login with Email]**&#x200B;トグルを&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。

## facebookアカウントを使用したログインを有効にする{#section_ph3_515_bbb}

facebookアカウントをLivefyreに接続して、ユーザーがFacebookログインを使用してサイト上のアプリとやり取りできるようにします。

facebookアカウントを使用したログインを有効にするには：

1. **[!UICONTROL Enable Login with Facebook]**&#x200B;トグルを&#x200B;**[!UICONTROL ON]**&#x200B;に切り替えます。

1. 追加Facebookアプリの&#x200B;**[!UICONTROL App ID]**&#x200B;と&#x200B;**[!UICONTROL App Secret]**。

   これらの値は、[https://developers.facebook.com/apps/](https://developers.facebook.com/apps/675503539257343/dashboard/)から入手できる、アプリのFacebook開発者ダッシュボードに一覧表示されます。

## Googleでのログインを有効にする{#section_fq3_kb5_bbb}

Google+アカウントをLivefyreに接続して、ユーザーがGoogle+ログインを使用してサイト上のアプリとやり取りできるようにします。

Google+アカウントを使用したログインを有効にするには：

1. **[!UICONTROL Enable Login with Google]**&#x200B;トグルを&#x200B;**[!UICONTROL ON]**&#x200B;に切り替えます。

1. 追加Googleアプリの&#x200B;**[!UICONTROL Client ID]**&#x200B;と&#x200B;**[!UICONTROL Client secret]**。

   これらの値は、Google Cloud Platformプロジェクトインターフェイスに一覧表示されます。このインターフェイスは、[https://console.cloud.google.com/](https://console.cloud.google.com/apis/library)から入手できます。 この情報を取得するには、**[!UICONTROL API Manager > Credentials]**&#x200B;に移動し、プロジェクト名をクリックします。

## twitterアカウントを使用したログインの有効化{#section_iyz_wb5_bbb}

twitterアカウントをLivefyreに接続して、ユーザーがTwitterログインを使用してサイト上のアプリとやり取りできるようにします。

twitterアカウントを使用したログインを有効にするには：

1. **[!UICONTROL Enable Login with Twitter]**&#x200B;トグルを&#x200B;**[!UICONTROL ON]**&#x200B;に切り替えます。

1. 追加Twitterアプリの&#x200B;**[!UICONTROL Consumer Key (API Key)]**&#x200B;と&#x200B;**[!UICONTROL Consumer Secret (API Secret)]**。

   これらの値は、Twitterアプリの&#x200B;**[!UICONTROL Keys and Access Tokens]**&#x200B;ページに一覧表示され、[https://apps.twitter.com/](https://apps.twitter.com/)から入手できます。

## Yahoo！を使用したログインを有効にする アカウント {#section_s1q_3c5_bbb}

Yahoo! アカウントをLivefyreにアップロードし、ユーザーがYahoo! サイトのアプリとやり取りするためのログイン。

Yahoo! account:

1. **[!UICONTROL Enable Login with Yahoo!]**&#x200B;トグルを&#x200B;**[!UICONTROL ON]**&#x200B;に切り替えます。

1. 追加Yahoo! アプリの&#x200B;**[!UICONTROL Client ID]**&#x200B;と&#x200B;**[!UICONTROL Client Secret]**。

   これらの値はYahoo! アプリの詳細ページ([developer.yahoo.com/apps](https://developer.yahoo.com/apps)から入手可能)

## Microsoft Liveアカウントを使用したログインを有効にする{#section_z42_4c5_bbb}

Microsoft Live IDアカウントをLivefyreに接続すると、ユーザーはMicrosoft Live IDログインを使用してサイト上のアプリとやり取りできます。

Microsoft Live IDアカウントを使用してログインを有効にするには：

1. **[!UICONTROL Livefyre > Integration Settings > Livefyre Identity > Microsoft Live]**&#x200B;で、**[!UICONTROL Enable Microsoft Live Login]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に切り替えます。

1. **[!UICONTROL Microsoft Live Client ID (Private Key)]**&#x200B;と&#x200B;**[!UICONTROL Microsoft Live Client Secret (Password)]**&#x200B;を入力します。

1. クリック **[!UICONTROL Save Settings]**.

   **[!UICONTROL Microsoft Live Client ID (Private Key)]**&#x200B;と&#x200B;**[!UICONTROL Microsoft Live Client Secret (Password)]**&#x200B;の値は、Microsoft Live IDアプリの詳細ページに一覧表示されます。

## ソーシャルアプリをLivefyre IDに接続{#section_on2_vc5_bbb}

ユーザーがサイト上のアプリに対してLivefyre ID実装を使用できるようにします。

1. アプリを作成.
1. **[!UICONTROL Studio]** > **[!UICONTROL Settings]** > **[!UICONTROL Integration Settings]** **[!UICONTROL Livefyre Identity]**&#x200B;に移動します。

1. 作成したアプリに必要なアプリの資格情報を入力します。
