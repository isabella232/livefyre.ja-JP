---
description: Livefyre.jsを使用して、Livefyre Appsのページ全体の認証を追加します。
seo-description: Livefyre.jsを使用して、Livefyre Appsのページ全体の認証を追加します。
seo-title: 追加Livefyre.jsを使用したアプリの認証
solution: Experience Manager
title: 追加Livefyre.jsを使用したアプリの認証
uuid: b7c61e07-e341-45d7-9112-c50155e38f1d
translation-type: tm+mt
source-git-commit: a6aebcc14325632cab0415e4aa4a24fda8a19bfc
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---


# Livefyre.js追加を使用したアプリへの認証{#add-authetication-to-an-app-using-livefyre-js}

Livefyre.jsを使用して、Livefyre Appsのページ全体の認証を追加します。

`Livefyre.js Aut`hは、Livefyreが開発したJavaScriptパッケージで、Webサイト上のすべてのアプリケーションで単一の認証統合を共有できます。Authを使用すると、ユーザーが定義したAuthDelegateオブジェクトにこれらのフローを委任することで、ユーザーの登録、ログイン、ログアウト方法を定義できます。

## 手順1:ページの認証を有効にする{#section_pgp_jtt_bbb}

`Livefyre.js`を使用してページの認証を有効にし、ユーザーがログインして既存の認証システムを使用したアプリとのやり取りを可能にします。

1. ページで認証を有効にするには、WebページまたはWebサイトテンプレートの&#x200B;*&lt;head>*&#x200B;要素に`Livefyre.js`を追加します。

   ```
   <script src="//cdn.livefyre.com/Livefyre.js"></script>
   ```

1. `Livefyre.require`を使用して認証を有効にします。 `Livefyre.require`の使用は、他のパッケージを呼び出す際に必要となるのと似ています。 認証を必要とする統合コードは次のようになります。

   ```
   Livefyre.require(['auth'], function (auth) { // Do authy things...});
   ```

## 手順2:AuthDelegateを登録する{#section_oqm_15t_bbb}

認証を有効にするには、`AuthDelegate`を作成し、`Livefyre.js`認証に渡します。

`AuthDelegate`とは、ユーザーのログイン、ログアウト、表示プロファイルの方法を決定する、ユーザー定義のオブジェクトです。

1. `AuthDelegate`を作成します。 `AuthDelegate`の構成方法は、使用するIDプロバイダによって異なります。 詳しい手順については、「ID統合」を参照してください。

1. `AuthDelegate`を`Livefyre.js`認証に渡します。 最も簡単な`AuthDelegate`は、ユーザーがアプリから委任されたログイン方法をトリガーするたびに、同じユーザーをログインします。

   ```
   Livefyre.require(['auth'], function (auth) { 
      auth.delegate({ 
         login: function (errback) { 
            errback(null, { livefyre: '<userAuthToken>' }); 
         }    
      });  
   });
   ```

## 手順3:ユーザーデータの同期{#section_u4m_j5t_bbb}

LivefyreとIDプロバイダー間でユーザープロファイル情報を同期します。

ユーザープロファイル情報は、LivefyreとIDプロバイダーの間で同期する必要があります。 詳しくは、[ジャンレイン・キャプチャの統合](/help/implementation/c-livefyre-identity-comp/c-janrain-capture-backplane-comp.md)を参照してください。
