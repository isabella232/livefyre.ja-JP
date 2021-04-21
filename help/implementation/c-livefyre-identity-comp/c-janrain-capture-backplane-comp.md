---
description: Janrain Captureとバックプレーンを使用しているお客様は、Livefyre Authをシングルサインオン(SSO)用に使用している場合があり、ユーザーはサイトにログインしたときにLivefyre Appsと即座に連携できます。
title: ジャンレインキャプチャ/バックプレーン
exl-id: c7e6cfef-7570-4f9c-9d2c-79f890ee5c49
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 1%

---

# ジャンレインキャプチャ/バックプレーン{#janrain-capture-backplane}

Janrain Captureとバックプレーンを使用しているお客様は、Livefyre Authをシングルサインオン(SSO)用に使用している場合があり、ユーザーはサイトにログインしたときにLivefyre Appsと即座に連携できます。

この組み込みのCapture/Backplane統合のメリットを活かすには、CaptureアプリとLivefyre.js統合の両方に設定を変更する必要があります。

>[!NOTE]
>
>Janrain Captureを使用していない場合は、このセクションをスキップします。

詳しくは、[Janrain’s Backplane documentation](https://developers.janrain.com/how-to/integrations/self-serve-integrations-and-tools/backplane-1-2/)を参照してください。

1. [Captureを設定します。](#c_janrain_capture_backplane/section_r2f_kxt_bbb)
1. （オプション）[追加Livefyreのデフォルトはキャプチャアプリ](#c_janrain_capture_backplane/section_z2s_txt_bbb)です。
1. [AuthDelegateオブジェクトを構築します。](#c_janrain_capture_backplane/section_asv_vyt_bbb)
1. [PingでプルのためにLivefyreと同期します。](#c_janrain_capture_backplane/section_ilv_bzt_bbb)

## 手順1:Captureの設定{#section_r2f_kxt_bbb}

Livefyreには、Janrain Captureアプリからの特定の資格情報が必要です。

1. Janrain Captureアプリを設定します。
1. Livefyreの次の情報を収集します。

   * Janrain Captureインスタンスへのアクセス。
   * ジャンレイン・エンゲージ・ダッシュボードにアクセスします。
   * キャプチャの設定と資格情報。
   * ソーシャル活動の資格情報
   * ID URL。

>[!NOTE]
>
>LivefyreはCNAMEからデータを直接受信します。したがって、このID URLを、Janrain Captureの実際のCNAMEに解決されるCNAMEdレコード（バニティURL CNAME）にすることはできません。

## 手順2:（オプション）追加 Livefyreのデフォルトはキャプチャアプリ{#section_z2s_txt_bbb}です。

Livefyreのデフォルトは、Captureアプリに保存され追加たユーザーです。これにより、ユーザーに電子メール通知を送信したり、ユーザーがコメントする会話を自動的に追跡できるようになります。

1. [手順1:Capture](#c_janrain_capture_backplane/section_r2f_kxt_bbb)を設定します。
1. 追加以下のLivefyreの初期設定フィールド すべてのフィールドはオプションです。

| パラメーター | タイプ | 説明 |
|---|---|---|
| **[!UICONTROL livefyre_comments]** | 文字列 | 記事に対してコメントが行われた場合に、フォローしていることをユーザーに通知します。 即座に、頻繁に、または絶対に指定できます。 |
| **[!UICONTROL livefyre_likes]** | 文字列 | 誰かが自分の投稿の「いいね！」をしたら、ユーザーに通知します。 即座に、頻繁に、または絶対に指定できます。 |
| **[!UICONTROL livefyre_replies]** | 文字列 | ユーザーが自分の投稿の1つに返信したら、そのユーザーに通知します。ただちに通知する、頻繁に送信する、しないいいずれかを指定できます。 |
| **[!UICONTROL livefyre_moderator_comments]** | 文字列 | モデレートしている会話に対してコメントがあったら、モデレーターに通知します。すぐに通知する、頻繁に通知する、しないことができます。 |
| **[!UICONTROL livefyre_moderator_flags]** | 文字列 | モデレートしている会話の投稿にフラグが付いたら、モデレーターに通知します。即時、頻繁または常に通知しないことができます。 |
| **[!UICONTROL livefyre_autofollow_conversations]** | ブール値 | ユーザーが投稿を離れたときに会話を自動フォローするように設定します。 trueまたはfalseに設定できます。 |

## 手順3:Janrain統合用のAuthDelegateオブジェクトの構築{#section_asv_vyt_bbb}

Livefyre.requireは、Janrainバックプレーンバスをリッスンするための認証を有効にするプラグインを提供します。

### ログイン {#login}

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



>[!NOTE]
>
>認証委任は、ジャンレインインスタンスによって異なります。

次に、Janrain Capture統合に対する認証委任の検索例を示します。

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

### 表示プロファイル{#viewprofile}

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

## 手順4:Pingを使用してLivefyreと同期し、Janrainとの統合に使用{#section_ilv_bzt_bbb}

Livefyreリモートプロファイルをキャプチャのユーザー管理システムと同期させておくには、Ping for Pullと呼ばれる一連の手順が必要です。 このプロセスでは、Janrainから有効なアクセストークンを取得し、次の手順3で指定したエンドポイントにそのトークンを渡す必要があります。

1. Janrainからアクセスコードを取得します。

   アクセスコードを取得するには、必要な資格情報を指定し、user_typeを「user」に指定し、uuidを現在のユーザーのuuidに指定して更新します。 詳しくは、[https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/](https://developers.janrain.com/rest-api/methods/authentication/access-codes-and-tokens/getauthorizationcode/)を参照してください。

1. アクセストークンのアクセスコードを交換します。 必要な資格情報と手順1で受け取ったアクセスコードを指定し、grant_typeを「authorization_code」と指定します。

   詳しくは、[https://developers.janrain.com/rest-api/methods/authentication/oauth/token/](https://developers.janrain.com/rest-api/methods/authentication/oauth/token/)を参照してください。

1. Livefyreの「Ping to Pull Capture」エンドポイントを押します。

   エンドポイントURL:[!DNL https://{networkName}/api/v1.1/private/capture/profile_updated/?jrtoken={token}]***{networkName}***&#x200B;はLivefyreから提供されるネットワーク名で、jrtokenは手順2でJanrainから受け取ったトークンです。

   このエンドポイントに到達すると、202応答が返され、Livefyreが非同期プロセスを開始します。

## 仕組み{#concept_mty_f31_2cb}

この組み込みのCapture/Backplane統合のメリットを活かすには、CaptureアプリとLivefyre.js統合の両方に対して設定を変更する必要があります。

Janrainは、バックプレーンバスを通じてログイン/ログアウトの成功メッセージを送信します。このバス上でLivefyre Appが正しく設定されている場合、メッセージをリッスンします。 これらのメッセージには、アプリのユーザーにログインまたはログアウトしたときの表示に必要なすべての情報が含まれます。 開発者は、ブラウザーの開発者コンソールの「Network」タブを調べて、バックプレーンバスメッセージを表示できます。

## ログインコードの例{#section_ftt_tvp_mz}

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

## ログアウトコードの例{#section_t52_svp_mz}

リクエスト:

```
https://backplane1.janrainbackplane.com/v1.2/bus/{CUSTOMER}/channel/new?callback=Backplane.finishInit&amp;rnd=0.1057701709214598
```

応答:

```
Backplane.finishInit("{CHANNEL}");
```

これらのメッセージがネットワークリクエストに表示されない場合、Livefyreはログイン/ログアウトの試行を認識しないので、Livefyreはユーザーをアプリに統合できません。
