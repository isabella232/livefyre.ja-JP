---
description: 統合およびテスト中に、コンソールを通じてユーザーをログインし、認証のデバッグを行うことができます。
title: 認証委任のデバッグ
exl-id: fa1c17fa-5aba-4f4c-9217-5823af30af61
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '90'
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
