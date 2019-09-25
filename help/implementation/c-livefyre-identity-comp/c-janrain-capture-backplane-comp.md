---
description: Janrain Captureとバックプレーンを使用するお客様は、Livefyre Auth for Single Sign On(SSO)を使用して、Livefyre Appsをサイトにログインしたときにユーザーがすぐに利用できるようにすることができます。
seo-description: Janrain Captureとバックプレーンを使用するお客様は、Livefyre Auth for Single Sign On(SSO)を使用して、Livefyre Appsをサイトにログインしたときにユーザーがすぐに利用できるようにすることができます。
seo-title: ジャンレインキャプチャ/バックプレーン
solution: Experience Manager
title: ジャンレインキャプチャ/バックプレーン
uuid: 776e9626-db04-4c34-adfe-681a71b552c5
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# ジャンレインキャプチャ/バックプレーン{#janrain-capture-backplane}

Janrain Captureとバックプレーンを使用するお客様は、Livefyre Auth for Single Sign On(SSO)を使用して、Livefyre Appsをサイトにログインしたときにユーザーがすぐに利用できるようにすることができます。

この組み込みのCapture/Backplane統合を利用するには、CaptureアプリとLivefyre.js統合の両方に設定を変更する必要があります。

>[!NOTE]
>
>Janrain Captureを使用していない場合は、この節をスキップしてください。

