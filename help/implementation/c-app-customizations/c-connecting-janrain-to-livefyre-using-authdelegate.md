---
description: Livefyre. requireは、Janrain Callbackバスをリッスンするためのプラグインを提供します。
seo-description: Livefyre. requireは、Janrain Callbackバスをリッスンするためのプラグインを提供します。
seo-title: AuthDelegateを使用してJanfyreにJanrainを接続
title: AuthDelegateを使用してJanfyreにJanrainを接続
uuid: 9d56e3f4-960a-4108- aab5-2795b0e71c88
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# AuthDelegateを使用してJanfyreにJanrainを接続{#connecting-janrain-to-livefyre-using-authdelegate}

Livefyre. requireは、Janrain Callbackバスをリッスンするためのプラグインを提供します。

コールバックチャネルでID/ログインメッセージがブロードキャストされると、ユーザーのLivefyre認証トークンがユーザーに対して呼び出されます。AuthDelegateを実装する必要があります。

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
>window. Callbackオブジェクトは、Livefyreコールバックプラグインを使用してauth. pluginを呼び出す前に、ページ上で定義する必要があります。バックCallbackオブジェクトが使用可能になっていることを確認するには、onReadyコールバックからLivefyreインスタンス化コードを呼び出します。他のアプリケーションがバックCallbackオブジェクトを使用できるかどうかは、Janrainの連絡先に問い合わせて判断してください。

以下は、認証デリゲートがJanrain Captureの統合をどのように探しているかの例です。

>[!NOTE]
>
>認証デリゲートは、JanRainインスタンスによって異なります。

<!--Hannah: Mystery stray bullet found here. Please check against source. -Bob -->

* 認証デリゲートのログインメソッドに渡されるコールバック
* Janrainキャプチャ変数への参照。
* :コールバックオブジェクトへの参照です。

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

* **finishLogout:** 認証デリゲートのログインメソッドに渡されるコールバック。

* **window. Callback:** コールバックオブジェクトへの参照です。

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

プロファイルを編集

これは、ユーザーが自分のプロファイルページを表示するために訪問したいサイトのどの部分にもリンクできます。この例では、渡された作成者オブジェクトを出力するだけです。

```
/** 
* Edit profile function 
* @param user - User who would like to edit their profile 
*/ 
authDelegate.editProfile = function(user) { 
   console.log(user); 
}; 
```

プロファイルを表示

プロファイルの編集と同様、これは現在ログインしているユーザーとは異なるユーザーのページにリンクする必要があります。これは実装できますが、実装できます。この例では、作成者パラメーターをコンソールに記録します。

```
/** 
* View profile function 
* @param user - User or userId whose profile should be displayed 
*/ 
authDelegate.viewProfile = function(user) { 
   console.log(author); 
};
```

