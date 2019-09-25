---
description: Livefyre IdentityをFacebookと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-description: Livefyre IdentityをFacebookと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-title: Livefyre IDで使用するFacebookアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するFacebookアプリの作成
uuid: a7f7be4e-8986-4e79-831a-0bb0ae55599
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するFacebookアプリの作成{#create-a-facebook-app-for-use-with-livefyre-identity}

Livefyre IdentityをFacebookと共に使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。

ユーザーがFacebookの資格情報を使用してログインできるようにするには、Livefyreで次のFacebookアプリの情報が必要です。

* アプリケーション ID
* アプリの秘密

Livefyre idで使用するFacebookアプリを作成するには：

1. https://developers.facebook.com/appsに移動し [ます](https://developers.facebook.com/apps)。
1. Facebook開発者アカウントにログインします。
1. Livefyre IDで使 **[!UICONTROL Add New App]** 用する既存のアプリをクリックまたは選択します。
1. をクリッ **[!UICONTROL Settings]**&#x200B;クし、次にをクリックし **[!UICONTROL Basic]**&#x200B;ます。 住所、、お **[!UICONTROL Contact Email]** よびを **[!UICONTROL Display Name]**&#x200B;入力 **[!UICONTROL Privacy Policy URL]**&#x200B;します **[!UICONTROL Terms of Service URL]**。
1. の横のプラス記号( **[!UICONTROL +]**)をクリックしま **[!UICONTROL Products]**&#x200B;す。
1. の下のをクリッ **[!UICONTROL Set Up]** クしま **[!UICONTROL Facebook Login]**&#x200B;す。
1. をクリ **[!UICONTROL Settings]** ックし、次の設定を行います。

   * Set **[!UICONTROL Client OAuth Login]** to **[!UICONTROL Yes]**.
   * Set **[!UICONTROL Web OAuth Login]** to **[!UICONTROL Yes]**.
   * Set **[!UICONTROL Use Strict Mode for Redirect URIs]** to **[!UICONTROL Yes]**.
   * Set **[!UICONTROL Enforce HTTPS for Web OAuth Login]** to **[!UICONTROL Yes]**.
   * で、URL **[!UICONTROL Valid OAuth redirect URLs]**&#x200B;を追加しま `https://identity.livefyre.com/{networkName}/api/v1.0/public/profile/social/complete/facebook_fyre` す(ここ `{networkName}` では、Livefyreが提供するネットワーク名です)。

1. Under **[!UICONTROL App Review]**:

   * アプリを公開します。
   * forが、、および **[!UICONTROL Approved Items]** を含むこ **[!UICONTROL Login Permissions]** とを確 `email`認し `public_profile`てくださ `user_friends`い。

完了すると、Facebook開発者用ダッシュボードページに、Studioの統合設定で使用するアプリIDとアプリシークレットが表示されます。
