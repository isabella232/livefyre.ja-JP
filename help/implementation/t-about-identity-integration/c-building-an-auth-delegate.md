---
description: authDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に対して必要な動作を実装します。
seo-description: authDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に対して必要な動作を実装します。
seo-title: AuthDelegateオブジェクト
solution: Experience Manager
title: AuthDelegateオブジェクト
uuid: a6acc4ef- d442-4782-9bfa- bbe494547c2e
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# AuthDelegateオブジェクト{#authdelegate-object}

authDelegateオブジェクトは、サイトの既存の認証システムとの統合をカスタマイズできるように、認証アクションおよびイベントの実行方法に対して必要な動作を実装します。

## 認証委任の構築 {#section_wmn_tv2_gz}

アクションを実行するには、認証パッケージに認証パッケージを提供する必要があります。認証delegateは、このトピックのいずれかのメソッドを実装するJavaScriptオブジェクトです。

## . login（finishLogin） {#section_mpk_lv2_gz}

有効なユーザーにログインし、エラーが発生した場合またはユーザーのLivefyre資格情報がある場合は、FinishLogin関数を呼び出します。このメソッドの一般的な実装では、ユーザーをログインページにリダイレクトするか、新しいウィンドウまたはモーダルを開きます。

この例では、Livefyreユーザーの認証トークン、トークンを自動的に通知します。

```
authDelegate.login = function (finishLogin) { 
 finishLogin(null, { 
   livefyre: 'token' 
 }); 
};
```

最も単純なログインのデリゲートは、Livefyre認証トークンのエンドユーザーに要求する可能性があります。

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

## . logout（complishLogout） {#section_uqz_2v2_gz}

ユーザーをログアウトし、エラーが発生した場合はErrorオブジェクトを使用してcomplishLogout関数を起動し、ログアウトが成功したことを通知するにはnullを呼び出します。

次に例を示します。

```
authDelegate.logout = function (finishLogout) { 
 clearUserSession(); //logic to clear a user session  
 finishLogout(null); 
}
```

## . viewProfile（user） {#section_kkv_dv2_gz}

ユーザーのプロファイルを表示するアクションを実行します。

```
authDelegate.viewProfile = function (user) { 
 window.open(user.get('profileUrl')); 
}
```

## . editProfile（user） {#section_bkx_pq2_gz}

ユーザーのプロファイルを編集するアクションを実行します。

```
authDelegate.editProfile = function (user) { 
 window.open(user.get('profileUrl') + '/edit/'); 
}
```

上記のすべてのメソッドを実装することで、認証をカスタム認証委任を使用して設定できます。委任が構築されると、delegateメソッドを使用して認証に提供できます。

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

