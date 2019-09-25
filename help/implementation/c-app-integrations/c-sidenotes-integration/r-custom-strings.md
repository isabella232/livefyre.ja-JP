---
description: 'null'
seo-description: 'null'
seo-title: カスタム文字列をサイト化
title: カスタム文字列をサイト化
uuid: 73745273-d3fb-4569-8910-d149fb37a7b4
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# カスタム文字列をサイト化{#sidenotes-custom-strings}

カスタム文字列は、Sidentsコンストラクターに挿入されたオブジェクトを通じて適用され、アプリケーションを通じて使用されるデフォルト文字列を上書きします。 これらは、言語の任意の部分を、スタイルや言語の仕様に合わせてカスタマイズするために使用できます。 文字列は自動的にデフォルトとマージされます。

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
| appName | サイデン |
| commentModeratorTag | Mod |
| commentPendingTag | 保留 |
| commentReadMoreLink | 詳細情報 |
| commentReplyLink | {number}件の返信を参照 |
| commentReplyLinkSing | 「返信」を参照 |
| commentVoteCount | 票 |
| commentVoteCountSing | 件の投票 |
| editorPlaceholder | どう思う？ |
| editorPostBtn | 投稿のサイト |
| editorPostBtnMobile | 投稿 |
| editorPosting | 投稿中… |
| editorReplyBtn | 返信を投稿 |
| editorReplyTitle | 返信の書き込み |
| editorTitle | メモの書き込み |
| emptyImageBlockTxt | どう思う？ |
| emptyTextBlockTxt | + |
| errorConnection | ああ。 君は良い関係がないようだ |
| errorDuplicate | お客様のメモも気に入っていますが、2回投稿することはできません。 |
| errorGeneral | エラーが発生しました. もう一度お試しください。 |
| errorServer | サーバーで問題が発生しました。 もう一度？ |
| facebookShareCaption | "{title}"のサイドノート |
| menuAuthSignedInMsg | {action}にサインインする必要があります |
| menuAuthSignInBtn | サインイン |
| menuBackBtn | 戻る |
| menuConfirmAccept | はい、{action} |
| menuConfirmCancel | キャンセル |
| menuConfirmTitle | よろしいですか？ |
| menuEtcOptionApprove | 承認 |
| menuEtcOptionDelete | 削除 |
| menuEtcOptionEdit | 編集 |
| menuEtcOptionFlag | Flag |
| menuEtcOptionShare | 共有 |
| menuEtcPostedAt | 投稿日： {date} |
| menuEtcTitle | 詳細情報 |
| menuFlagOptionDisagree | 同意しない |
| menuFlagOptionOffense | 不快な |
| menuFlagOptionOffTopic | トピック外 |
| menuFlagOptionSpam | スパム |
| menuFlagTitle | フラグの設定… |
| menuInfoCopyright | © Livefyre, Inc. 2014 |
| menuInfoHelp | ヘルプ |
| menuInfoLivefyreLink | Livefyre.comにアクセス |
| menuRepliesViewReply | 会話に返信 |
| menuRepliesViewTitle | 詳細 |
| menuShareOptionFacebook | Facebook |
| menuShareOptionLink | パーマリンクをコピー |
| menuShareOptionLinkComplete | コピー済み |
| menuShareOptionLinkFailed | コピー失敗 |
| menuShareOptionTwitter | Twitter |
| menuShareTitle | 共有 |
| notificationApproved | 承認済み |
| notificationDeleted | 削除済み |
| notificationFlagged | フラグあり |
| permalinkBackBtn | すべて |
| permalinkTitle | パーマリンク |
| questionExplation | 文章、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。<br><br>テキストをハイライトし、「fycon-write」アイコンをクリックするか、各段落の末尾にある「fycon-action-view」アイコンをクリックします。 |
| questionMockText | 「親しみ深い」ものは、「親しみ深い」という理由だけで、正しく知られていません。 |
| questionTitle | 「サイド」とは |
| queuedCommentsPlural | {number}新しいサイド |
| queuedCommentsSingular | 新しいサイトを1つ |
| queuedRepliesPlural | {number}件の新しい返信 |
| queuedRepliesSingular | 1件の新しい返信 |
| replyBtn | 返信 |
| signInToPost | サインインしてサイドを書き込む |
| sliderCommentTally | of |
| sliderInviteRead | 詳しくは、 |
| sliderInviteWrite | 書き込み |
| sliderWriteText | どう思う？ タップして書き込み |
| threadCollapseBtn | 折りたたみ |
| threadExpandBtnPlural | {number}件の返信を展開 |
| threadExpandBtnSingular | 1件の返信を展開 |
| threadReplyBtn | 会話に返信 |
