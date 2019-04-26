---
description: Janrain CaptureおよびCallbackを使用するお客様は、シングルサインオン（SSO）にLivefyre Authを使用することができます。これにより、ユーザーはサイトにログインする際に、Livefyreアプリにすぐに関与できます。
seo-description: Janrain CaptureおよびCallbackを使用するお客様は、シングルサインオン（SSO）にLivefyre Authを使用することができます。これにより、ユーザーはサイトにログインする際に、Livefyreアプリにすぐに関与できます。
seo-title: Janrain Capture/Callback
solution: Experience Manager
title: Janrain Capture/Callback
uuid: 776e9626- db04-4c34- adfe-681a71b552c5
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Janrain Capture/Callback{#janrain-capture-backplane}

Janrain CaptureおよびCallbackを使用するお客様は、シングルサインオン（SSO）にLivefyre Authを使用することができます。これにより、ユーザーはサイトにログインする際に、Livefyreアプリにすぐに関与できます。

この組み込みのキャプチャ/バックフィル統合を活用するには、CaptureアプリとLivefyre. jsの統合の両方に設定を変更する必要があります。

>[!NOTE]
>
>Janrain Captureを使用しない場合は、このセクションをスキップしてください。

詳しくは [、Janrainのバックエンドドキュメント](https://developers.janrain.com/how-to/integrations/self-serve-integrations-and-tools/backplane-1-2/)を参照してください。

1. [Captureを設定します。](#c_janrain_capture_backplane/section_r2f_kxt_bbb)
1. （オプション） [LivefyreのデフォルトをCaptureアプリに追加](#c_janrain_capture_backplane/section_z2s_txt_bbb)します。
1. [AuthDelegateオブジェクトを構築します。](#c_janrain_capture_backplane/section_asv_vyt_bbb)
1. [Ping for PullでLivefyreと同期します。](#c_janrain_capture_backplane/section_ilv_bzt_bbb)

## 手順1:キャプチャの設定 {#section_r2f_kxt_bbb}

Livefyreには、Janrain Captureアプリから特定の資格情報が必要です。

1. Janrain Captureアプリを設定します。
1. Livefyreの次の情報を収集します。

   * Janrain Captureインスタンスにアクセスします。
   * Janrain Engingダッシュボードへのアクセス。
   * キャプチャの設定および資格情報。
   * エンゲージメント資格情報。
   * ID URL。

>[!NOTE]
>
>LivefyreはCNAMEからデータを直接受信します。このため、このID URLは、Janrain Captureの実際のCNAMEに解決されるCNAMEレコード（バニティURL CNAME）にすることはできません。

## 手順2:（オプション） LivefyreのデフォルトをCaptureアプリに追加する {#section_z2s_txt_bbb}

デフォルトのLivefyreをCaptureアプリに保存して、ユーザーの電子メール通知を送信したり、ユーザーがコメントを自動的にフォローしたりすることができるようにします。

1. 手順 [1:Captureを設定](#c_janrain_capture_backplane/section_r2f_kxt_bbb)します。
1. 次のLivefyreデフォルトフィールドを追加します。すべてのフィールドはオプションです。

| パラメータ | タイプ | 説明 |
|---|---|---|
| **[!UICONTROL livefyre_comments]** | 文字列 | フォローしている記事に対するコメントをユーザーに通知します。即時、多く、または決して使用できません。 |
| **[!UICONTROL livefyre_likes]** | 文字列 | 誰かが投稿の1つを好むときにユーザーに通知します。即時、多く、または決して使用できません。 |
| **[!UICONTROL livefyre_replies]** | 文字列 | 誰かがその投稿の1つに返信したら、ユーザーに通知します。即時、多くの場合、または何もしないことができます。 |
| **[!UICONTROL livefyre_moderator_comments]** | 文字列 | モデレートの対象となる会話について、誰かがモデレーターにコメントしたときに、モデレーターに通知します。即時、多く、または決して使用できません。 |
| **[!UICONTROL livefyre_moderator_flags]** | 文字列 | モデレートの対象となる会話に対して誰かが投稿にフラグを付けたときに、モデレーターに通知します。即時、多く、または決して使用できません。 |
| **[!UICONTROL livefyre_autofollow_conversations]** | ブール値 | ユーザーが投稿を終了したときに、自動的に会話に従います。trueまたはfalseに設定できます。 |

## 手順3:JanDelegate統合用のAuthDelegateオブジェクトの構築 {#section_asv_vyt_bbb}

Livefyre. requireは、Janrain Callbackバスをリッスンするためのプラグインを提供します。

### ログイン {#login}

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



>[!NOTE]
>
>認証デリゲートは、JanRainインスタンスによって異なります。

以下は、認証デリゲートがJanrain Captureの統合をどのように探しているかの例です。

* `errback`:認証デリゲートのログインメソッドに渡されるコールバック
* `janrain`:Janrainキャプチャ変数への参照。
* `window.Backplane`:コールバックオブジェクトへの参照です。

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

* `finishLogout`:認証デリゲートのログインメソッドに渡されるコールバック。

* `window.Backplane`:コールバックオブジェクトへの参照です。

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

### プロファイルを編集 {#editprofile}

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

### プロファイルを表示 {#viewprofile}

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

## 手順4:Ping for Pull for Pull for Janrain統合のLivefyreと同期 {#section_ilv_bzt_bbb}

Livefyre Remote ProfilesをCaptureユーザー管理システムと同期させるには、Pingと呼ばれる一連の手順をPingと呼びます。このプロセスでは、Janrainから有効なアクセストークンを取得し、そのトークンを手順3で指定したエンドポイントに渡す必要があります。

1. Janrainからアクセスコードを入手します。

   アクセスコードを取得するには、必要な資格情報を指定し、user_ typeを"user"として指定し、現在のユーザーのuuidとしてuuidを更新します。詳しくは、 [https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/](https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/)を参照してください。

1. アクセストークンのアクセスコードをトレードします。必要な資格情報を指定し、手順1から受け取ったアクセスコードを、gant_ typeを"authorizment_ code"と指定します。

   詳しくは、 [https://developers.janrain.com/rest-api/methods/authentication/oauth/token/](https://developers.janrain.com/rest-api/methods/authentication/oauth/token/)を参照してください。

1. Livefyre"Ping to Pull Capture"エンドポイントをヒットします。

   エンドポイントURL: [!DNL https://{networkName}/api/v1.1/private/capture/profile_updated/?jrtoken={token}] ここ ***で、{networkName}は*** Livefyreによって提供されるネットワーク名で、jrtokenは手順2のJanrainから受け取ったトークンです。

   このエンドポイントをヒットすると、202応答が受信され、Livefyreは非同期処理を開始します。

## 仕組み {#concept_mty_f31_2cb}

この組み込みのキャプチャ/バックフィル統合を活用するには、CaptureアプリとLivefyre. jsの統合の両方にいくつかの設定変更を加える必要があります。

正しく設定されているときにLivefyreアプリのコールバックバスでログイン/ログアウトメッセージが正常に送信されるようになりました。これらのメッセージには、アプリユーザーをログインまたはログアウトするために必要なすべての情報が含まれています。開発者は、ブラウザーの開発者コンソールのネットワークタブを調査して、バックスラッシュバスメッセージを表示できます。

## ログインコードの例 {#section_ftt_tvp_mz}

リクエスト:

```
https://backplane1.janrainbackplane.com//bus/{CUSTOMER_NAME}/channel/{CHANNEL}?callback=Backplane.response&rnd=0.15930617856793106
```

回答:

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

空の応答:

```
Backplane.response([]);
```

## ログアウトコードの例 {#section_t52_svp_mz}

リクエスト:

```
https://backplane1.janrainbackplane.com/v1.2/bus/{CUSTOMER}/channel/new?callback=Backplane.finishInit&amp;rnd=0.1057701709214598
```

回答:

```
Backplane.finishInit("{CHANNEL}");
```

これらのメッセージがネットワークリクエストに表示されない場合、Livefyreはログイン/ログアウトの試行を認識しないので、Livefyreはユーザーをアプリケーションに統合できません。
