---
title: カスタム文字列を示す
description: カスタム文字列を示す
exl-id: b5e2c18b-5b98-45ff-aa89-dd92a02949a9
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 12%

---

# サイズのカスタム文字列{#sidenotes-custom-strings}

カスタム文字列は、Sidentsコンストラクターに挿入されたオブジェクトを通じて適用され、アプリケーションを通じて使用されるデフォルト文字列を上書きします。 これらは、スタイルや言語の仕様に合わせて言語の任意の部分をカスタマイズするために使用できます。 文字列は自動的にデフォルトと結合されます。

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
| appName | Sidenots |
| commentModeratorTag | Mod |
| commentPendingTag | 保留 |
| commentReadMoreLink | 詳細情報 |
| commentReplyLink | {number}件の返信を参照 |
| commentReplyLinkSing | 「返信」を参照 |
| commentVoteCount | 票 |
| commentVoteCountSing | 件の投票 |
| editorPlaceholder | どう思う？ |
| editorPostBtn | ポストサイド |
| editorPostBtnMobile | 投稿 |
| editorPosting | 投稿中… |
| editorReplyBtn | 返信を投稿 |
| editorReplyTitle | Write Reply |
| editorTitle | メモを書き込む |
| emptyImageBlockTxt | どう思う？ |
| emptyTextBlockTxt | + |
| errorConnection | ああ。 良い関係がないようです |
| errorDuplicate | メモも気に入っていますが、2回投稿することはできません。 |
| errorGeneral | エラーが発生しました. もう一度お試しください。 |
| errorServer | サーバーで問題が発生しました。 もう一度やってみる？ |
| facebookShareCaption | &quot;{title}&quot;のサイドノート |
| menuAuthSignedInMsg | {action}にサインインしている必要があります |
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
| menuFlagOptionDisagreet | 同意しない |
| menuFlagOptionOffense | 攻撃的 |
| menuFlagOptionOffTopic | トピックを除外 |
| menuFlagOptionSpam | スパム |
| menuFlagTitle | フラグの設定… |
| menuInfoCopyright | © Livefyre, Inc. 2014 |
| menuInfoHelp | ヘルプ |
| menuInfoLivefyreLink | Livefyre.comにアクセス |
| menuRepliesViewReply | 会話に返信 |
| menuRepliesViewTitle | 詳細 |
| menuShareOptionFacebook | Facebook |
| menuShareOptionLink | パーマリンクのコピー |
| menuShareOptionLinkComplete | コピー済み |
| menuShareOptionLinkFailed | コピーに失敗しました |
| menuShareOptionTwitter | Twitter |
| menuShareTitle | 共有 |
| notificationApproved | 承認済み |
| notificationDeleted | 削除済み |
| notificationFlagged | フラグあり |
| permalinkBackBtn | すべて |
| permalinkTitle | パーマリンク |
| questionExplation | センテンス、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。<br><br>テキストをハイライト表示し、「fycon-write」アイコンをクリックするか、各段落の最後にある「fycon-action-action」表示をクリックします。 |
| questionMockText | 「よく知られている」ものは、「慣れ親しんでいる」という理由だけで、正しく知られていません。 |
| questionTitle | 「サイド」とは |
| queuedCommentsPlural | {number}新しいサイド |
| queuedCommentsSingular | 1個の新しいサイドポイント |
| queuedRepliesPlural | {number}件の新しい返信 |
| queuedRepliesSingular | 1件の新しい返信 |
| replyBtn | 返信 |
| signInToPost | サインインしてサインマークを書き込む |
| sliderCommentTally | of |
| sliderInviteRead | 詳しくは、 |
| sliderInviteWrite | 書き込み |
| sliderWriteText | どう思う？ タップして書き込み |
| threadCollapseBtn | 折りたたみ |
| threadExpandBtnPlural | {number}件の返信の展開 |
| threadExpandBtnSingular | 1件の返信を展開 |
| threadReplyBtn | 会話に返信 |
