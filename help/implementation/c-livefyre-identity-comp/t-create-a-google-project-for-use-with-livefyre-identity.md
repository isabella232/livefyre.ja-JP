---
description: GoogleとLivefyreのIDを使用すると、ユーザーはGoogleログインを使用してサイト上のアプリとやり取りできます。
seo-description: GoogleとLivefyreのIDを使用すると、ユーザーはGoogleログインを使用してサイト上のアプリとやり取りできます。
seo-title: Livefyre IDで使用するGoogleプロジェクトの作成
solution: Experience Manager
title: Livefyre IDで使用するGoogleプロジェクトの作成
uuid: b0a6bb8a- abea-4f5c-92ed-026e60183e1d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDで使用するGoogleプロジェクトの作成{#create-a-google-project-for-use-with-livefyre-identity}

GoogleとLivefyreのIDを使用すると、ユーザーはGoogleログインを使用してサイト上のアプリとやり取りできます。

ユーザーがGoogle資格情報を使用してログインできるようにするには、Livefyreに以下のGoogleプロジェクト情報が必要です。

* クライアントID
* クライアントシークレット

Livefyre IDで使用するGoogleプロジェクトを作成するには:

1. [https://console.cloud.google.com/projectにアクセス](https://console.cloud.google.com/project) し、Googleアカウントにログインして新規作成するか、Livefyre IDで使用する既存のアプリを選択します。
1. アプリケーションのプロジェクトダッシュボード内から、をクリック **[!UICONTROL Enable and Manage APIs]** します。
1. APIの概要ページの&quot;Social API&quot;で、をクリックしてGoogle+ APIを有効にします。
1. API証明書ページから、「クライアントID&quot;を選択 **[!UICONTROL Credentials > New credentials > OAuth]** します。開く **[!UICONTROL Create client ID]** ページ内:

   * アプリケーションのタイプを選択します。Webアプリケーション。
   * for the **[!UICONTROL Name]** for the **[!UICONTROL Client ID]**.
   * **[!UICONTROL Authorized JavaScript origins]** フィールドは空白のままにします。
   * 入力 **[!UICONTROL Authorized redirect URIs]** : `https://identity.livefyre.com/{networkName}.fyre.co/api/v1.0/public/profile/social/complete/google_fyre` （Livefyre **[!UICONTROL {networkName}]** が提供するネットワーク名です。次に例を示します。** [!UICONTROL labs]** in in **[!UICONTROL `labs.fyre.co`]**.）
   * をクリック **[!UICONTROL Create]** して、資格情報を保存します。

完了すると、GoogleのAPIマネージャー/資格情報ページに、Studioの統合設定ページで使用するプロジェクトのクライアントIDとクライアントシークレットが一覧表示されます。
