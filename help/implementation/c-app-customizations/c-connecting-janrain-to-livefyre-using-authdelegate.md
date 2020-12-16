---
description: Livefyre.requireは、Janrainバックプレーンバスをリッスンするための認証を有効にするプラグインを提供します。
seo-description: Livefyre.requireは、Janrainバックプレーンバスをリッスンするための認証を有効にするプラグインを提供します。
seo-title: AuthDelegateを使用したJanrainのLivefyreへの接続
title: AuthDelegateを使用したJanrainのLivefyreへの接続
uuid: 9d56e3f4-960a-4108-aab5-2795b0e71c88
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 1%

---


# AuthDelegateを使用したJanrainのLivefyreへの接続{#connecting-janrain-to-livefyre-using-authdelegate}

Livefyre.requireは、Janrainバックプレーンバスをリッスンするための認証を有効にするプラグインを提供します。

ID/ログインメッセージがバックプレーンチャネルでブロードキャストされると、ユーザーのLivefyre認証トークンを使用してauth.authenticate()が呼び出されます。 AuthDelegateは、まだ実装する必要があります。

```
Livefyre.require(['auth', 'backplane-auth-plugin#0'], function(auth, backplanePluginFactory) { 
   auth.plugin(backplanePluginFactory('network.fyre.co')); 
   auth.delegate({ 
      login: function (finishLogin) { 
         loginWithCapture(finishLogin); 
      } 
   }); 
});
```

>[!NOTE]
>
>Livefyre Backplaneプラグインを使用してauth.pluginを呼び出す前に、window.Backplaneオブジェクトをページで定義する必要があります。 バックプレーンオブジェクトが使用可能であることを確認するには、onReadyコールバックからLivefyreインスタンス化コードを呼び出します。 Janrainの担当者に問い合わせて、他のアプリケーションがバックプレーンオブジェクトを使用する可能性があるかどうかを確認してください。

次に、Janrain Capture統合に対する認証委任の検索例を示します。

>[!NOTE]
>
>認証委任は、ジャンレインインスタンスによって異なります。

<!--Hannah: Mystery stray bullet found here. Please check against source. -Bob -->

* 認証委任のログインメソッドに渡されるコールバック
* Janrainキャプチャ変数への参照。
* :バックプレーンオブジェクトへの参照。

```
/** 
* Login function 
* In this case, opens a login modal and triggers Backplane to start listening 
* for login messages 
*/ 
authDelegate.login = function(finishLogin) { 
   var successCallback = function() { 
      // These need to be replaced with the actions that correspond to successful login  
      // and when the Janrain modal is closed. 
      janrain.events.onCaptureLoginSuccess.removeHandler(successCallback); 
      janrain.events.onModalClose.removeHandler(failureCallback); 
      finishLogin(); 
   }; 
  
   var failureCallback = function(e) { 
      janrain.events.onModalClose.removeHandler(failureCallback); 
      janrain.events.onCaptureLoginSuccess.removeHandler(successCallback); 
      finishLogin(e || new Error("Error logging in with Janrain Capture")); 
   }; 
  
   // Open the modal to log a user in 
   janrain.capture.ui.renderScreen('signIn'); 
   // Send a backplane message 
   window.Backplane.expectMessages('identity/login'); 
   // Add handlers to specific janrain events 
   janrain.events.onCaptureLoginSuccess.addHandler(successCallback); 
   janrain.events.onModalClose.addHandler(failureCallback); 
};
```

ログアウト

* **finishLogout：認証委任** のログインメソッドに渡されるコールバック。

* **window.Backplane：バックプレーンオブジェクト** への参照。

```
/** 
* Logout function 
* In this case, invalidates the session and removes the cookie. 
* Also reloads the page to change state. In order to do this without a reload, 
* it would be necessary to also update the UI. 
*/ 
authDelegate.logout = function(finishLogout) { 
   Backplane.resetCookieChannel(); 
   janrain.capture.ui.endCaptureSession(); 
   finishLogout(); 
}; 
```

プロファイルの編集

これは、サイトのどの部分にもリンクし、表示が自分のプロファイルページを訪問するようにしたい場合があります。 この例では、渡された作成者オブジェクトを印刷するだけです。

```
/** 
* Edit profile function 
* @param user - User who would like to edit their profile 
*/ 
authDelegate.editProfile = function(user) { 
   console.log(user); 
}; 
```

表示プロファイル

編集プロファイルと同様に、このリンクは現在ログインしているユーザーとは異なるユーザーのページに設定する必要があります。 これは、適切に実装できます。 この例では、コンソールに作成者パラメーターを記録します。

```
/** 
* View profile function 
* @param user - User or userId whose profile should be displayed 
*/ 
authDelegate.viewProfile = function(user) { 
   console.log(author); 
};
```

