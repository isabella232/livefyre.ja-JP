---
description: FacebookでLivefyre IDを使用すると、ユーザーはFacebookログインを使用してサイト上のアプリとやり取りできます。
seo-description: FacebookでLivefyre IDを使用すると、ユーザーはFacebookログインを使用してサイト上のアプリとやり取りできます。
seo-title: Livefyre IDで使用するFacebookアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するFacebookアプリの作成
uuid: a7f7be4e-8986-4e79-831a-0bb0ae555599
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するFacebookアプリの作成{#create-a-facebook-app-for-use-with-livefyre-identity}

FacebookでLivefyre IDを使用すると、ユーザーはFacebookログインを使用してサイト上のアプリとやり取りできます。

ユーザーがFacebook資格情報を使用してログインできるようにするには、Livefyreには以下のFacebookアプリの情報が必要です。

* アプリID
* アプリシークレット

Livefyre IDで使用するFacebookアプリを作成するには:

1. [https://developers.facebook.com/appsに移動](https://developers.facebook.com/apps)します。
1. Facebook開発者アカウントにログインします。
1. Livefyre IDで使用する既存のアプリケーションをクリック **[!UICONTROL Add New App]** または選択します。
1. **[!UICONTROL Settings]** **[!UICONTROL Basic]** をクリックしてから、**[!UICONTROL Contact Email]** アドレス **[!UICONTROL Display Name]**、およびを入力 **[!UICONTROL Privacy Policy URL]** **[!UICONTROL Terms of Service URL]** します。
1. 横のプラス記号（**[!UICONTROL +]**）をクリック **[!UICONTROL Products]** します。
1. **[!UICONTROL Set Up]** 下 **[!UICONTROL Facebook Login]** のをクリックします。
1. をクリック **[!UICONTROL Settings]** し、次の設定を行います。

   * に設定 **[!UICONTROL Client OAuth Login]** **[!UICONTROL Yes]** します。
   * に設定 **[!UICONTROL Web OAuth Login]** **[!UICONTROL Yes]** します。
   * に設定 **[!UICONTROL Use Strict Mode for Redirect URIs]** **[!UICONTROL Yes]** します。
   * に設定 **[!UICONTROL Enforce HTTPS for Web OAuth Login]** **[!UICONTROL Yes]** します。
   * 下 **[!UICONTROL Valid OAuth redirect URLs]** で、URLを追加します `https://identity.livefyre.com/{networkName}/api/v1.0/public/profile/social/complete/facebook_fyre` （ここで `{networkName}` Livefyreによって提供されるネットワーク名）。

1. 下 **[!UICONTROL App Review]** の

   * アプリを公開にします。
   * **[!UICONTROL Approved Items]** **[!UICONTROL Login Permissions]** 必ず、for include `email`、 `public_profile``user_friends`および

完了すると、Facebook開発者のダッシュボードページに、Studioの統合設定で使用するアプリIDとアプリシークレットが一覧表示されます。
