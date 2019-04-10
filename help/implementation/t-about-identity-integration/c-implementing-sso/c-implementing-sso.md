---
description: Livefyreアプリケーションによってトリガーされないフロー経由でLivefyreを使用するユーザーを認証するには、LivefyreによってAuthDelegateオブジェクトにForegoPlayationメソッドを実装することをお勧めします。
seo-description: Livefyreアプリケーションによってトリガーされないフロー経由でLivefyreを使用するユーザーを認証するには、LivefyreによってAuthDelegateオブジェクトにForegoPlayationメソッドを実装することをお勧めします。
seo-title: SSOの実装
solution: Experience Manager
title: SSOの実装
uuid: c96d456c- b1ac-40e0-8d18-224652b9697f
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# SSOの実装{#implementing-sso}

Livefyreアプリケーションによってトリガーされないフロー経由でLivefyreを使用するユーザーを認証するには、LivefyreによってAuthDelegateオブジェクトにForegoPlayationメソッドを実装することをお勧めします。

これは、渡さ `authDelegate` れると呼び出さ `auth.delegate`れ、複数回渡すことができる認証関数に渡されます。このメソッドは、認証イベントの制御を反転して、認証をグローバル `AuthDelegateobject` 参照することなく自己完結できるようにします。

```
authDelegate.forEachAuthentication = function (authenticate) { 
 window.addEventListener('userAuthenticated', function(data) { 
  authenticate({livefyre: data.token}); 
 }); 
}
```

Livefyreは、認証のためのユーザートークンに依存しています。そのため、Livefyreのユーザーを認証するには、IDサービスからこのトークンを返す必要があります。Livefyreユーザートークンの作成方法については、「ユーザー認証トークンの作成」を参照してください。

>[!NOTE]
>
>ログインが成功すると、ユーザーのセッションが作成され、ページの更新とリロード時にユーザーのセッションの読み込みが試行されます。`auth.logout()` このセッションをクリアします。つまり、認証とは独立してユーザーのセッションを管理する必要はありません。

