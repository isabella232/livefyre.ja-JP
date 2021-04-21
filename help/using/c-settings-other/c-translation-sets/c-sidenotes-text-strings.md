---
description: Livefyreサイト用のテキスト文字列のカスタマイズ
title: テキスト文字列を表示
exl-id: 132a7c8d-10e1-419c-9d79-a40553e70785
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 13%

---

# サイトテキスト文字列{#sidenotes-text-strings}

Livefyreサイト用のテキスト文字列のカスタマイズ

このページのリストと、Sidetsアプリのカスタマイズに使用できるすべての文字列について説明します。 コアLivefyreアプリで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

導入
認証
ストリーム情報
作成者/コンテンツ情報
ユーザーアクション
投稿関数
モデレーターインターフェイス
エラー

## 実装 {#section_wp2_ql4_xz}

この機能を実装するには、オーバーライドする文字列の1 ～ 1個のオブジェクトマッピングをJavaScript設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

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

認証プロセスおよび認証済みユーザーのメニューから使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 認証メニュー文字列 | menuAuthSignInBtn | サインイン |
|  | menuAuthSignedInMsg | {action}にサインインしている必要があります |
|  | menuUserEditProfile | プロファイルの編集 |
|  | menuUserAdmin | Admin Console |
|  | menuUserLogout | サインアウト |
|  | menuUserBackBtn | すべて |

## ストリーム情報{#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 情報メニューのオプション | menuInfoCopyright | © Livefyre, Inc. 2014 |
|  | menuInfoHelp | ヘルプ |
|  | menuInfoLivefyreLink | Livefyre.comにアクセス |

## 作成者/コンテンツ情報{#section_dhb_gl4_xz}

発言者および個々のコンテンツの情報に使用できる文字列です。

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
|  | questionExplation | センテンス、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。<br><br><span class="&rdquo;lf-highlight-text&rdquo;">テ</span> キストをハイライト表示し、 <span class="&rdquo;fycon-write&rdquo;"></span> アイコンをクリックするか、各段落の最後にある <span class="&rdquo;fycon-action-view&rdquo;"></span> アイコンをクリックします。 |
|  | questionMockText | 「よく知られている」ものは、「慣れ親しんでいる」という理由だけで、正しく知られていません。 |
|  | questionTitle | 「サイド」とは |

## ユーザーアクション{#section_qxd_fl4_xz}

ユーザーアクションで使用できる文字列：既存のコンテンツにフラグを付け、共有し、「いいね！」を付けます。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 返信メニューのオプション | menuRepliesViewTitle | 詳細 |
|  | menuRepliesViewReply | 会話に返信 |
| 共有メニューのオプション | menuShareOptionFacebook | Facebook |
|  | menuShareOptionTwitter | Twitter |
|  | menuShareTitle | 共有 |
| フラグメニューのオプション | menuFlagOptionDisagreet | 同意しない |
|  | menuFlagOptionOffense | 攻撃的 |
|  | menuFlagOptionOffTopic | トピックを除外 |
|  | menuFlagOptionSpam | スパム |
|  | menuFlagTitle | フラグの設定… |
|  | facebookShareCaption | 「{title}」上のサイン |
| モバイルユーザーオプション | sliderCommentTally | of |
|  | sliderInviteRead | 詳しくは、 |
|  | sliderInviteWrite | 書き込み |
|  | sliderLoading | ロードしています… |
|  | sliderWriteText | どう思う？ タップして書き込みます。 |

## ポスト関数{#section_xzf_2l4_xz}

コンテンツを投稿するユーザーが使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | editorEditBtn | 保存 |
|  | editorEditPosting | 保存中… |
|  | editorEditReplyTitle | 返信の編集 |
|  | editorEditTitle | サイトを編集 |
|  | editorPlaceholder | どう思う？ |
|  | editorPostBtn | ポストサイド |
|  | editorPostBtnMobile | 投稿 |
|  | editorPosting | 投稿中… |
|  | editorReplyBtn | 返信を投稿 |
|  | editorReplyTitle | Write Reply |
|  | editorTitle | 書き込みサイド |
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

## モデレーターインターフェイス{#section_o5f_dl4_xz}

ユーザー認証モデレーターインターフェイスで使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 「詳細」メニューからの確認メッセージ | notificationApproved | 承認済み |
|  | notificationDeleted | 削除済み |
|  | notificationFlagged | フラグあり |

## エラー {#section_gtk_cl4_xz}

一般的なエラーメッセージに使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | errorConnection | ああ。 良い関係がないようです |
|  | errorDuplicate | メモも気に入っていますが、2回投稿することはできません。 |
|  | errorGeneral | エラーが発生しました. もう一度お試しください。 |
|  | errorServer | サーバーで問題が発生しました。 もう一度やってみる？ |
