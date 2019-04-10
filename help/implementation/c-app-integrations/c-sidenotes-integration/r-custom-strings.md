---
description: null
seo-description: null
seo-title: カスタム文字列を指定
title: カスタム文字列を指定
uuid: 73745273- d3fb-4569-8910- d149fb37a7b4
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# カスタム文字列を指定{#sidenotes-custom-strings}

カスタム文字列は、Sokesコンストラクターに挿入されたオブジェクトを通して適用され、アプリケーションで使用されるデフォルトの文字列に優先します。これらは、スタイルや言語仕様に合わせて言語の任意の部分をカスタマイズするために使用できます。文字列は自動的にデフォルトと結合されます。

```
var customStrings = { 
   'menuBackBtn': 'return' }; 
new Livefyre.Sidenotes({ 
   strings: customStrings, 
   ...  
});
```

| キー | デフォルト |
|---|---|
| appName | Ssiindes |
| CommentModeratorTag | Mod |
| CommentPendingTag | 保留中 |
| commentReadMoreLink | 詳細情報 |
| commentReplyLink | {number}件の返信を参照 |
| commentReplyLinkSing | 「返信」を参照 |
| commentSearchCount | 投票数 |
| commentSearchCounting | 投票 |
| editorPlaceHolder | どう思いますか。 |
| editorPostBtn | 投稿の開始 |
| editorPostBnMobile | Post |
| editorPosting | 投稿中… |
| editorReplyBtn | 返信の返信 |
| editorReplyTitle | 返信の書き込み |
| editorTitle | メモを記入 |
| EmptyImageBlockSpt | どう思いますか。 |
| EmptyTextBlockTXT | + |
| errorConnection | Uh- oo.適切な接続がないと思われます。 |
| errorDuplicate | メモも同様ですが、2回投稿することはできません。 |
| errorGeneral | エラーが発生しました。再試行してください。 |
| errorServer | サーバーに問題がありました。再試行しますか? |
| facebookShareReption | "{title}"で指定 |
| menuAuthSignInMsg | {action}にサインインしている必要があります |
| menuAuthSignInBtn | サインイン |
| menubackBtn | 戻る |
| menuConfirmAccept | はい、{action} |
| menuConfirmCancel | キャンセル |
| menuConfirmTitle | よろしいですか。 |
| menuetOptionApprove | 承認 |
| menuetOptionDelete | 削除 |
| menuetOptionEdit | 編集 |
| menuetOptionFlag | フラグ |
| menuetOptionShare | 共有 |
| menuetCpostedAt | {date}に投稿 |
| menuGetCtitle | 詳細情報 |
| menuFlagOptionInside | 同意しない |
| menuFlagOption不快 | 不快な不快行為 |
| menuFlagOptionOffTopic | トピックなし |
| menuFlagOptionスパム | スパム |
| menuFlagTitle | フラグの設定 |
| menuInfoCopyright | © Livefyre， Inc.2014 |
| menuInfoHelp | ヘルプ |
| menuInLiativeFyLink | Livefyre.comにアクセス |
| menuRepliesViewReply | 会話への返信 |
| menuRepliesViewTitle | 詳細情報 |
| MenuHareOptionFacebook | Facebook |
| menuHareOptionLink | Permalinkのコピー |
| menuHasOptionLinkComplete | コピー |
| MenuHaveOptionLinkFailed | コピー失敗 |
| MenuHareOptionTwitter | Twitter |
| menusHasTitle | 共有 |
| NotificationApproved | 承認済み |
| NotificationDeleted | 削除済み |
| NotificationFlag | フラグ付き |
| permalLinkbackBtn | すべて |
| permalLinkTitle | Permalink |
| QuestionDescription | 文章、段落、画像、引用符でコメントを直接読み取りおよび書き込みできるようになりました。<br><br>テキストをハイライトし、"fycon- write"アイコンをクリックするか、各段落の最後にある"fycon- action- view"アイコンをクリックします。 |
| QuestionModeText | 「なじみのある」という理由では、適切に認識されません。 |
| QuestionTitle | Sitesizeとは何ですか。 |
| queueCommentsSpural | {number}新しいサイト紹介 |
| queueCommentsSingular | 1つの新しいサイト |
| queueRepliceMultiple | {number}新しい返信 |
| queueRepliceSingular | 1新しい返信 |
| replyBtn | Reply |
| signIntoPost | サインインしてサイトを開く |
| sliderCommentTempt | of |
| sliderInviterAd | 読み取り |
| sliderInviteWrite | 書き込み |
| sliderWriteText | どう思いますか。タップして書き込み |
| ThreadCollapseBtn | 折りたたみ |
| ThreadExpandbtnMultiple | {number}返信を展開 |
| ThreadExpandbtnSingic | "1件の返信」を展開 |
| ThreadReplyBn | 会話への返信 |