詳しくは、Janrainのバックプレ [ーンのドキュメントを参照してください](https://developers.janrain.com/how-to/integrations/self-serve-integrations-and-tools/backplane-1-2/)。

1. [Captureを設定します。](#c_janrain_capture_backplane/section_r2f_kxt_bbb)
1. （オプション）Livefyreのデ [フォルトをCaptureアプリに追加します](#c_janrain_capture_backplane/section_z2s_txt_bbb)。
1. [AuthDelegateオブジェクトを作成します。](#c_janrain_capture_backplane/section_asv_vyt_bbb)
1. [引き出し用にPingを使用してLivefyreと同期します。](#c_janrain_capture_backplane/section_ilv_bzt_bbb)

## 手順1:キャプチャの設定 {#section_r2f_kxt_bbb}

Livefyreには、Janrain Captureアプリから特定の資格情報が必要です。

1. Janrain Captureアプリを設定します。
1. Livefyre用に次の情報を収集します。

   * Janrain Captureインスタンスへのアクセス。
   * Janrain Engageダッシュボードにアクセスします。
   * キャプチャの設定と資格情報。
   * ソーシャル資格情報。
   * ID URL。

>[!NOTE]
>
>LivefyreはCNAMEから直接データを受け取ります。したがって、このID URLは、Janrain Captureの実際のCNAMEに解決されるCNAMEdレコード（バニティURL CNAME）にはできません。

## 手順2:（オプション）Livefyreのデフォルト設定をCaptureアプリに追加 {#section_z2s_txt_bbb}

Captureアプリに保存されたユーザーにLivefyreのデフォルトを追加して、ユーザーに電子メール通知を送信したり、ユーザーがコメントする会話を自動的にフォローできるようにします。

1. 手順1 [を完了します。Captureを設定します](#c_janrain_capture_backplane/section_r2f_kxt_bbb)。
1. 次のLivefyreのデフォルトフィールドを追加します。 すべてのフィールドはオプションです。

| パラメーター | タイプ | 説明 |
|---|---|---|
| **[!UICONTROL livefyre_comments]** | 文字列 | 他のユーザーが記事にコメントしたときに、フォローしていることをユーザーに通知します。 即座に、頻繁に、またはないことが可能です。 |
| **[!UICONTROL livefyre_likes]** | 文字列 | 誰かが自分の投稿に「いいね！」をしたら、ユーザーに通知します。 即座に、頻繁に、またはないことが可能です。 |
| **[!UICONTROL livefyre_replies]** | 文字列 | ユーザーが投稿に返信したら通知します。すぐに通知するか、頻繁に通知しないかを指定できます。 |
| **[!UICONTROL livefyre_moderator_comments]** | 文字列 | モデレート中の会話に対してコメントが出たら、モデレーターに通知します。すぐに実行できる場合と、頻繁に実行できない場合があります。 |
| **[!UICONTROL livefyre_moderator_flags]** | 文字列 | モデレート中の会話で投稿にフラグが付いたら、モデレーターに通知します。即時、頻繁、または常に通知しないことができます。 |
| **[!UICONTROL livefyre_autofollow_conversations]** | ブール値 | ユーザーが投稿を離れたときに会話を自動フォローするように設定します。 trueまたはfalseに設定できます。 |

## 手順3:Janrain統合用のAuthDelegateオブジェクトの構築 {#section_asv_vyt_bbb}

Livefyre.requireは、Janrainバックプレーンバスをリッスンするためのプラグインを提供します。

### ログイン {#login}

ID/ログインメッセージがバックプレーンチャネルでブロードキャストされると、ユーザーのLivefyre認証トークンを使用してauth.authenticate()が呼び出されます。 引き続きAuthDelegateを実装する必要があります。

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
>Livefyre Backplaneプラグインを使用してauth.pluginを呼び出す前に、window.Backplaneオブジェクトをページで定義する必要があります。 Backplaneオブジェクトが使用可能であることを確認するには、onReadyコールバックからLivefyreのインスタンス化コードを呼び出します。 Janrainの担当者に問い合わせて、他のアプリケーションがバックプレーンオブジェクトを使用する可能性があるかどうかを確認してください。



>[!NOTE]
>
>認証委任は、10月のインスタンスによって異なります。

次に、認証委任がJanrain Capture統合を検索する例を示します。

* `errback`:認証委任のログインメソッドに渡されるコールバック
* `janrain`:Janrainキャプチャ変数への参照。
* `window.Backplane`:バックプレーンオブジェクトへの参照。

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

### ログアウト {#logout}

* `finishLogout`:認証委任のログインメソッドに渡されるコールバック。

* `window.Backplane`:バックプレーンオブジェクトへの参照。

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

### プロファイルの編集 {#editprofile}

これは、ユーザーが自分のプロファイルページを表示するために訪問したいサイトのどの部分にもリンクできます。 この例では、渡された作成者オブジェクトを印刷するだけです。

```
/** 
* Edit profile function 
* @param user - User who would like to edit their profile 
*/ 
authDelegate.editProfile = function(user) { 
   console.log(user); 
}; 
```

### プロファイルを表示 {#viewprofile}

「プロファイルの編集」と同様に、このリンクは現在ログインしているユーザーとは異なるユーザーのページにリンクする必要があります。 これは、適切に実装できます。 この例では、作成者パラメーターをコンソールに記録します。

```
/** 
* View profile function 
* @param user - User or userId whose profile should be displayed 
*/ 
authDelegate.viewProfile = function(user) { 
   console.log(author); 
};
```

## 手順4:Pingを使用したLivefyreとの同期（Janrain統合のためのプル） {#section_ilv_bzt_bbb}

LivefyreリモートプロファイルをCaptureのユーザー管理システムと同期させておくには、「引き出し用にping」と呼ばれる一連の手順が必要です。 このプロセスでは、Janrainから有効なアクセストークンを取得し、そのトークンを下の手順3で指定したエンドポイントに渡す必要があります。

1. Janrainからアクセスコードを取得します。

   アクセスコードを取得するには、必要な資格情報を指定し、user_typeを「user」に指定し、uuidを更新する現在のユーザーのuuidに指定します。 詳しくは、https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/を参照してく [ださい](https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/)。

1. アクセストークンのアクセスコードを交換します。 必要な資格情報と手順1で受け取ったアクセスコードを指定し、grant_typeを「authorization_code」と指定します。

   詳しくは、https://developers.janrain.com/rest-api/methods/authentication/oauth/token/を参照してく [ださい](https://developers.janrain.com/rest-api/methods/authentication/oauth/token/)。

1. Livefyreの「Ping to Pull Capture」エンドポイントをヒットします。

   エンドポイントURL:ここ [!DNL https://{networkName}/api/v1.1/private/capture/profile_updated/?jrtoken={token}] で、 ****** {networkName}はLivefyreから提供されたネットワーク名で、jrtokenは手順2でJanrainから受け取ったトークンです。

   このエンドポイントに到達すると、202応答を受信し、Livefyreが非同期プロセスを開始します。

## How It All Works {#concept_mty_f31_2cb}

この組み込みのCapture/Backplane統合を利用するには、CaptureアプリとLivefyre.js統合の両方に対して設定を変更する必要があります。

Janrainは、Livefyre appが正しく設定されている場合にリッスンする、バックプレーンバスを通じて、成功したログイン/ログアウトメッセージを送信します。 これらのメッセージには、アプリのユーザーにログインまたはログアウトとして表示するのに必要なすべての情報が含まれます。 開発者は、ブラウザーの開発者コンソールの「Network」タブを調べることで、バックプレーンバスのメッセージを表示できます。

## ログインコードの例 {#section_ftt_tvp_mz}

リクエスト:

```
https://backplane1.janrainbackplane.com//bus/{CUSTOMER_NAME}/channel/{CHANNEL}?callback=Backplane.response&rnd=0.15930617856793106
```

応答:

```
Backplane.response([{ 
  "id": "2014-05-06T22:51:55.406Z-eZp1HB1F7B", 
  "channel_name": "{CHANNEL_NAME}", 
  "message": { 
    "source": "https://{CUSTOMER_DOMAIN}", 
    "type": "identity/login", 
    "sticky": true, 
    "payload": { 
      "context": "https://{CUSTOMER_DOMAIN}", 
      "identities": { 
        "startIndex": 0, 
        "itemsPerPage": 1, 
        "totalResults": 1, 
        "entry": { 
          "id": "https://{CUSTOMER}.janraincapture.com/oauth/public_profile?uuid={UNIQUE_USER_ID}", 
          "displayName": "{USER_DISPLAY_NAME}", 
          "accounts": [ 
            { 
              "username": "{USER_DISPLAY_NAME}", 
              "identityUrl": "https://{CUSTOMER}.janraincapture.com/oauth/public_profile?uuid={UNIQUE_USER_ID}", 
              "photos": [ 
                { 
                  "id": 48570146, 
                  "value": "https://lh3.googleusercontent.com/-h8poqH8hlgw/AAA/AAA1/QuHtbeHMJzc/photo.jpg?sz=50", 
                  "type": "other" 
                }, 
                { 
                  "id": 48570147, 
                  "value": "https://lh3.googleusercontent.com/-h8poqH8hlgw/AAA/AAA1/QuHtbeHMJzc/photo.jpg?sz=50", 
                  "type": "original" 
                }, 
                { 
                  "id": 48570148, 
                  "value": "https://lh3.googleusercontent.com/-h8poqH8hlgw/AAA/AAA1/QuHtbeHMJzc/photo.jpg?sz=50", 
                  "type": "large" 
                }, 
                { 
                  "value": "https://lh3.googleusercontent.com/-h8poqH8hlgw/AAA/AAA1/QuHtbeHMJzc/photo.jpg?sz=50", 
                  "type": "avatar" 
                } 
              ] 
            }, 
            { 
              "identityUrl": "{USER_PROFILE_LINK}" 
            } 
          ] 
        } 
      } 
    } 
  } 
} 
]);
```

空の応答：

```
Backplane.response([]);
```

## ログアウトコードの例 {#section_t52_svp_mz}

リクエスト:

```
https://backplane1.janrainbackplane.com/v1.2/bus/{CUSTOMER}/channel/new?callback=Backplane.finishInit&amp;rnd=0.1057701709214598
```

応答:

```
Backplane.finishInit("{CHANNEL}");
```

これらのメッセージがネットワーク要求に表示されない場合、Livefyreはログイン/ログアウトの試行を認識しないので、Livefyreはユーザーをアプリに統合できません。
