---
description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-description: 翻訳セットを使用すると、アプリの代替言語を指定できます。
seo-title: 翻訳セット
solution: Experience Manager
title: 翻訳セット
uuid: 8ba66a61-5520-482a-bc0b-e4f6b57f1744
translation-type: tm+mt
source-git-commit: 366b7248c2f3b6994fa10419599e66fa1c8e5e48
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 7%

---


# 変換セット{#translation-sets}

翻訳セットを使用すると、アプリの代替言語を指定できます。

<!-- 
c_translation_sets.dita
-->

翻訳設定を使用して、様々な言語のアプリをローカライズしたり、Studioの1つの場所から複数のアプリの代替テキストを指定したりします。 例えば、すべてのスペイン語サイトで、すべてのアプリフィールドにスペイン語を使用できます。 また、テキストを変更して、すべてのフィールドがサイトやネットワークの音声と操作性に一致するようにすることもできます。

Storify 2を除くすべてのアプリに対して、翻訳設定を指定できます。 ローカライズできるフィールドの詳細については、[「文字列のローカライズ](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md)」を参照してください。

コメント、ライブブログ、およびチャットは、翻訳セット内で同じ文字列セットを共有します。

ネットワーク、サイト、アプリ、またはAPIを使用した翻訳セットの指定

異なるレベルの変換セットは、次のパターンに従って互いに上書きされます。

* API変換セットは、任意のレベル（アプリ、ネットワーク、サイト）のすべての変換セットより優先されます
* アプリの翻訳セットは、ネットワークレベルおよびサイトレベルの翻訳セットよりも優先されます。
* サイトレベルの翻訳セットは、ネットワークレベルの翻訳セットよりも優先されます。

## レビューテキスト文字列{#c-review-text-strings}

Livefyre Reviews用のテキスト文字列のカスタマイズ

このページのリストと、レビューアプリのカスタマイズで使用できる文字列について説明します。 ここに示す文字列は、Livefyreコアアプリのデフォルトの文字列に加えて、文字列のカスタマイズに一覧表示されている文字列よりも優先されます。 重複が一覧表示される場合、これらの表に示す文字列がレビューアプリのデフォルトです。

* 実装
* レビュー/評価インターフェイス
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* エラー

## 実装 {#section-vsy-1k4-xz}

この機能を実装するには、オーバーライドする文字列の1 ～ 1個のオブジェクトマッピングをJavaScript設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

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

## レビュー/評価インターフェイス{#section_iyv_zj4_xz}

レビューと評価のユーザーインターフェイスで使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
| --------------- | ------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| ボタン |  |  |
|  | editReviewBtn | レビューの編集 |
|  | reviewBtn | 書き込みレビュー |
|  | reviewsClosed | レビュー終了 |
|  | showReviewBtn | レビューを表示 |
|  | フォロー | 興味がある |
|  | shareText | 私はレビューを書いただけです。 見ろ！ |
| 評価ツールチップ |  |  |
|  | ratingValues | 配列. デフォルト= [‘Por’, ‘Por’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excelent’, ‘Excerrent’]; |
|  |  | 注意：各星の左半分と右半分の両方に同じ名前を割り当てるには、配列内の値を複製する必要があります。 |
| 定格サブパーツ |  |  |
|  | ratingSubpartPlaceholders | 配列. デフォルト = [] |
|  | ratingSubpartTitles | 配列. デフォルト = [] |
|  | reviewStreamTitle | デフォルトでは空白です。 レビューの概要セクションのタイトル。 |
| その他 |  |  |
|  | averageRating | 平均ユーザー評価 |
|  | breakdownHeader | 評価の分類 |
|  | 役立つ | %s / %sが役立ちました |
|  | helpPlural | %s / %sが役立ちました |
|  | outOf | / |
|  | ratingType | star |

