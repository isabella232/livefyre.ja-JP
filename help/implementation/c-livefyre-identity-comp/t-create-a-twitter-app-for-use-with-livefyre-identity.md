---
description: Livefyre IDとTwitterを使用して、Twitterログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-description: Livefyre IDとTwitterを使用して、Twitterログインを使用してサイト上のアプリを操作できるようにすることができます。
seo-title: Livefyre IDと共に使用するTwitterアプリを作成する
solution: Experience Manager
title: Livefyre IDと共に使用するTwitterアプリを作成する
uuid: 841cce7c-618d-4154-85a3-1de96d04bb69
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---


# Livefyre IDと共に使用するTwitterアプリを作成する{#create-a-twitter-app-for-use-with-livefyre-identity}

Livefyre IDとTwitterを使用して、Twitterログインを使用してサイト上のアプリを操作できるようにすることができます。

Twitterのログインを有効にするには、Livefyreで次のTwitterアプリ情報が必要です。

* Consumer key（APIキー）
* Consumer secret（APIシークレット）

Livefyre Idで使用するTwitterアプリを作成するには：

1. [https://apps.twitter.com/](https://apps.twitter.com/)に移動し、Twitterアカウントにサインインして、Livefyre IDで使用する新しいアプリを作成するか、既存のアプリを選択します。
1. アプリの設定ページから、次の操作を行います。

   * **[!UICONTROL Callback URL:]** `https://identity.livefyre.com/{networkName}.fyre.co/api/v1.0/public/profile/social/complete/twitter_fyre`と入力します（**{networkName}**&#x200B;はLivefyreが提供するネットワーク名です）。 例：**[!UICONTROL `labs.fyre.co`]**&#x200B;の** [!UICONTROL labs]**
   * 選択を解除 **[!UICONTROL Enable Callback Locking]**.
   * Select **[!UICONTROL Allow this application to be used to Sign in with Twitter]**.

1. 「**[!UICONTROL Permissions]**」タブで、「**[!UICONTROL Access: Read only]**」を選択します。

完了すると、Twitterのアプリケーション管理/キーとアクセストークンページに、Studioの統合設定ページで使用するアプリのConsumer key（APIキー）とConsumer secret（APIシークレット）がリストされます。
