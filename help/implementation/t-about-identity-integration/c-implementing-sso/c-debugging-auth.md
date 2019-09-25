---
description: 統合およびテスト中に、コンソールからユーザーをログインし、認証をデバッグできます。
seo-description: 統合およびテスト中に、コンソールからユーザーをログインし、認証をデバッグできます。
seo-title: 認証委任のデバッグ
solution: Experience Manager
title: 認証委任のデバッグ
uuid: fb0c7396-190e-4dc9-bf26-23dde9efd45d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 認証委任のデバッグ{#debugging-auth-delegate}

統合およびテスト中に、コンソールからユーザーをログインし、認証をデバッグできます。

次の（トークン）を使用してコンソールを使用してユーザ `auth.authenticate` ーをログインし、Livefyreユーザートークンを渡して、ページ上でユーザーを認証します。

また、上記の例を変更し、JavaScriptに次のスニペットをインラインで追加して、ユーザーをLivefyreにすばやくログインできます（認証の参照が必要です）。

```
window.addEventListener('userAuthenticated', function(data) { 
 Livefyre.require(['auth'], function (auth) { 
  auth.authenticate({livefyre: data.token}); 
 }); 
});
```

