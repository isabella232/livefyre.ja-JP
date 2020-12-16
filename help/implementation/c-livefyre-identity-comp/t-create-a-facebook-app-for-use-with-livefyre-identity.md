---
description: Livefyre IDとFacebookを使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-description: Livefyre IDとFacebookを使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。
seo-title: Livefyre IDと共に使用するFacebookアプリを作成する
solution: Experience Manager
title: Livefyre IDと共に使用するFacebookアプリを作成する
uuid: a7f7be4e-8986-4e79-831a-0bb0ae555599
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Livefyre IDと共に使用するFacebookアプリの作成{#create-a-facebook-app-for-use-with-livefyre-identity}

Livefyre IDとFacebookを使用して、ユーザーがFacebookのログインを使用してサイト上のアプリとやり取りできるようにすることができます。

ユーザーがFacebookの資格情報を使用してログインできるようにするには、Livefyreに次のFacebookアプリ情報が必要です。

* アプリケーション ID
* アプリの秘密

Livefyre Idで使用するFacebookアプリを作成するには：

1. [https://developers.facebook.com/apps](https://developers.facebook.com/apps)に移動します。
1. Facebook開発者アカウントにログインします。
1. **[!UICONTROL Add New App]**&#x200B;をクリックするか、Livefyre Idで使用する既存のアプリを選択します。
1. 「**[!UICONTROL Settings]**」、「**[!UICONTROL Basic]**」の順にクリックします。 **[!UICONTROL Contact Email]**&#x200B;アドレス、**[!UICONTROL Display Name]**、**[!UICONTROL Privacy Policy URL]**、**[!UICONTROL Terms of Service URL]**&#x200B;を入力します。
1. **[!UICONTROL Products]**&#x200B;の横のプラス記号(**[!UICONTROL +]**)をクリックします。
1. **[!UICONTROL Facebook Login]**&#x200B;の下の&#x200B;**[!UICONTROL Set Up]**&#x200B;をクリックします。
1. **[!UICONTROL Settings]**&#x200B;をクリックし、次の設定を行います。

   * **[!UICONTROL Client OAuth Login]**&#x200B;を&#x200B;**[!UICONTROL Yes]**&#x200B;に設定します。
   * **[!UICONTROL Web OAuth Login]**&#x200B;を&#x200B;**[!UICONTROL Yes]**&#x200B;に設定します。
   * **[!UICONTROL Use Strict Mode for Redirect URIs]**&#x200B;を&#x200B;**[!UICONTROL Yes]**&#x200B;に設定します。
   * **[!UICONTROL Enforce HTTPS for Web OAuth Login]**&#x200B;を&#x200B;**[!UICONTROL Yes]**&#x200B;に設定します。
   * **[!UICONTROL Valid OAuth redirect URLs]**&#x200B;の下に、URL `https://identity.livefyre.com/{networkName}/api/v1.0/public/profile/social/complete/facebook_fyre`を追加します（`{networkName}`はLivefyreが提供するネットワーク名です）。

1. **[!UICONTROL App Review]**&#x200B;の下：

   * アプリを公開にします。
   * **[!UICONTROL Login Permissions]**&#x200B;の&#x200B;**[!UICONTROL Approved Items]**&#x200B;には`email`、`public_profile`、`user_friends`が含まれていることを確認してください。

完了すると、Facebook開発者のダッシュボードページに、Studioの統合設定で使用するApp IDとApp Secretがリストされます。
