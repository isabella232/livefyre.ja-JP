---
description: TwitterとLivefyreのIDを使用すると、Twitterログインを使用してサイト上のアプリをインタラクティブに操作できます。
seo-description: TwitterとLivefyreのIDを使用すると、Twitterログインを使用してサイト上のアプリをインタラクティブに操作できます。
seo-title: Livefyre IDで使用するためのTwitterアプリの作成
solution: Experience Manager
title: Livefyre IDで使用するためのTwitterアプリの作成
uuid: 841cce7c-618d-4154-85a3-1de96d04bb69
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyre IDで使用するためのTwitterアプリの作成{#create-a-twitter-app-for-use-with-livefyre-identity}

TwitterとLivefyreのIDを使用すると、Twitterログインを使用してサイト上のアプリをインタラクティブに操作できます。

Twitterログインを有効にするには、Livefyreに以下のTwitterアプリ情報が必要です。

* 消費者キー（APIキー）
* コンシューマーシークレット（APIシークレット）

Livefyre IDで使用するTwitterアプリを作成するには:

1. [https://apps.twitter.com/にアクセス](https://apps.twitter.com/)し、Twitterアカウントにサインインして新規作成するか、Livefyre IDで使用する既存のアプリを選択します。
1. アプリの設定ページから、次の操作を行います。

   * Enter **[!UICONTROL Callback URL:]**`https://identity.livefyre.com/{networkName}.fyre.co/api/v1.0/public/profile/social/complete/twitter_fyre` （ **{networkName}** はLivefyreが提供するネットワーク名です。次に例を示します。** [!UICONTROL labs]** in in **[!UICONTROL `labs.fyre.co`]**.）
   * 選択を解除 **[!UICONTROL Enable Callback Locking]**します。
   * 選択 **[!UICONTROL Allow this application to be used to Sign in with Twitter]**します。

1. **[!UICONTROL Permissions]** タブから、を選択 **[!UICONTROL Access: Read only]**します。

完了すると、Twitterのアプリケーション管理/キーおよびアクセストークンページに、Studioの統合設定ページで使用するアプリのコンシューマーキー（APIキー）およびコンシューマーシークレット（APIシークレット）が一覧表示されます。
