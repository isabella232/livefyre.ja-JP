---
description: Sidentのインスタンスでイベントをリッスンできます。
seo-description: Sidentのインスタンスでイベントをリッスンできます。
seo-title: Sidents Appイベント
solution: Experience Manager
title: Sidents Appイベント
uuid: afca4b03-c370-41ca-aa12-45bc357517ca
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---


# Sidents Appイベント{#sidenotes-app-events}

Sidentのインスタンスでイベントをリッスンできます。

コールバックは`onmethod`に登録でき、`removeListener`メソッドで登録を解除できます。 コールバックを1回だけ呼び出してから登録を解除する場合は、`once`メソッドを使用して便利です。

```
var app = Livefyre.Sidenotes(convConfig); 
   app.once('sidenotes.initialized', function () { 
     // Sidenotes initialized!  
});
```

Livefyreイベントについて詳しくは、リファレンスセクションのJavaScriptイベントページを参照してください。

| キー | 説明 |
|--- |--- |
| sidenotes.initialized | アプリがインスタンス化され、データが含まれ、ページ上にある場合に呼び出されます。 |
| sidenotes.commentFlagged | コメントがフラグ付けされた場合に発生します。 データの内容：<br><ul><li>`targetId`:フラグ付けされたコメントのid</li><li>`type`:フラグタイプ文字列  `(offensive, off-topic, spam, disagree)`</li></ul> |
| `sidenotes.commentPosted` | コメントが投稿されたときに発生しました。 データの内容：<br><ul><li> `authorId`:コメントの作成者のid </li><li>`bodyHtml`:コメントの本文 </li><li> `parent`:コメントの親のidまたはnull</li></ul> |
| `sidenotes.commentShared` | コメントが共有されたときに発生しました。 データの内容：<br><ul><li>`targetId`:共有されたコメントのid </li><li> `sharedToFacebook`:コメントがFacebookに共有されたかどうか </li><li>`sharedToTwitter`:コメントがTwitterに共有されたかどうか</li></ul> |
| `sidenotes.commentVoted` | コメントに対する投票が行われたときに発生しました。 データの内容：<br><ul><li>`targetId`:投票されたコメントのid </li><li> `targetAuthorId`:投票されたコメントの作成者のid</li><li> `type`:数値投票タイプ：0:「clear」、1:「upvote」または2:「downvote」</li></ul> |
| `sidenotes.userLoggedIn` | ユーザーがログインしたときに発生します。 データの内容：<br><ul><li>`avatar`:ユーザーのアバターurl </li><li>`displayName`:ユーザーの表示名</li><li>`id`:ユーザーのID</li><li> `isModerator`:ユーザーが現在のコレクションのモデレーターかどうか</li></ul> |
| `sidenotes.userLoggedOut` | ユーザーがログアウトしたときに発生します |
