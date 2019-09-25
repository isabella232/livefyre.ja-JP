---
description: Livefyreアプリでトリガーされないフローを介してLivefyreでユーザーを認証する場合、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。
seo-description: Livefyreアプリでトリガーされないフローを介してLivefyreでユーザーを認証する場合、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。
seo-title: SSOの実装
solution: Experience Manager
title: SSOの実装
uuid: c96d456c-b1ac-40e0-8d18-224652b9697f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# SSOの実装{#implementing-sso}

Livefyreアプリでトリガーされないフローを介してLivefyreでユーザーを認証する場合、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。

この関数は、がに渡さ `authDelegate` れると呼び出さ `auth.delegate`れ、複数回渡される認証関数が渡されます。 この方法は、認証イベントの制御を逆にするので、認証に対するグローバル参照を必要とす `AuthDelegateobject` ることなく、ユーザーが自己完結できるようにします。

```
authDelegate.forEachAuthentication = function (authenticate) { 
 window.addEventListener('userAuthenticated', function(data) { 
  authenticate({livefyre: data.token}); 
 }); 
}
```

Livefyreは、認証の調整にユーザートークンを使用します。 その結果、Livefyreでユーザーを認証するには、IDサービスからこのトークンを返す必要があります。 Livefyreユーザートークンの作成方法について詳しくは、ユーザー認証トークンの構築を参照してください。

>[!NOTE]
>
>ログインに成功した後、authはユーザーのセッションを作成し、ページの更新と再読み込みの際にユーザーのセッションの読み込みを試みます。 `auth.logout()` は、このセッションをクリアします。 つまり、認証とは独立してユーザーのセッションを管理する必要はありません。

