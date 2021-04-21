---
description: Livefyreアプリでトリガーされないフローを通じてLivefyreでユーザーを認証する場合、Livefyreでは、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。
title: SSOの実装
exl-id: 9af75b8a-9d2a-446e-8cce-2de8645038f2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# SSO{#implementing-sso}の実装

Livefyreアプリでトリガーされないフローを通じてLivefyreでユーザーを認証する場合、Livefyreでは、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。

`authDelegate`が`auth.delegate`に渡されると呼び出され、複数回渡すことができる認証関数が渡されます。 この方法は、認証イベントの制御を逆にすることで、認証に対するグローバル参照を必要とせずに`AuthDelegateobject`を自己完結させることができるようにします。

```
authDelegate.forEachAuthentication = function (authenticate) { 
 window.addEventListener('userAuthenticated', function(data) { 
  authenticate({livefyre: data.token}); 
 }); 
}
```

Livefyreは、認証の調整にユーザートークンを使用します。 その結果、Livefyreでユーザーを認証するには、IDサービスからこのトークンを返す必要があります。 Livefyreのユーザートークンの作成方法について詳しくは、ユーザー認証トークンの作成を参照してください。

>[!NOTE]
>
>ログインが正常に完了すると、authはユーザーのセッションを作成し、ページが更新されてから再読み込みされると、ユーザーのセッションの読み込みを試みます。 `auth.logout()` このセッションをクリアします。つまり、認証とは独立してユーザーのセッションを管理する必要はありません。
