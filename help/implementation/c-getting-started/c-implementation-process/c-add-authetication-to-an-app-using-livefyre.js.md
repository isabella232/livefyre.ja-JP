---
description: Livefyre. jsを使用してLivefyreアプリのページ全体の認証を追加します。
seo-description: Livefyre. jsを使用してLivefyreアプリのページ全体の認証を追加します。
seo-title: Livefyre. jsを使用したアプリへのAuthationの追加
solution: Experience Manager
title: Livefyre. jsを使用したアプリへのAuthationの追加
uuid: b7c61e07- e341-45d7-9112- c50155e38f1d
translation-type: tm+mt
source-git-commit: a6aebcc14325632cab0415e4aa4a24fda8a19bfc

---


# Livefyre. jsを使用したアプリへの認証の追加{#add-authetication-to-an-app-using-livefyre-js}

Livefyre. jsを使用してLivefyreアプリのページ全体の認証を追加します。

`Livefyre.js Aut`hはLivefyreによって開発されたJavaScriptパッケージで、Webサイト上のすべてのアプリケーションが単一の認証統合を共有できます。Authを使用すると、ユーザーがどのように登録してログインし、定義したAuthDelegateオブジェクトにこれらのフローを委任するかを定義できます。

## 手順1:ページの認証を有効にする {#section_pgp_jtt_bbb}

既存の認証システムを使用して、ユーザーがアプリケーションにログインしてアプリケーションとやり取りできるようにするために使用 `Livefyre.js` します。

1. ページで認証を有効にするには、 `Livefyre.js` WebページまたはWebサイトテンプレートの *&lt; head&gt;* 要素に追加します。

   ```
   <script src="//cdn.livefyre.com/Livefyre.js"></script>
   ```

1. 認証を有効に `Livefyre.require` するために使用します。使用 `Livefyre.require` することは、他のパッケージを呼び出す必要があることに似ています。認証を必要とする統合コードは次のようになります。

   ```
   Livefyre.require(['auth'], function (auth) { // Do authy things...});
   ```

## 手順2:AuthDelegateの登録 {#section_oqm_15t_bbb}

認証を有効にするには、認証 `AuthDelegate` を作成して認証に `Livefyre.js` 渡します。

&quot;1つ `AuthDelegate` 」は、ユーザーがログイン、ログアウトおよび表示する方法を決定するオブジェクトです。

1. を作成 `AuthDelegate`します。作成する方法は、ID `AuthDelegate` プロバイダーによって異なります。詳しくは、&quot;ID統合」を参照してください。

1. 認証 `AuthDelegate` を `Livefyre.js` 渡します。最も単純な `AuthDelegate` ログは、ユーザーがアプリケーションから委任ログインメソッドをトリガーした場合に限ります。

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

LivefyreとIDプロバイダーの間でユーザープロファイル情報を同期します。

LivefyreとIDプロバイダーの間でユーザープロファイル情報を同期する必要があります。詳しくは [、Janrain Capture統合](/help/implementation/c-livefyre-identity-comp/c-janrain-capture-backplane-comp.md)を参照してください。
