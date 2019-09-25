---
description: Livefyre.js認証パッケージを使用すると、ページ上のすべてのソーシャルコンポーネントで単一の認証統合を検出できます。
seo-description: Livefyre.js認証パッケージを使用すると、ページ上のすべてのソーシャルコンポーネントで単一の認証統合を検出できます。
seo-title: Livefyre IDの初期化
title: Livefyre IDの初期化
uuid: 9365d827-2734-4a84-bfe7-9be573b2b03e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre IDの初期化{#initialize-livefyre-identity}

Livefyre.js認証パッケージを使用すると、ページ上のすべてのソーシャルコンポーネントで単一の認証統合を検出できます。

Livefyreが提供するパッ `lfep-auth-delegate` ケージを使用して、適切な認証委任を行うことができます。 Authは、ログインやログアウトなどの認証操作の実行方法を知っているAuthDelegateオブジェクトを提供する必要があります。

1. Livefyre.jsをWebページに追加します。
1. AuthにこれらのアクションをLivefyre idに委任するように指示するには、次を追加します。

   ```
   Livefyre.require([ 
     'livefyre-auth', 
     'identity' 
     ], function (auth, Identity) { 
       var identity = new Identity({ 
         app: "https://identity.livefyre.com/{networkName}.fyre.co" 
       }); 
    auth.delegate( identity ); 
    });
   ```
