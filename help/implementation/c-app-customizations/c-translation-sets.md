---
description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-title: 翻訳セット
solution: Experience Manager
title: 翻訳セット
uuid: 8ba66a61-5520-482a-bc0b-e4f6b57f1744
translation-type: tm+mt
source-git-commit: 366b7248c2f3b6994fa10419599e66fa1c8e5e48

---


# 翻訳セット {#translation-sets}

翻訳セットを使用すると、アプリの代替言語を指定できます。

<!-- 
c_translation_sets.dita
-->

翻訳設定を使用して、様々な言語でアプリをローカライズしたり、Studioの1つの場所から複数のアプリの代替テキストを指定したりします。 例えば、すべてのスペイン語サイトで、すべてのアプリフィールドにスペイン語を使用するように設定できます。 また、テキストを変更して、すべてのフィールドがサイトやネットワークの音声と操作性に一致するようにすることもできます。

Storify 2を除くすべてのアプリに対して翻訳設定を指定できます。 ローカライズ可能なフィールドの詳細については、「文字列をローカライズ [する」を参照してくださ](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md)い。

コメント、ライブブログ、およびチャットは、翻訳セット内で同じ文字列セットを共有します。

ネットワーク、サイト、アプリ、またはAPIを使用する翻訳セットを指定します。

異なるレベルの変換セットは、このパターンに従って互いに上書きされます。

* API変換セットは、任意のレベル（アプリ、ネットワーク、サイト）のすべての変換セットより優先されます。
* アプリ翻訳セットは、ネットワークレベルおよびサイトレベルの翻訳セットよりも優先されます。
* サイトレベルの翻訳セットは、ネットワークレベルの翻訳セットよりも優先されます。

## テキスト文字列の確認 {#c-review-text-strings}

Livefyre Reviews用のテキスト文字列のカスタマイズを参照してください。

このページには、Reviewアプリケーションのカスタマイズに使用できる文字列の一覧と説明が含まれています。 ここに示す文字列は、Livefyreコアアプリのデフォルト文字列に加えて、文字列のカスタマイズに表示される文字列よりも優先されます。 重複が表示される場合は、これらの表に示す文字列がレビューアプリのデフォルトの文字列になります。

* 実装
* レビュー/評価インターフェイス
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* エラー

## 実装 {#section-vsy-1k4-xz}

この機能を実装するには、上書きする文字列の1 ～ 1個のオブジェクトマッピングをJavaScript設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

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

レビューと評価のユーザーインターフェイスで使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
| --------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| ボタン |  |  |
|  | editReviewBtn | レビューの編集 |
|  | reviewBtn | レビューの書き込み |
|  | reviewsClosed | 終了したレビュー |
|  | showReviewBtn | レビューを表示 |
|  | フォロー | 興味がある |
|  | shareText | 私はただレビューを書いただけです。 見ろ！ |
| 評価ツールチップ |  |  |
|  | ratingValues | 配列. デフォルト=[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Excelrent’, ‘Excelrent’]; |
|  |  | 注意：各星の左半分と右半分の両方に同じ名前を割り当てるには、配列内の値を複製する必要があります。 |
| 評価サブパーツ |  |  |
|  | ratingSubpartPlaceholders | 配列. デフォルト = [] |
|  | ratingSubpartTitles | 配列. デフォルト = [] |
|  | reviewStreamTitle | デフォルトでは空白です。 レビューの概要セクションのタイトル。 |
| その他 |  |  |
|  | averageRating | 平均ユーザー評価 |
|  | breakdownHeader | 評価の内訳 |
|  | 役立つ | %s/%sが役に立ちました |
|  | hempluralPlural | %s/%sが役に立ちました |
|  | outOf | / |
|  | ratingType | 星 |

