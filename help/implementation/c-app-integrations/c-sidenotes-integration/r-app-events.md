---
description: Sideingのインスタンスでイベントをリッスンできます。
seo-description: Sideingのインスタンスでイベントをリッスンできます。
seo-title: アプリイベントを示す
solution: Experience Manager
title: アプリイベントを示す
uuid: afca4b03- c370-41ca- aa12-45bc357517ca
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934

---


# アプリイベントを示す {#sidenotes-app-events}

Sideingのインスタンスでイベントをリッスンできます。

コールバックは `onmethod``removeListener` 、メソッドに登録し、登録解除することができます。この `once` メソッドは、コールバックが1回だけ呼び出されてから未登録の場合に便利です。

```
var app = Livefyre.Sidenotes(convConfig); 
   app.once('sidenotes.initialized', function () { 
     // Sidenotes initialized!  
});
```

Livefyreイベントについて詳しくは、&quot;Reference&quot;セクションのJavaScriptイベントページを参照してください。

| キー | 説明 |
|--- |--- |
| siposing. initialized | アプリケーションがインスタンス化され、データがあり、ページ上にある場合に発生します。 |
| siindes. commentFlag | コメントがフラグ付けされたときに発生します。データには次のものがあります。 <br><ul><li>`targetId`:フラグ付きのコメントのID</li><li>`type`:フラグタイプ文字列 `(offensive, off-topic, spam, disagree)`</li></ul> |
| `sidenotes.commentPosted` | コメントが投稿されたときに発生します。データには次のものがあります。 <br><ul><li> `authorId`:コメントの作成者のID </li><li>`bodyHtml`:コメント本文 </li><li> `parent`:コメントの親のID、またはnull</li></ul> |
| `sidenotes.commentShared` | コメントが共有されたときに発生します。データには次のものがあります。 <br><ul><li>`targetId`:共有されたコメントのID </li><li> `sharedToFacebook`:コメントがFacebookに共有されているかどうか </li><li>`sharedToTwitter`:コメントがTwitterに共有されているかどうか</li></ul> |
| `sidenotes.commentVoted` | コメントが投票されたときに発生します。データには次のものがあります。 <br><ul><li>`targetId`:投票したコメントのID </li><li> `targetAuthorId`:コメントが投票された発言者のID</li><li> `type`:投票タイプ:0:&#39;clear&#39;，1:&#39;up投票&#39;または2:&#39;down投票&#39;</li></ul> |
| `sidenotes.userLoggedIn` | ユーザーがログインすると起動します。データには次のものがあります。 <br><ul><li>`avatar`:ユーザーのアバターURL </li><li>`displayName`:ユーザーの表示名</li><li>`id`:IDのID</li><li> `isModerator`:ユーザーが現在のコレクションのモデレーターかどうか</li></ul> |
| `sidenotes.userLoggedOut` | ユーザーがログアウトしたときに発生する |
