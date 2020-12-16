---
description: Livefyre IDはYahoo! を使用して、ユーザがYahoo! サイトのアプリとやり取りするためのログイン。
seo-description: Livefyre IDはYahoo! を使用して、ユーザがYahoo! サイトのアプリとやり取りするためのログイン。
seo-title: Yahoo！の作成 Livefyre IDで使用するアプリ
solution: Experience Manager
title: Yahoo！の作成 Livefyre IDで使用するアプリ
uuid: 6863cd2e-eb0d-465b-b706-88ecaccf41bc
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Yahoo！の作成 Livefyre IDと共に使用するアプリ{#create-a-yahoo-app-for-use-with-livefyre-identity}

Livefyre IDはYahoo! を使用して、ユーザがYahoo! サイトのアプリとやり取りするためのログイン。

ユーザーがYahooの資格情報を使用してログインできるようにするには、Livefyreで次のYahooアプリ情報が必要です。

* クライアントID(Consumer key)
* クライアントシークレット(Consumer secret)

Yahoo！を作成するには Livefyre IDで使用するアプリ：

1. [https://developer.yahoo.com/apps/](https://developer.yahoo.com/apps/)に移動し、Yahoo！にサインインします。 アカウントを作成するか、Livefyre Idで使用する既存のアプリを選択します。
1. Select **[!UICONTROL Application Type: Web Application]**.
1. Enter **[!UICONTROL Callback Domain:]** `https://identity.livefyre.com`
1. **[!UICONTROL API Permissions: Profiles (Social Directory)]**&#x200B;と&#x200B;**[!UICONTROL Read Public]**&#x200B;を選択します。

   完了すると、Yahooのアプリの詳細ページに、Studioの統合設定ページで使用するアプリのクライアントID(Consumer key)とクライアントシークレット(Consumer secret)がリストされます。

   >[!NOTE]
   >
   >Yahoo! Yahoo! アプリケーションに追加し、Studioの「クライアントID」と「クライアントシークレット」フィールドを空白のままにした場合、LivefyreはOpenIDを使用してLivefyre Appsにログインします。 この場合、OAuthとカスタムブランドは使用できません。