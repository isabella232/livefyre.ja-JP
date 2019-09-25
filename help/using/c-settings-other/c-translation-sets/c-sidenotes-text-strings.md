---
description: Livefyreサイドのテキスト文字列のカスタマイズ
seo-description: Livefyreサイドのテキスト文字列のカスタマイズ
seo-title: テキスト文字列を表示
solution: Experience Manager
title: テキスト文字列を表示
uuid: a3735237-e55d-4bc0-b88d-8a323980ee09
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# テキスト文字列を表示{#sidenotes-text-strings}

Livefyreサイドのテキスト文字列のカスタマイズ

このページには、サイドアプリのカスタマイズに使用できるすべての文字列の一覧と説明が表示されます。 コアLivefyreアプリで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

ImplementationAuthStream infoAuthor / Content infoUser ActionsPost FunctionsModerator InterfaceErrors

## 実装 {#section_wp2_ql4_xz}

この機能を実装するには、上書きする文字列の1 ～ 1個のオブジェクトマッピングをJavaScript設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

例：

```
var customStrings = { 
   postAsButton: "New Post As Text", 
   postEditButton: "New Post Edit Text" 
}; 
networkConfig["strings"] = customStrings; fyre.conv.load( 
   networkConfig, 
   [convConfig], 
   function(){} 
);
```

## Authentication {#section_pqf_3l4_xz}

認証プロセスで使用できる文字列、および認証済みユーザーメニューから使用できます。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 認証メニュー文字列 | menuAuthSignInBtn | サインイン |
|  | menuAuthSignedInMsg | {action}にサインインする必要があります |
|  | menuUserEditProfile | プロファイルの編集 |
|  | menuUserAdmin | Admin Console |
|  | menuUserLogout | サインアウト |
|  | menuUserBackBtn | すべて |

## ストリーム情報 {#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 情報メニューのオプション | menuInfoCopyright | © Livefyre, Inc. 2014 |
|  | menuInfoHelp | ヘルプ |
|  | menuInfoLivefyreLink | Livefyre.comにアクセス |

## 作成者/コンテンツ情報 {#section_dhb_gl4_xz}

発言者および個々のコンテンツ情報に関する設定。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | commentModeratorTag | Mod |
|  | commentPendingTag | 保留 |
|  | commentReadMoreLink | 詳細情報 |
|  | commentReplyLink | {number}件の返信を参照 |
|  | commentReplyLinkSing | 「返信」を参照 |
|  | commentVoteCount | 票 |
|  | commentVoteCountSing | 件の投票 |
|  | datetimeMinutePrefix | m |
|  | datetimeMonths | 配列. デフォルト =`[‘January’, ‘February’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘August’, ‘September’, ‘October’, ‘November’, ‘December’]` |
|  | questionExplation | 文章、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。<br><br><span class="&rdquo;lf-highlight-text&rdquo;">テキストをハイライトし</span> 、各段落 <span class="&rdquo;fycon-write&rdquo;"></span> の最後にあるアイコン <span class="&rdquo;fycon-action-view&rdquo;"></span> をクリックするか、アイコンをクリックします。 |
|  | questionMockText | 「親しみ深い」ものは、「親しみ深い」という理由だけで、正しく知られていません。 |
|  | questionTitle | 「サイド」とは |

## ユーザーアクション {#section_qxd_fl4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを付け、共有し、「いいね！」をクリックします。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 返信メニューのオプション | menuRepliesViewTitle | 詳細 |
|  | menuRepliesViewReply | 会話に返信 |
| 共有メニューのオプション | menuShareOptionFacebook | Facebook |
|  | menuShareOptionTwitter | Twitter |
|  | menuShareTitle | 共有 |
| フラグメニューオプション | menuFlagOptionDisagree | 同意しない |
|  | menuFlagOptionOffense | 不快な |
|  | menuFlagOptionOffTopic | トピック外 |
|  | menuFlagOptionSpam | スパム |
|  | menuFlagTitle | フラグの設定… |
|  | facebookShareCaption | 「{title}」のサイド |
| モバイルユーザーオプション | sliderCommentTally | of |
|  | sliderInviteRead | 詳しくは、 |
|  | sliderInviteWrite | 書き込み |
|  | sliderLoading | ロードしています… |
|  | sliderWriteText | どう思う？ タップして書き込みます。 |

## 投稿関数 {#section_xzf_2l4_xz}

ユーザーがコンテンツを投稿する際に使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | editorEditBtn | 保存 |
|  | editorEditPosting | 保存中… |
|  | editorEditReplyTitle | 返信の編集 |
|  | editorEditTitle | サイトの編集 |
|  | editorPlaceholder | どう思う？ |
|  | editorPostBtn | 投稿のサイト |
|  | editorPostBtnMobile | 投稿 |
|  | editorPosting | 投稿中… |
|  | editorReplyBtn | 返信を投稿 |
|  | editorReplyTitle | 返信の書き込み |
|  | editorTitle | 書き込みサイト |
|  | emptyImageBlockTxt | どう思う？ |
|  | emptyTextBlockTxt | + |
|  | replyBtn | 返信 |
|  | threadReplyBtn | 会話に返信 |
| 削除メニューオプション | menuConfirmAccept | はい、{action} |
|  | menuConfirmCancel | キャンセル |
|  | menuConfirmTitle | よろしいですか？ |
| Etcメニューオプション | menuEtcOptionApprove | 承認 |
|  | menuEtcOptionDelete | 削除 |
|  | menuEtcOptionEdit | 編集 |
|  | menuEtcOptionFlag | Flag |
|  | menuEtcOptionShare | 共有 |
|  | menuEtcPostedAt | 投稿日： {date} |
|  | menuEtcTitle | 詳細情報 |

## モデレーターインターフェイス {#section_o5f_dl4_xz}

ユーザー認証モデレーターインターフェイスで使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 「詳細」メニューからの確認メッセージ | notificationApproved | 承認済み |
|  | notificationDeleted | 削除済み |
|  | notificationFlagged | フラグあり |

## エラー {#section_gtk_cl4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | errorConnection | ああ。 君は良い関係がないようだ |
|  | errorDuplicate | お客様のメモも気に入っていますが、2回投稿することはできません。 |
|  | errorGeneral | エラーが発生しました. もう一度お試しください。 |
|  | errorServer | サーバーで問題が発生しました。 もう一度？ |

