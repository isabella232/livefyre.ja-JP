---
description: 会話アプリ（Comments、Chat、Live Blog、Reviews、Sidenotes など）用に JavaScript をバインドできるものに対して使用できるイベントです。
seo-description: 会話アプリ（Comments、Chat、Live Blog、Reviews、Sidenotes など）用に JavaScript をバインドできるものに対して使用できるイベントです。
seo-title: JavaScriptイベントの定義と例
solution: Experience Manager
title: JavaScriptイベントの定義と例
uuid: 61da2e2e-8fcd-482d-93df-c946f0475277
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# JavaScriptイベントの定義と例{#javascript-events-definitions-and-examples}

会話アプリ（Comments、Chat、Live Blog、Reviews、Sidenotes など）用に JavaScript をバインドできるものに対して使用できるイベントです。

Livefyreは、Livefyreアプリでのユーザーアクティビティを追跡するJavaScriptイベントを提供します。 例えば、ユーザーがTwitterやFacebookにコンテンツを「いいね！」したり共有したりした場合や、新しいコンテンツが投稿された場合に、ページを更新したい場合があります。

また、Livefyreでは、サードパーティの解析統合（Adobe Analytics JS、Google Analytics、Dynamic Tag Managementなど）にイベントを追加して、アプリイベントを追跡することもできます。 詳しくは、サードパーティの統合マネージャーと協力して正しいイベントを指定してください。

これらのイベントに連結するには、ページでアプリをインスタンス化する際に、次のコードをページに追加します。 イベント名を次の名前に置き換えま `{eventName}`す。

```
Livefyre.require(['fyre.conv#3'], function(Conv) { 
   new Conv(networkConfig, [convConfig], function(widget) { 
      widget.on('{eventName}', function (data) { 
         // Do something, perhaps using data 
      }); 
   }); 
});
```

>[!NOTE]
>
>データオブジェクトは、すべてのイベントハンドラーに対して提供されます。 各イベントの後には、サンプルデータオブジェクトが続きます。

## commentPosted {#section_qfr_51p_xz}

ユーザーがコメントを投稿しました。

* nullの親は新しいコメントです。
* 「なし」の親は、編集されたコメントです。
* 親の数値は、返信の親IDです。

```
data = { 
   authorId: "_u2012@livefyre.com" // The ID of the author of the comment  
   parent: "893549"  
      // The ID of the comment that this new comment is in reply to, else null 
   bodyHtml: "<p>42</>" // The HTML of the submitted Content 
   sharedToFacebook:true // Whether the comment was also posted to Facebook 
   sharedToTwitter:false // Whether the comment was also posted to Twitter 
   title: "demo title" // The title of the review (exists only for Reviews) 
   rating: [90] // Array of ratings for the review (exists only for Reviews) 
} 
```

## commentFlagged {#section_szy_s1p_xz}

ユーザーがコメントにフラグを付けました。

```
data = { 
   targetId: "789347" // The ID of the comment that was flagged 
   type: ["disagree"] // The type of flag 
   notes: ["I don't entirely agree with this post"] // A note/reason for the flag 
}
```

## commentLinked {#section_vc1_r1p_xz}

ユーザーがコメントに「いいね！」しました。

```
data = { 
   targetId: "245625" // The ID of the comment that was liked 
   targetAuthorId: "i_am_author@livefyre.com"  
      // The ID of the author of the comment that was liked 
} 
```

## commentShared {#section_nqb_31p_xz}

ユーザーがストリームからコメントを共有しました。 （このイベントは、ユーザーがコメントエディターから共有した場合には実行されません）。このイベントは、「共有」ボタンがクリックされたときにトリガーされます。

```
data = { 
   targetId: "256255" // The ID of the comment that was shared 
   sharedToFacebook:false // Whether the comment was shared to Facebook 
   sharedToTwitter:true // Whether the comment was shared to Twitter 
}
```

## commentCountUpdated {#section_qdq_f1p_xz}

この会話で表示されるコメントの総数が変更されました（増分または減分）。

```
data: 34 // The total number of visible comments in the conversation (integer). 
```

## userLoggedIn {#section_yjt_vz4_xz}

ユーザーがログインしました。

```
data = { 
   avatar: "https://gravatar.com/avatar/50.jpg"  
      // Link to logged in user's avatar image 
   displayName: "NewUser" // Display name of the logged in user 
   id: "newuser@livefyre.com" // ID of the logged in user 
   isModerator:false // Boolean indicating whether logged in user is a moderator 
}
```

## userLoggedOut {#section_tsg_5z4_xz}

ユーザーがログアウトしました。

データが未定義です。

## socialMention {#section_a1w_tz4_xz}

ユーザーがコメントに@メンションを含めました。 次の配列を返します。

```
data = { 
   id: '111111@fb.gw.livefyre.com' // ID of the mentioned user 
   displayName: 'testUser' // Display name of mentioned user 
   message: "@testUser Wow, I can't believe it either!"  
      // Message that was sent to the particular user 
   provider: 'twitter' // Provider to which the mention was shared 
} 
```

## commentFeatured

モデレーターユーザーがコメントを投稿しました。 次の配列を返します。

```
data = { 
   targetId: "134234" // The ID of the comment that was featured 
   targetAuthorId: "i_am_author@livefyre.com"  
      // The ID of the author of the comment that was featured 
}
```

## initialRenderComplete {#section_odc_4z4_xz}

コメントストリームが読み込まれ、最初のコンテンツセットがサーバーから取得され、ユーザーに表示されました。

データが未定義です。

## showMore {#section_pqg_nz4_xz}

ユーザーがボタンをクリッ **[!UICONTROL Show More]** クしました。

データが未定義です。

## userFollowed {#section_xxw_jz4_xz}

ユーザーがボタンをクリックするとtrue **[!UICONTROL Follow]** を返し、ストリームにコンテンツが投稿されるとfalseを返します。

```
data = { 
   id: 'authorId@livefyre.com', 
   optIn: true 
}
```

## userUnfollowed {#section_wm1_gz4_xz}

ユーザーが「フォロー解除」ボタンをクリ **ックすると** 、trueを返し、ストリームにコンテンツが投稿されるとfalseを返します。

```
data = { 
   id: 'authorId@livefyre.com', 
   optOut: true 
}
```

