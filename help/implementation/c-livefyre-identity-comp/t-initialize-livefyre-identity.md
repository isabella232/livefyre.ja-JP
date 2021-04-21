---
description: Livefyre.js認証パッケージを使用すると、ページ上のすべてのソーシャルコンポーネントで単一の認証統合を検出できます。
title: Livefyre IDの初期化
exl-id: 9990d284-a21e-49fb-932c-62906b41484a
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Livefyre IDの初期化{#initialize-livefyre-identity}

Livefyre.js認証パッケージを使用すると、ページ上のすべてのソーシャルコンポーネントで単一の認証統合を検出できます。

Livefyreは、適切な認証委任を行う`lfep-auth-delegate`パッケージを提供しています。 Authは、ログインやログアウトなどの認証操作の実行方法を知っているAuthDelegateオブジェクトを提供する必要があります。

1. 追加Livefyre.jsをWebページに追加します。
1. これらの操作をLivefyre IDに委任するようにAuthに指示するには、以下を追加します。

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