## ストリーム情報 {#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *並べ替え* |  |  |
|  | sortBy | *デフォルトでは空白です。* |
|  | sortHighestRated | [最高評価](https://d.pr/i/huTd) |
|  | sortLowestRated | [最低評価](https://d.pr/i/huTd) |
|  | sortMostHemplive | [最も役に立つ](https://d.pr/i/huTd) |
| *ストリームその他* |  |  |
|  | showMore | 詳細を表示 |
| *高速ストリーム* |  |  |
|  | newComment | 新規レビュー |
|  | newComments | 新しいレビュー |
| *リスナー数* |  |  |
|  | listenerCount | 聞く人 |
|  | listenerCountPlural | 聞く人 |
| *コメント数* |  |  |
|  | commentCountLabel | LiveReviews |
|  | commentCountLabelPlural | LiveReviews |
| *コメント通知数* |  |  |
|  | commentNotifier | 新規レビュー |
|  | commentNotifierPlural | 新しいレビュー |

## 作成者/コンテンツ情報 {#section_osx_xj4_xz}

発言者および個々のコンテンツ情報に関する設定。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *スレッド分割* |  |  |
|  | reviewsContentNotFoundMsg | [このレビューは表示されなくなりました](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション {#section_tlx_wj4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを付け、共有し、役立つものとしてマークする。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *コメントフッター* |  |  |
|  | wasReviewHenvelupe | [役に立つ？](https://d.pr/i/Q0mA) |
|  | wasReviewHenpliceMobile | 役に立つ？ |
|  | ownWasReviewHenpled | [役に立ちました。](https://d.pr/i/Q0mA) |
|  | reviewWasHenvelupe | [○](https://d.pr/i/Q0mA) |
|  | helpDivider | [&amp;vert;](https://d.pr/i/Q0mA) |
|  | reviewWasNotHemple | [×](https://d.pr/i/Q0mA) |
| *投票モーダル* |  |  |
|  | voteTitle | このレビューは役に立ちましたか？ |
|  | voteDownvote | × |
|  | voteReplyTitle | この返事は役に立ちましたか。 |
|  | voteTitle | このコメントは役に立ちましたか？ |
|  | voteUpvote | ○ |
| *フラグモーダル* |  |  |
|  | flagTitle | フラグ%sのレビュー |
|  | flagSuccessMsg | レビューにフラグが付けられました。 |
| *フラグモバイル* |  |  |
|  | flagConfirmationMessage | %sのレビューに%sのフラグを付けますか？ |
| *メンションモーダル* |  |  |
|  | mentionDefaultText | ライブフィレのレビューで言った！ |
| *共有モーダル* |  |  |
|  | shareTitle | レビューを共有 |

## 投稿関数 {#section_yl1_wj4_xz}

レビューを投稿するユーザーが使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *編集者* |  |  |
|  | bodyPlaceholder | レビューの書き込み… |
|  | postEditButton | 編集 |
|  | postEditCancelButton | キャンセル |
|  | postAsButton | レビュー後の形式 |
|  | postButton | レビュー後 |
|  | postReplyAsButton | 投稿… |
|  | postReplyButton | 投稿 |
|  | shareButton | 共有 |
|  | titlePlaceholder | タイトル… |

## エラー {#section_jbc_vj4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| エラー |  |  |
|  | errorAlreadyPosted | レビューは1つだけ投稿できます。 |
|  | errorAuthError | この会話に対するレビューを投稿する権限がありません |
|  | errorCommentsNotAllowed | 現時点ではレビューを投稿できません |
|  | errorDislikeOwnComment | 自分の考えを嫌うことはできない |
|  | errorDuplicate | レビューを好む限り、2回投稿することはできません。 |
|  | errorEditDuplicate | レビューの本文は、編集時に変更する必要があります。 |
|  | errorEditNotAllowed | この会話のレビューを編集することはできません。 |
|  | errorEditTimeExceeded | レビュー編集期間が終了しました。 |
|  | errorEmpty | 空のレビューを投稿しようとしている可能性があります。 |
|  | errorEmptyTitle | 空のタイトルを投稿しようとしているようです |
|  | errorFieldRating | 星評価 |
|  | errorFieldReview | レビュー |
|  | errorFieldTitle | title |
|  | errorMaxChars | レビューが長すぎます。 編集して、もう一度お試しください。 |
|  | errorMissingFields | Please enter a |
|  | errorRatingEmpty | 空の評価を送信することはできません |
|  | errorRatingNotSet | すべての評価を設定する必要があります |
|  | errorRatingNotValid | 評価はオブジェクトである必要があります |
|  | errorShowMore | レビューの読み込み中にエラーが発生しました。 |
|  | errorTitleMaxChars | 申し訳ございません。肩書が長すぎます。 編集して、もう一度お試しください。 |
|  | errorVoteOwnComment | 自分のレビューに対して投票することはできません |

## テキスト文字列を表示 {#c_sidenotes_text_strings}

Livefyreサイドのテキスト文字列のカスタマイズ

<!-- 

c_sidenotes_text_strings.dita

 -->

このページには、サイドアプリのカスタマイズに使用できるすべての文字列の一覧と説明が表示されます。 コアLivefyreアプリで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

* 実装
* 認証
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* モデレーターインターフェイス
* エラー

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
| *認証メニュー文字列* |  |  |
|  | menuAuthSignInBtn | サインイン |
|  | menuAuthSignedInMsg | {action}にサインインする必要があります |
|  | menuUserEditProfile | プロファイルの編集 |
|  | menuUserAdmin | Admin Console |
|  | menuUserLogout | サインアウト |
|  | menuUserBackBtn | すべて |

## ストリーム情報 {#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *情報メニューのオプション* |  |  |
|  | menuInfoCopyright | © Livefyre, Inc. 2014 |
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
|  | datetimeMonths | *配列. Default = *[ ‘January’, ‘February’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘August’, ‘September’, ‘October’, ‘November’, ‘December’ ] |
|  | questionExplation | 文章、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。 <br>テキストをハイライト表示し、アイコンをクリックするか、各段落の末尾にあるアイコンをクリックします。 |
|  | questionMockText | 「親しみ深い」ものは、「親しみ深い」という理由だけで、正しく知られていません。 |
|  | questionTitle | 「サイド」とは |

## ユーザーアクション {#section_qxd_fl4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを付け、共有し、「いいね！」をクリックします。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *返信メニューのオプション* |  |  |
|  | menuRepliesViewTitle | 詳細 |
|  | menuRepliesViewReply | 会話に返信 |
| *共有メニューのオプション* |  |  |
|  | menuShareOptionFacebook | Facebook |
|  | menuShareOptionTwitter | Twitter |
|  | menuShareTitle | 共有 |
| *フラグメニューオプション* |  |  |
|  | menuFlagOptionDisagree | 同意しない |
|  | menuFlagOptionOffense | 不快な |
|  | menuFlagOptionOffTopic | トピック外 |
|  | menuFlagOptionSpam | スパム |
|  | menuFlagTitle | フラグの設定… |
|  | facebookShareCaption | 「{title}」のサイド |
| *モバイルユーザーオプション* |  |  |
|  | sliderCommentTally | of |
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
| *削除メニューオプション* |  |  |
|  | menuConfirmAccept | はい、{action} |
|  | menuConfirmCancel | キャンセル |
|  | menuConfirmTitle | よろしいですか？ |
| *Etcメニューオプション* |  |  |
|  | menuEtcOptionApprove | 承認 |
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
| *「詳細」メニューからの確認メッセージ* |  |  |
|  | notificationApproved | 承認済み |
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
