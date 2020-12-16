---
description: Livefyreアプリでトリガーされないフローを通じてLivefyreでユーザーを認証する場合、Livefyreでは、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。
seo-description: Livefyreアプリでトリガーされないフローを通じてLivefyreでユーザーを認証する場合、Livefyreでは、AuthDelegateオブジェクトにforEachAuthenticationメソッドを実装することをお勧めします。
seo-title: SSOの実装
solution: Experience Manager
title: SSOの実装
uuid: c96d456c-b1ac-40e0-8d18-224652b9697f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '218'
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

