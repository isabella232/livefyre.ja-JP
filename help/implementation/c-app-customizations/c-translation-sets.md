---
description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-title: 翻訳セット
solution: Experience Manager
title: 翻訳セット
uuid: 8ba66a61-5520-482a- bc0b- e4f6b57f1744
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 翻訳セット {#translation-sets}

翻訳セットを使用すると、アプリの代替言語を指定できます。

<!-- 
c_translation_sets.dita
-->

翻訳設定を使用して、様々な言語のアプリをローカライズしたり、Studioのある場所から複数のアプリの代替テキストを指定したりできます。例えば、すべてのスペイン語サイトですべてのアプリフィールドにスペイン語を使用することができます。また、すべてのフィールドがサイトやネットワークの音声と雰囲気に一致するようにテキストを変更することもできます。

Storeify2以外のすべてのアプリの翻訳設定を指定できます。ローカライズできるフィールドについて詳しくは、「文字列 [のローカライズ](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md)」を参照してください。

コメント、ライブブログおよびチャットは、翻訳セット内で同じ文字列を共有します。

ネットワーク、サイト、アプリ、またはAPIを使用して、翻訳セットを指定します。

異なるレベルの翻訳セットは、次のパターンに従って互いに上書きします。

* API翻訳セットは、どのレベル（アプリ、ネットワーク、サイト）でも翻訳セットより優先されます。
* アプリ翻訳セットは、ネットワークレベルとサイトレベルの翻訳セットを上書きします。
* サイトレベルの翻訳セットは、ネットワークレベルの翻訳セットを上書きします。

## レビューテキスト文字列 {#c-review-text-strings}

Livefyreレビューのテキスト文字列のカスタマイズ

このページには、レビューアプリでのカスタマイズに使用できる文字列の一覧と説明が記載されています。ここに示す文字列は、Livefyreコアアプリのデフォルト文字列と、文字列のカスタマイズに一覧表示されているデフォルトの文字列の上書きです。重複がリストされている場合、これらのテーブルに一覧表示されている文字列は、レビューアプリのデフォルトです。

* 導入
* レビュー/評価インターフェイス
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* エラー

## 導入 {#section-vsy-1k4-xz}

この機能を実装するには、オーバーライドする文字列の1-1オブジェクトマッピングをJavascript設定オブジェクトに渡します。フィールドを指定しない場合、デフォルトのテキストが使用されます。

例：

```
var customStrings = { 
   postAsButton: "New Post As Text", 
   postEditButton: "New Post Edit Text" }; 
networkConfig["strings"] = customStrings; fyre.conv.load( 
   networkConfig, 
   [convConfig], 
   function(){} 
);
```

## レビュー/評価インターフェイス {#section_iyv_zj4_xz}

レビューおよびレーティングユーザーインターフェイスで使用できる文字列。

| 要素 | キー | デフォルトテキスト |
| --------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| ボタン |  |  |
|  | editViewBtn | レビューの編集 |
|  | ReviewBtn | レビューの書き込み |
|  | ReviewSclosed | レビュー終了 |
|  | showReviewBtn | レビューを表示 |
|  | フォロー | 関心があること |
|  | ShareText | レビューを作成しました。チェックアウトしてください。 |
| レーティングツールチップ |  |  |
|  | rateingValues | 配列。デフォルト=[「不十分」、「不十分」、「公平」、「公平」、「平均」、「平均」、「良好」、「良好」、「優れた」、「優れた」]、 |
|  |  | 注意:各星の左側と右側の両方を同じ名前に割り当てるには、配列内の値を複製する必要があります。 |
| 評価サブパーツ |  |  |
|  | ragingSubpartPlaceholder | 配列。デフォルト=[] |
|  | ragingSubpartTitles | 配列。デフォルト=[] |
|  | reviewStreamTitle | デフォルトでは空白です。レビューの概要セクションのタイトル。 |
| Misc |  |  |
|  | averageSetting | 平均ユーザー評価 |
|  | breakDownHeader | 評価分類 |
|  | 役立つ | % s/% sが役に立ちました |
|  | HelpfulMultiple | % s/% sが役に立ちました |
|  | OutOf | / |
|  | rateingType | 星形 |

## ストリーム情報 {#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *並べ替え* |  |  |
|  | sortBy | *デフォルトでは空白です。* |
|  | sortHighestRate | [最高レーティング](https://d.pr/i/huTd) |
|  | sortLoaded | [最低評価](https://d.pr/i/huTd) |
|  | sortOmsful | [最も役に立つ](https://d.pr/i/huTd) |
| *ストリームの不一致。* |  |  |
|  | showMore | 表示を増やす |
| *高速度ストリーム* |  |  |
|  | newComment | 新しいレビュー |
|  | newComments | 新しいレビュー |
| *リスナー数* |  |  |
|  | listenerCount | リスニングするユーザー |
|  | listenerCountMultiple | 訪問者 |
| *コメント数* |  |  |
|  | commentCountLabel | libeReviews |
|  | commentCountLabelMultiple | libeReviews |
| *コメント通知のカウント* |  |  |
|  | CommentNofier | 新しいレビュー |
|  | CommentNoIdentifierMultiple | 新しいレビュー |

## 作成者/コンテンツ情報 {#section_osx_xj4_xz}

作成者および個々のコンテンツ情報に使用できるステリング。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *スレッドアウトアウト* |  |  |
|  | ReviewsContentNotFoundMsg | [このレビューは表示されません](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション {#section_tlx_wj4_xz}

ユーザーアクションで使用できる文字列:フラグ付け、共有、既存のコンテンツの便利なマーク付け。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *コメントフッター* |  |  |
|  | WasreviewPaful | [役に立つか。](https://d.pr/i/Q0mA) |
|  | WasreviewURPfulmobile | 役に立つか。 |
|  | OwnWasReviewPaful | [便利です。](https://d.pr/i/Q0mA) |
|  | ReviewWasful | [はい](https://d.pr/i/Q0mA) |
|  | HelpFulldivider | [& amp;vert;](https://d.pr/i/Q0mA) |
|  | ReviewWasNoSupport | [いいえ](https://d.pr/i/Q0mA) |
| *投票モーダル* |  |  |
|  | videTitle | このレビューは役に立ちましたか。 |
|  | videDown投票 | いいえ |
|  | videePrivacTitle | この返信は役に立ちましたか。 |
|  | videTitle | このコメントは役に立ちましたか。 |
|  | videup投票 | はい |
| *フラグモーダル* |  |  |
|  | flagTitle | フラグ% sのレビュー |
|  | flagSuccessMsg | レビューがフラグ付けされました。 |
| *Mobile Mobile* |  |  |
|  | flagConfirmationMessage | % sのレビューを% sとしてフラグ付けしますか? |
| *メンションモーダル* |  |  |
|  | mentContextDefaultText | Livefyreレビューであなたに問い合わせました。 |
| *共有モーダル* |  |  |
|  | shareTitle | 共有レビュー |

## 投稿関数 {#section_yl1_wj4_xz}

ユーザーがレビューを投稿するために使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *エディター* |  |  |
|  | bodyPlaceHolder | レビューの書き込み… |
|  | postEditButton | 編集 |
|  | postEditCancelButton | キャンセル |
|  | postAsButton | レビューのレビュー対象 |
|  | postButton | 投稿のレビュー |
|  | postReplayButton | 投稿先… |
|  | postReplyButton | Post |
|  | shareButton | 共有 |
|  | titlePlaceHolder | タイトル… |

## エラー {#section_jbc_vj4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| エラー |  |  |
|  | errorAlreadyPost | 1つのレビューのみ投稿できます。 |
|  | errorAuthError | この会話にはレビューを投稿する権限がありません |
|  | errorCommentSnowAllowed | 現時点ではレビューを投稿できません |
|  | errorDismisseOwnComment | 自分のレビューには気をつけることはできません |
|  | errorDuplicate | レビューを「いいね!"するだけで、2回投稿することはできません。 |
|  | errorEditDuplicate | 編集時にレビューの本文を変更する必要があります。 |
|  | errorEditNotAllowed | この会話ではレビューを編集できません。 |
|  | errorEditTimeExced | レビューの編集期間が有効期限切れです。 |
|  | errorEmpty | 空のレビューを投稿しようとしています。 |
|  | errorEmptyTitle | 空のタイトルを投稿しようとしています |
|  | errorFieldDating | 星レーティング |
|  | errorFieldReview | レビュー |
|  | errorFieldTitle | title |
|  | errorMaxChars | レビューが長すぎます。編集して再試行してください。 |
|  | errorMissingFields | Please enter a |
|  | errorRatingEmpty | 空の評価は送信できません |
|  | errorRatingNotSet | すべてのレーティングを設定する必要があります |
|  | errorRatingNotValid | レーティングはオブジェクトである必要があります |
|  | errorShowMore | レビューの読み込み中にエラーが発生しました。 |
|  | errorTitleMacChars | タイトルが長すぎます。編集して再試行してください。 |
|  | errorVideOwnerComment | 自分のレビューに投票することはできません |

## テキスト文字列を指定 {#c_sidenotes_text_strings}

Livefyre Sosemesのテキスト文字列のカスタマイズ

<!-- 

c_sidenotes_text_strings.dita

 -->

このページでは、アプリのカスタマイズに使用できるすべての文字列を一覧表示し、説明します。Livefyreアプリケーションで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

* 導入
* Auth
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* モデレーターインターフェイス
* エラー

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
| *認証メニュー文字列* |  |  |
|  | menuAuthSignInBtn | サインイン |
|  | menuAuthSignInMsg | {action}にサインインしている必要があります |
|  | menuUserEditProfile | プロファイルを編集 |
|  | menuUserAdmin | 管理コンソール |
|  | menuUserLogout | サインアウト |
|  | menuUserbackBtn | すべて |

## ストリーム情報 {#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *情報メニューオプション* |  |  |
|  | menuInfoCopyright | © Livefyre， Inc.2014 |
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
|  | dataTimeMons | *配列。デフォルト=*[ '1月'、'2月'、'3月'、'4月'、'5月'、'5月'、'月'、'月'、'月'、'11月'、'12月'、'12月' ] |
|  | QuestionDescription | 文章、段落、画像、引用符でコメントを直接読み取りおよび書き込みできるようになりました。<br>テキストをハイライトしてアイコンをクリックするか、各段落の最後にあるアイコンをクリックします。 |
|  | QuestionModeText | 「なじみのある」という理由では、適切に認識されません。 |
|  | QuestionTitle | Sitesizeとは何ですか。 |

## ユーザーアクション {#section_qxd_fl4_xz}

ユーザーアクションで使用できる文字列:既存のコンテンツのフラグ付け、共有、およびいいね!。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| *返信メニューオプション* |  |  |
|  | menuRepliesViewTitle | 詳細情報 |
|  | menuRepliesViewReply | 会話への返信 |
| *共有メニューオプション* |  |  |
|  | MenuHareOptionFacebook | Facebook |
|  | MenuHareOptionTwitter | Twitter |
|  | menusHasTitle | 共有 |
| *フラグメニューオプション* |  |  |
|  | menuFlagOptionInside | 同意しない |
|  | menuFlagOption不快 | 不快な不快行為 |
|  | menuFlagOptionOffTopic | トピックなし |
|  | menuFlagOptionスパム | スパム |
|  | menuFlagTitle | フラグの設定 |
|  | facebookShareReption | "{title}"について |
| *モバイルユーザーオプション* |  |  |
|  | sliderCommentTempt | of |
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
| *メニューオプションの削除* |  |  |
|  | menuConfirmAccept | はい、{action} |
|  | menuConfirmCancel | キャンセル |
|  | menuConfirmTitle | よろしいですか。 |
| *Etcメニューオプション* |  |  |
|  | menuetOptionApprove | 承認 |
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
| *その他メニューからの確認メッセージ* |  |  |
|  | NotificationApproved | 承認済み |
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
