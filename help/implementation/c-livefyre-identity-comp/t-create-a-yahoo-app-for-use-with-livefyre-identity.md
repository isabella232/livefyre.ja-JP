---
description: Yahoo!でLivefyre IDを使用できます。ユーザがYahoo!を使用できるようにすること。ログインを参照してください。
seo-description: Yahoo!でLivefyre IDを使用できます。ユーザがYahoo!を使用できるようにすること。ログインを参照してください。
seo-title: Yahoo!の作成!Livefyre IDで使用するアプリケーション
solution: Experience Manager
title: Yahoo!の作成!Livefyre IDで使用するアプリケーション
uuid: 6863cd2e- eb0d-465b- b706-88ecaccf41bc
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Yahoo!の作成!Livefyre IDで使用するアプリケーション{#create-a-yahoo-app-for-use-with-livefyre-identity}

Yahoo!でLivefyre IDを使用できます。ユーザがYahoo!を使用できるようにすること。ログインを参照してください。

ユーザーがYahoo資格情報を使用してログインできるようにするには、Livefyreには次のYahooアプリケーション情報が必要です。

* クライアントID（消費者キー）
* クライアントシークレット（消費者シークレット）

Yahoo!を作成するにはアプリケーションをLivefyre IDで使用する場合:

1. [https://developer.yahoo.com/apps/に移動](https://developer.yahoo.com/apps/)し、Yahoo!にサインインします。アカウントを作成するか、Livefyre IDで使用する既存のアプリを選択します。
1. 選択 **[!UICONTROL Application Type: Web Application]** します。
1. Enter **[!UICONTROL Callback Domain:]** `https://identity.livefyre.com`
1. 「 **[!UICONTROL API Permissions: Profiles (Social Directory)]** および **[!UICONTROL Read Public]** 」を選択します。

   完了すると、Yahooのアプリの詳細ページに、Studioの統合設定ページで使用するアプリケーションのクライアントID（消費者キー）とクライアントシークレット（消費者シークレット）が一覧表示されます。

   >[!NOTE]
   >
   >Yahoo!を有効にする場合Yahoo!アプリケーションで、「クライアントID&quot;フィールドと「クライアントシークレット」フィールドをStudioの空白にした場合、LivefyreはOpenIDを使用してこれらのユーザーをLivefyreアプリケーションにログインします。この場合、OAuthおよびカスタムブランディングは使用できません。