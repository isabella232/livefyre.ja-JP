---
description: Livefyre IDはYahoo! を使用して、ユーザがYahoo! サイトのアプリとやり取りするためのログイン。
title: Yahoo！の作成 Livefyre IDで使用するアプリ
exl-id: 6b4c6ea9-1cb0-4496-aabe-70811f464a3d
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '203'
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
