---
description: 統合およびテスト中に、コンソールを通じてユーザーをログインし、認証のデバッグを行うことができます。
seo-description: 統合およびテスト中に、コンソールを通じてユーザーをログインし、認証のデバッグを行うことができます。
seo-title: 認証委任のデバッグ
solution: Experience Manager
title: 認証委任のデバッグ
uuid: fb0c7396-190e-4dc9-bf26-23dde9efd45d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---


# 認証委任のデバッグ{#debugging-auth-delegate}

統合およびテスト中に、コンソールを通じてユーザーをログインし、認証のデバッグを行うことができます。

次の`auth.authenticate`（トークン）を使用してコンソールからユーザーをログインし、Livefyreユーザートークンを渡してページ上のユーザーを認証します。

また、上記の例を変更し、JavaScriptに次のスニペットをインラインで追加して、ユーザーをLivefyreにすばやくログインできます（認証の参照が必要です）。

```
window.addEventListener('userAuthenticated', function(data) { 
 Livefyre.require(['auth'], function (auth) { 
  auth.authenticate({livefyre: data.token}); 
 }); 
});
```

