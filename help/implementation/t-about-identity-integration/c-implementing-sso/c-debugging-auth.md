---
description: 統合および認証のテスト中に、コンソールを介してユーザーをログインできます。
seo-description: 統合および認証のテスト中に、コンソールを介してユーザーをログインできます。
seo-title: デバッグ認証の委任
solution: Experience Manager
title: デバッグ認証の委任
uuid: fb0c7396-190e-4dc9- bf26-23dictionary9efd45d
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# デバッグ認証の委任{#debugging-auth-delegate}

統合および認証のテスト中に、コンソールを介してユーザーをログインできます。

次 `auth.authenticate` の（トークン）を使用してコンソール経由でユーザーをログインし、Livefyreユーザートークンを渡して、ページ上のユーザーを認証します。

上記の例を変更し、JavaScriptに次のスニペットを追加して、ユーザーをLivefyreにすばやくログインさせることもできます（認証を参照する必要があります）。

```
window.addEventListener('userAuthenticated', function(data) { 
 Livefyre.require(['auth'], function (auth) { 
  auth.authenticate({livefyre: data.token}); 
 }); 
});
```

