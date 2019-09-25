---
description: Sidentのインスタンスでイベントをリッスンできます。
seo-description: Sidentのインスタンスでイベントをリッスンできます。
seo-title: アプリイベントの通知
solution: Experience Manager
title: アプリイベントの通知
uuid: afca4b03-c370-41ca-aa12-45bc357517ca
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934

---


# アプリイベントの通知 {#sidenotes-app-events}

Sidentのインスタンスでイベントをリッスンできます。

コールバックは、メソッドで登録し、メソッ `onmethod` ドで登録を解除することが `removeListener` できます。 コールバック `once` を1回だけ呼び出してから登録を解除する場合は、便利な方法を使用できます。

```
var app = Livefyre.Sidenotes(convConfig); 
   app.once('sidenotes.initialized', function () { 
     // Sidenotes initialized!  
});
```

Livefyreイベントについて詳しくは、リファレンスセクションのJavaScriptイベントページを参照してください。

| キー | 説明 |
|--- |--- |
| sidents.initialized | アプリがインスタンス化され、データが含まれ、ページ上にある場合に実行されます。 |
| sidents.commentFlagged | コメントにフラグが付けられた場合に実行されます。 データの内容： <br><ul><li>`targetId`:フラグ付けされたコメントのID</li><li>`type`:フラグタイプ文字列 `(offensive, off-topic, spam, disagree)`</li></ul> |
| `sidenotes.commentPosted` | コメントが投稿された場合に発行されます。 データの内容： <br><ul><li> `authorId`:コメントの作成者のID </li><li>`bodyHtml`:コメントの本文 </li><li> `parent`:コメントの親のIDまたはnull</li></ul> |
| `sidenotes.commentShared` | コメントが共有されたときに実行されます。 データの内容： <br><ul><li>`targetId`:共有されたコメントのID </li><li> `sharedToFacebook`:コメントがFacebookに共有されたかどうか </li><li>`sharedToTwitter`:コメントがTwitterに共有されたかどうか</li></ul> |
| `sidenotes.commentVoted` | コメントが投票された場合に発行されます。 データの内容： <br><ul><li>`targetId`:投票されたコメントのID </li><li> `targetAuthorId`:投票された発言者のID</li><li> `type`:数値投票タイプ：0:‘clear’, 1:「upvote」または2:「downvote」</li></ul> |
| `sidenotes.userLoggedIn` | ユーザーがログインしたときに呼び出されます。 データの内容： <br><ul><li>`avatar`:ユーザーのアバターURL </li><li>`displayName`:ユーザーの表示名</li><li>`id`:ユーザーのID</li><li> `isModerator`:ユーザーが現在のコレクションのモデレーターかどうか</li></ul> |
| `sidenotes.userLoggedOut` | ユーザーがログアウトしたときに実行されます |
