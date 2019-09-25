---
description: Livefyre.jsを使用して、Livefyreアプリにページ全体の認証を追加します。
seo-description: Livefyre.jsを使用して、Livefyreアプリにページ全体の認証を追加します。
seo-title: Livefyre.jsを使用したアプリへの認証の追加
solution: Experience Manager
title: Livefyre.jsを使用したアプリへの認証の追加
uuid: b7c61e07-e341-45d7-9112-c50155e38f1d
translation-type: tm+mt
source-git-commit: a6aebcc14325632cab0415e4aa4a24fda8a19bfc

---


# Livefyre.jsを使用したアプリへの認証の追加{#add-authetication-to-an-app-using-livefyre-js}

Livefyre.jsを使用して、Livefyreアプリにページ全体の認証を追加します。

`Livefyre.js Aut`hは、Livefyreが開発したJavaScriptパッケージで、Webサイト上のすべてのアプリケーションで単一の認証統合を共有できます。 Authを使用すると、ユーザーが定義したAuthDelegateオブジェクトにこれらのフローを委任することで、ユーザーの登録、ログイン、ログアウトの方法を定義できます。

## 手順1:ページ認証の有効化 {#section_pgp_jtt_bbb}

既存の `Livefyre.js` 認証システムを使用してユーザーがログインし、アプリとやり取りできるようにするために、ページの認証を有効にするために使用します。

1. ページで認証を有効にするには、Webページまた `Livefyre.js` はWebサイ *トテンプレートの* &lt;head&gt;要素に追加します。

   ```
   <script src="//cdn.livefyre.com/Livefyre.js"></script>
   ```

1. 認証を有 `Livefyre.require` 効にするために使用します。 を使用す `Livefyre.require` る方法は、他のパッケージを呼び出す際に必要となる方法と似ています。 認証を必要とする統合コードは次のようになります。

   ```
   Livefyre.require(['auth'], function (auth) { // Do authy things...});
   ```

## 手順2:AuthDelegateの登録 {#section_oqm_15t_bbb}

認証を有効にするには、認証を作成 `AuthDelegate` し、認証に渡す必要があ `Livefyre.js` ります。

「 」は、 `AuthDelegate` ユーザーがログイン、ログアウト、およびプロファイルの表示を行う方法を決定する、ユーザー定義のオブジェクトです。

1. Create an `AuthDelegate`. を構築する方法は、IDプロバ `AuthDelegate` イダーによって異なります。 詳しい手順については、「ID統合」を参照してください。

1. 認証に `AuthDelegate` 渡し `Livefyre.js` ます。 最も簡単な方法 `AuthDelegate` は、ユーザーがアプリから委任されたログイン方法をトリガーするたびに、同じユーザーをログインする方法です。

   ```
   Livefyre.require(['auth'], function (auth) { 
      auth.delegate({ 
         login: function (errback) { 
            errback(null, { livefyre: '<userAuthToken>' }); 
         }    
      });  
   });
   ```

## 手順3:ユーザーデータの同期 {#section_u4m_j5t_bbb}

LivefyreとIDプロバイダー間でユーザープロファイル情報を同期します。

LivefyreとIDプロバイダー間でユーザープロファイル情報を同期する必要があります。 詳しくは、Janrain Capture Integrationを参 [照してください](/help/implementation/c-livefyre-identity-comp/c-janrain-capture-backplane-comp.md)。