## ストリーム情報{#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *並べ替え* |  |  |
|  | sortBy | *デフォルトでは空白です。* |
|  | sortHighestRated | [最高評価](https://d.pr/i/huTd) |
|  | sortLowestRated | [最低評価](https://d.pr/i/huTd) |
|  | sortMostHelply | [最も役に立つ](https://d.pr/i/huTd) |
| *その他のストリーム* |  |  |
|  | showMore | 表示を増やす |
| *高速ストリーミング* |  |  |
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

## 作成者/コンテンツ情報{#section_osx_xj4_xz}

発言者および個々のコンテンツの情報に使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *スレッドブレークアウト* |  |  |
|  | reviewsContentNotFoundMsg | [このレビューは表示されなくなります](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション{#section_tlx_wj4_xz}

ユーザーアクションで使用できる文字列：既存のコンテンツにフラグを付けたり、共有したり、役立つとマークを付けたりします。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *コメントフッター* |  |  |
|  | wasReviewHelped | [助けに？](https://d.pr/i/Q0mA) |
|  | wasReviewHenpleMobile | 助けに？ |
|  | ownWasReviewHelpure | [役に立ちました。](https://d.pr/i/Q0mA) |
|  | reviewWasHenple | [○](https://d.pr/i/Q0mA) |
|  | helpDivider | [&amp;vert;](https://d.pr/i/Q0mA) |
|  | reviewWasNotHelp | [×](https://d.pr/i/Q0mA) |
| *投票モーダル* |  |  |
|  | voteTitle | このレビューは役に立ちましたか？ |
|  | voteDownvote | × |
|  | voteReplyTitle | この返信は役に立ちましたか。 |
|  | voteTitle | このコメントは役に立ちましたか？ |
|  | voteUpvote | ○ |
| *フラグモーダル* |  |  |
|  | flagTitle | %sのレビューにフラグを付けます |
|  | flagSuccessMsg | レビューにフラグが付けられました。 |
| *モバイルにフラグ* |  |  |
|  | flagConfirmationMessage | %sのレビューに%sとフラグを付けますか？ |
| *メンションモーダル* |  |  |
|  | mentionDefaultText | Livefyreのレビューで君のことを言った！ |
| *共有モーダル* |  |  |
|  | shareTitle | 共有レビュー |

## ポスト関数{#section_yl1_wj4_xz}

レビューを投稿するユーザーが使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *編集者* |  |  |
|  | bodyPlaceholder | レビューの書き込み… |
|  | postEditButton | 編集 |
|  | postEditCancelButton | キャンセル |
|  | postAsButton | レビュー後のユーザー名 |
|  | postButton | レビュー後 |
|  | postReplyAsButton | 投稿形式… |
|  | postReplyButton | 投稿 |
|  | shareButton | 共有 |
|  | titlePlaceholder | タイトル… |

## エラー {#section_jbc_vj4_xz}

一般的なエラーメッセージに使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| エラー |  |  |
|  | errorAlreadyPosted | レビューを投稿できるのは1つだけです。 |
|  | errorAuthError | この会話に対するレビューを投稿する権限がありません |
|  | errorCommentsNotAllowed | 現時点ではレビューを投稿できません |
|  | errorDislikeOwnComment | 自分の考えを嫌うことはできない |
|  | errorDuplicate | レビューを好む限り、2回投稿することはできません。 |
|  | errorEditDuplicate | レビューの本文は、編集時に変更する必要があります。 |
|  | errorEditNotAllowed | この会話のレビューを編集することはできません。 |
|  | errorEditTimeExceeded | レビュー編集期間が終了しました。 |
|  | errorEmpty | 空のレビューを投稿しようとしている可能性があります。 |
|  | errorEmptyTitle | 空のタイトルを投稿しようとしています |
|  | errorFieldRating | 星評価 |
|  | errorFieldReview | レビュー |
|  | errorFieldTitle | title |
|  | errorMaxChars | レビューが長すぎます。 編集して、もう一度お試しください。 |
|  | errorMissingFields | aを入力してください |
|  | errorRatingEmpty | 空の評価を送信することはできません |
|  | errorRatingNotSet | すべての評価を設定する必要があります |
|  | errorRatingNotValid | 評価はオブジェクトである必要があります |
|  | errorShowMore | それ以上のレビューを読み込む際にエラーが発生しました。 |
|  | errorTitleMaxChars | 申し訳ございません。肩書が長すぎます。 編集して、もう一度お試しください。 |
|  | errorVoteOwnComment | 自分のレビューに対しては投票できません |

## サイトテキスト文字列{#c_sidenotes_text_strings}

Livefyreサイト用のテキスト文字列のカスタマイズ

<!-- 

c_sidenotes_text_strings.dita

 -->

このページのリストと、Sidetsアプリのカスタマイズに使用できるすべての文字列について説明します。 コアLivefyreアプリで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

* 実装
* 認証
* ストリーム情報
* 作成者/コンテンツ情報
* ユーザーアクション
* 投稿関数
* モデレーターインターフェイス
* エラー

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
| *認証メニュー文字列* |  |  |
|  | menuAuthSignInBtn | サインイン |
|  | menuAuthSignedInMsg | {action}にサインインしている必要があります |
|  | menuUserEditProfile | プロファイルの編集 |
|  | menuUserAdmin | Admin Console |
|  | menuUserLogout | サインアウト |
|  | menuUserBackBtn | すべて |

## ストリーム情報{#section_wpy_gl4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *情報メニューのオプション* |  |  |
|  | menuInfoCopyright | © Livefyre, Inc. 2014 |
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
|  | datetimeMonths | *配列. デフォルト= *[ ‘January’, ‘Febrary’, ‘March’, ‘April’, ‘May’, ‘June’, ‘July’, ‘Egustember’, ‘October’, ‘November’, ‘December’ ] |
|  | questionExplation | センテンス、段落、画像、引用符に対するコメントの読み取りと書き込みを直接行えるようになりました。 <br>テキストをハイライト表示し、アイコンをクリックするか、各段落の最後にあるアイコンをクリックします。 |
|  | questionMockText | 「よく知られている」ものは、「慣れ親しんでいる」という理由だけで、正しく知られていません。 |
|  | questionTitle | 「サイド」とは |

## ユーザーアクション{#section_qxd_fl4_xz}

ユーザーアクションで使用できる文字列：既存のコンテンツにフラグを付け、共有し、「いいね！」を付けます。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *返信メニューのオプション* |  |  |
|  | menuRepliesViewTitle | 詳細 |
|  | menuRepliesViewReply | 会話に返信 |
| *共有メニューのオプション* |  |  |
|  | menuShareOptionFacebook | Facebook |
|  | menuShareOptionTwitter | Twitter |
|  | menuShareTitle | 共有 |
| *フラグメニューのオプション* |  |  |
|  | menuFlagOptionDisagreet | 同意しない |
|  | menuFlagOptionOffense | 攻撃的 |
|  | menuFlagOptionOffTopic | トピックを除外 |
|  | menuFlagOptionSpam | スパム |
|  | menuFlagTitle | フラグの設定… |
|  | facebookShareCaption | 「{title}」上のサイン |
| *モバイルユーザーオプション* |  |  |
|  | sliderCommentTally | of |
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

## モデレーターインターフェイス{#section_o5f_dl4_xz}

ユーザー認証モデレーターインターフェイスで使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| *「詳細」メニューからの確認メッセージ* |  |  |
|  | notificationApproved | 承認済み |
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
