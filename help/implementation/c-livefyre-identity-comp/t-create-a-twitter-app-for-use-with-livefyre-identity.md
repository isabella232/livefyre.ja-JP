---
description: TwitterでLivefyre IDを使用して、ユーザーがTwitterログインを使用してサイト上のアプリをインタラクティブに操作できるようにすることができます。
seo-description: TwitterでLivefyre IDを使用して、ユーザーがTwitterログインを使用してサイト上のアプリをインタラクティブに操作できるようにすることができます。
seo-title: Livefyre IDで使用するTwitterアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するTwitterアプリの作成
uuid: 841cce7c-618d-4154-85a3-1de96d04bb69
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するTwitterアプリの作成{#create-a-twitter-app-for-use-with-livefyre-identity}

TwitterでLivefyre IDを使用して、ユーザーがTwitterログインを使用してサイト上のアプリをインタラクティブに操作できるようにすることができます。

Twitterログインを有効にするには、Livefyreで次のTwitterアプリの情報が必要です。

* コンシューマーキー（APIキー）
* コンシューマシークレット（APIシークレット）

Livefyre idで使用するTwitterアプリを作成するには：

1. https://apps.twitter.com/に移動し [、Twitter](https://apps.twitter.com/)アカウントにサインインして、Livefyre IDで使用する新しいアプリを作成するか、既存のアプリを選択します。
1. アプリの設定ページから、次の操作を行います。

   * Livefyreが提供す **[!UICONTROL Callback URL:]** るネットワ `https://identity.livefyre.com/{networkName}.fyre.co/api/v1.0/public/profile/social/complete/twitter_fyre` ーク名を入力します **** （{networkName}はLivefyreが提供するネットワーク名です）。 For example:** [!UICONTROL labs]** in **[!UICONTROL `labs.fyre.co`]**.)
   * Deselect **[!UICONTROL Enable Callback Locking]**.
   * Select **[!UICONTROL Allow this application to be used to Sign in with Twitter]**.

1. タブで、を **[!UICONTROL Permissions]** 選択します **[!UICONTROL Access: Read only]**。

完了すると、Twitterのアプリケーション管理/キーとアクセストークンページに、Studioの統合設定ページで使用するアプリのコンシューマーキー（APIキー）とコンシューマーシークレット（APIシークレット）が表示されます。
