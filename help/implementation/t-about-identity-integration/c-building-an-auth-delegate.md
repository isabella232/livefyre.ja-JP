---
description: AuthDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に必要な動作を実装します。
seo-description: AuthDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に必要な動作を実装します。
seo-title: AuthDelegateオブジェクト
solution: Experience Manager
title: AuthDelegateオブジェクト
uuid: a6acc4ef-d442-4782-9bfa-bbe494547c2e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---


# AuthDelegateオブジェクト{#authdelegate-object}

AuthDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に必要な動作を実装します。

## 認証委任の構築{#section_wmn_tv2_gz}

操作を実行する前に、認証パッケージに認証委任を指定する必要があります。 認証委任とは、このトピックのいずれかのメソッドを実装する任意のJavaScriptオブジェクトです。

## .login(finishLogin) {#section_mpk_lv2_gz}

有効なユーザーにログインし、エラーが発生した場合はErrorオブジェクト、またはユーザーのLivefyre資格情報を使用して、finishLogin関数を呼び出します。 このメソッドの一般的な実装では、ユーザーがログインページにリダイレクトされるか、新しいウィンドウまたはモーダルが開きます。

次の例では、認証トークン、トークンを持つLivefyreユーザーの認証を自動的に通知します。

```
authDelegate.login = function (finishLogin) { 
 finishLogin(null, { 
   livefyre: 'token' 
 }); 
};
```

最も単純なログイン委任機能は、エンドユーザーにLivefyre認証トークンを要求する場合があります。

```
authDelegate.login = function contrivedLogin(finishLogin) { 
  var lfToken = prompt("Please type your Livefyre Token");  
  if (lfToken.length === 0) { 
   return finishLogin(new Error("User failed to type their lftoken")); 
  }  
 finishLogin(null, { 
   livefyre: lfToken 
 }); 
};
```

## .logout(finishLogout) {#section_uqz_2v2_gz}

ユーザーをログアウトし、Errorオブジェクト（エラーが発生した場合）またはNull（ログアウトが成功したことを認証に通知する場合）を使用して、finishLogout関数を呼び出します。

例：

```
authDelegate.logout = function (finishLogout) { 
 clearUserSession(); //logic to clear a user session  
 finishLogout(null); 
}
```

## .viewProfile(user) {#section_kkv_dv2_gz}

ユーザーのプロファイルを表示するためのアクションを実行します。

```
authDelegate.viewProfile = function (user) { 
 window.open(user.get('profileUrl')); 
}
```

## .editProfile(user) {#section_bkx_pq2_gz}

ユーザーのプロファイルを編集するアクションを実行します。

```
authDelegate.editProfile = function (user) { 
 window.open(user.get('profileUrl') + '/edit/'); 
}
```

上記のすべてのメソッドを実装することで、カスタムの認証委任を使用して認証を設定できます。 委任を構築すると、delegateメソッドを使用して認証用に提供できます。

```
var authDelegate = { 
 login: function(cb) { 
  ... 
  cb(null); 
 }, 
 ... 
} 
  
auth.delegate(authDelegate);
```

