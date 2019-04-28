---
description: Livefyre Sosemesのテキスト文字列のカスタマイズ
seo-description: Livefyre Sosemesのテキスト文字列のカスタマイズ
seo-title: テキスト文字列を指定
solution: Experience Manager
title: テキスト文字列を指定
uuid: a3735237- e55d-4bc0- b88d-8a323980ee09
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# テキスト文字列を指定{#sidenotes-text-strings}

Livefyre Sosemesのテキスト文字列のカスタマイズ

このページでは、アプリのカスタマイズに使用できるすべての文字列を一覧表示し、説明します。Livefyreアプリケーションで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

実装認証ストリーム情報作成者/コンテンツ情報ユーザーアクション投稿関数モデレーターインターフェイスエラー

## 導入 {#section_wp2_ql4_xz}

この機能を実装するには、オーバーライドする文字列の1-1オブジェクトマッピングをJavascript設定オブジェクトに渡します。フィールドを指定しない場合、デフォルトのテキストが使用されます。

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

## 認証 {#section_pqf_3l4_xz}

認証プロセスで使用できる文字列、および認証済みのユーザーメニューから使用できます。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| 認証メニュー文字列 | menuAuthSignInBtn | サインイン |
|  | menuAuthSignInMsg | {action}にサインインしている必要があります |
|  | menuUserEditProfile | プロファイルを編集 |
|  | menuUserAdmin | 管理コンソール |
|  | menuUserLogout | サインアウト |
|  | menuUserbackBtn | すべて |

## ストリーム情報 {#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| 情報メニューオプション | menuInfoCopyright | © Livefyre， Inc.2014 |
|  | menuInfoHelp | ヘルプ |
|  | menuInLiativeFyLink | Livefyre.comにアクセス |

## 作成者/コンテンツ情報 {#section_dhb_gl4_xz}

作成者および個々のコンテンツ情報に使用できるステリング。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
|  | CommentModeratorTag | Mod |
|  | CommentPendingTag | 保留中 |
|  | commentReadMoreLink | 詳細情報 |
|  | commentReplyLink | {number}件の返信を参照 |
|  | commentReplyLinkSing | 「返信」を参照 |
|  | commentSearchCount | 投票数 |
|  | commentSearchCounting | 投票 |
|  | dataTimeMinutePrefix | m |
|  | dataTimeMons | 配列。デフォルト=`[‘January’, ‘February’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘August’, ‘September’, ‘October’, ‘November’, ‘December’]` |
|  | QuestionDescription | 文章、段落、画像、引用符でコメントを直接読み取りおよび書き込みできるようになりました。<br><br><span class="&rdquo;lf-highlight-text&rdquo;">テキスト</span> をハイライトしてアイコンを <span class="&rdquo;fycon-write&rdquo;"></span> クリックするか、各段落の最後に <span class="&rdquo;fycon-action-view&rdquo;"></span> あるアイコンをクリックします。 |
|  | QuestionModeText | 「なじみのある」という理由では、適切に認識されません。 |
|  | QuestionTitle | Sitesizeとは何ですか。 |

## ユーザーアクション {#section_qxd_fl4_xz}

ユーザーアクションで使用できる文字列:既存のコンテンツのフラグ付け、共有、およびいいね!。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| 返信メニューオプション | menuRepliesViewTitle | 詳細情報 |
|  | menuRepliesViewReply | 会話への返信 |
| 共有メニューオプション | MenuHareOptionFacebook | Facebook |
|  | MenuHareOptionTwitter | Twitter |
|  | menusHasTitle | 共有 |
| フラグメニューオプション | menuFlagOptionInside | 同意しない |
|  | menuFlagOption不快 | 不快な不快行為 |
|  | menuFlagOptionOffTopic | トピックなし |
|  | menuFlagOptionスパム | スパム |
|  | menuFlagTitle | フラグの設定 |
|  | facebookShareReption | &quot;{title}&quot;について |
| モバイルユーザーオプション | sliderCommentTempt | of |
|  | sliderInviterAd | 読み取り |
|  | sliderInviteWrite | 書き込み |
|  | sliderLoading | 読み込み中… |
|  | sliderWriteText | どう思いますか。タップして書き込みます。 |

## 投稿関数 {#section_xzf_2l4_xz}

コンテンツを投稿するために使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
|  | editedEditBtn | 保存 |
|  | editedEditPosting | 保存中… |
|  | editedEditAppTitle | 返信を編集 |
|  | editedEditTitle | サイトビューを編集 |
|  | editorPlaceHolder | どう思いますか。 |
|  | editorPostBtn | 投稿の開始 |
|  | editorPostBnMobile | Post |
|  | editorPosting | 投稿中… |
|  | editorReplyBtn | 返信の返信 |
|  | editorReplyTitle | 返信の書き込み |
|  | editorTitle | Sideesを書き込み |
|  | EmptyImageBlockSpt | どう思いますか。 |
|  | EmptyTextBlockTXT | + |
|  | replyBtn | Reply |
|  | ThreadReplyBn | 会話への返信 |
| メニューオプションの削除 | menuConfirmAccept | はい、{action} |
|  | menuConfirmCancel | キャンセル |
|  | menuConfirmTitle | よろしいですか。 |
| Etcメニューオプション | menuetOptionApprove | 承認 |
|  | menuetOptionDelete | 削除 |
|  | menuetOptionEdit | 編集 |
|  | menuetOptionFlag | フラグ |
|  | menuetOptionShare | 共有 |
|  | menuetCpostedAt | {date}に投稿 |
|  | menuGetCtitle | 詳細情報 |

## モデレーターインターフェイス {#section_o5f_dl4_xz}

ユーザー認証モデレーターインターフェイスで使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| その他メニューからの確認メッセージ | NotificationApproved | 承認済み |
|  | NotificationDeleted | 削除済み |
|  | NotificationFlag | フラグ付き |

## エラー {#section_gtk_cl4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
|  | errorConnection | Uh- oo.適切な接続がないと思われます。 |
|  | errorDuplicate | メモも同様ですが、2回投稿することはできません。 |
|  | errorGeneral | エラーが発生しました。再試行してください。 |
|  | errorServer | サーバーに問題がありました。再試行しますか? |

