---
description: Livefyre IDはYahoo！で使用できます。 ユーザがYahoo! ログインして、サイト上のアプリを操作します。
seo-description: Livefyre IDはYahoo！で使用できます。 ユーザがYahoo! ログインして、サイト上のアプリを操作します。
seo-title: Yahoo! Livefyre IDで使用するアプリ
solution: Experience Manager
title: Yahoo! Livefyre IDで使用するアプリ
uuid: 6863cd2e-eb0d-465b-b706-88ecaccf41bc
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Yahoo! Livefyre IDで使用するアプリ{#create-a-yahoo-app-for-use-with-livefyre-identity}

Livefyre IDはYahoo！で使用できます。 ユーザがYahoo! ログインして、サイト上のアプリを操作します。

ユーザーがYahooの資格情報を使用してログインできるようにするには、Livefyreで次のYahooアプリケーション情報が必要です。

* クライアントID（コンシューマーキー）
* クライアントシークレット（コンシューマシークレット）

Yahoo！を作成するには livefyre idで使用するアプリ：

1. https://developer.yahoo.com/apps/に移 [動し](https://developer.yahoo.com/apps/)、Yahoo! アカウントを使用して、Livefyre IDで使用する新しいアプリを作成するか、既存のアプリを選択します。
1. Select **[!UICONTROL Application Type: Web Application]**.
1. Enter **[!UICONTROL Callback Domain:]** `https://identity.livefyre.com`
1. とを選 **[!UICONTROL API Permissions: Profiles (Social Directory)]** 択しま **[!UICONTROL Read Public]**&#x200B;す。

   完了すると、Yahooのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID（コンシューマーキー）とクライアントシークレット（コンシューマーシークレット）が表示されます。

   >[!NOTE]
   >
   >Yahoo! yahoo！を作成せずにログインする アプリケーションに追加し、Studioの「クライアントID」フィールドと「クライアントシークレット」フィールドを空白のままにした場合、LivefyreはOpenIDを使用してLivefyreアプリケーションにユーザーをログインします。 この場合、OAuthとカスタムブランドは使用できません。