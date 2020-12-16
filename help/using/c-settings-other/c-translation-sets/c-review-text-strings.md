---
description: Livefyre Reviews用のテキスト文字列のカスタマイズ
seo-description: Livefyre Reviews用のテキスト文字列のカスタマイズ
seo-title: テキスト文字列の確認
solution: Experience Manager
title: テキスト文字列の確認
uuid: 86251e49-bc73-4eec-9f9b-b4b0a5b42099
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 5%

---


# レビューテキスト文字列{#review-text-strings}

Livefyre Reviews用のテキスト文字列のカスタマイズ

このページのリストと、レビューアプリのカスタマイズで使用できる文字列について説明します。 ここに示す文字列は、Livefyreコアアプリのデフォルトの文字列に加えて、文字列のカスタマイズに一覧表示されている文字列よりも優先されます。 重複が一覧表示される場合、これらの表に示す文字列がレビューアプリのデフォルトです。

導入
レビュー/評価インターフェイス
ストリーム情報
作成者/コンテンツ情報
ユーザーアクション
投稿関数
エラー

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
|--- |--- |--- |
| ボタン | editReviewBtn | レビューの編集 |
|  | reviewBtn | [書き込みレビュー](https://d.pr/i/QscA) |
|  | reviewsClosed | [レビュー終了](https://d.pr/i/zr7M) |
|  | showReviewBtn | [レビューを表示](https://d.pr/i/onxU) |
|  | フォロー | 興味がある |
|  | shareText | 私はレビューを書いただけです。 見ろ！ |
| 評価ツールチップ | ratingValues | 配列. デフォルト= `[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]`;<br>注意：配列内の値を複製して、各星の左半分と右半分の両方に同じ名前を割り当てる必要があります。 |
| 定格サブパーツ | ratingSubpartPlaceholders | 配列. デフォルト = `[]` |
|  | ratingSubpartTitles | 配列. デフォルト = `[]` |
|  | reviewStreamTitle | デフォルトでは空白です。 レビューの概要セクションのタイトル。 |
| その他 | averageRating | [平均ユーザー評価](https://d.pr/i/QscA) |
|  | breakdownHeader | [評価の分類](https://d.pr/i/QscA) |
|  | 役立つ | %s / %sが役立ちました |
|  | helpPlural | %s / %sが役立ちました |
|  | outOf | / |
|  | ratingType | star |

## ストリーム情報{#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 並べ替え | sortBy | デフォルトでは空白です。 |
|  | sortHighestRated | [最高評価](https://d.pr/i/huTd) |
|  | sortLowestRated | [最低評価](https://d.pr/i/huTd) |
|  | sortMostHelply | [最も役に立つ](https://d.pr/i/huTd) |
| その他のストリーム | showMore | 表示を増やす |
| 高速ストリーミング | newComment | 新規レビュー |
|  | newComments | 新しいレビュー |
| リスナー数 | listenerCount | 聞く人 |
|  | listenerCountPlural | 聞く人 |
| コメント数 | commentCountLabel | LiveReviews<strong> | </strong> |
|  | commentCountLabelPlural | LiveReviews<strong> | </strong>%s |
| コメント通知数 | commentNotifier | 新規レビュー |
|  | commentNotifierPlural | 新しいレビュー |

## 作成者/コンテンツ情報{#section_osx_xj4_xz}

発言者および個々のコンテンツの情報に使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| スレッドブレークアウト | reviewsContentNotFoundMsg | [このレビューは表示されなくなります](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション{#section_tlx_wj4_xz}

ユーザーアクションで使用できる文字列：既存のコンテンツにフラグを付けたり、共有したり、役立つとマークを付けたりします。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| コメントフッター | wasReviewHelped | [助けに？](https://d.pr/i/Q0mA) |
|  | wasReviewHenpleMobile | 助けに？ |
|  | ownWasReviewHelpure | [役に立ちました。](https://d.pr/i/Q0mA) |
|  | reviewWasHenple | [○](https://d.pr/i/Q0mA) |
|  | helpDivider | [&amp;vert;](https://d.pr/i/Q0mA) |
|  | reviewWasNotHelp | [×](https://d.pr/i/Q0mA) |
| 投票モーダル | voteTitle | このレビューは役に立ちましたか？ |
|  | voteDownvote | × |
|  | voteReplyTitle | この返信は役に立ちましたか。 |
|  | voteTitle | このコメントは役に立ちましたか？ |
|  | voteUpvote | ○ |
| フラグモーダル | flagTitle | %sのレビューにフラグを付けます |
|  | flagSuccessMsg | レビューにフラグが付けられました。 |
| モバイルにフラグ | flagConfirmationMessage | %sのレビューに%sとフラグを付けますか？ |
| メンションモーダル | mentionDefaultText | Livefyreのレビューで君のことを言った！ |
| 共有モーダル | shareTitle | 共有レビュー |

## ポスト関数{#section_yl1_wj4_xz}

レビューを投稿するユーザーが使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 編集者 | bodyPlaceholder | レビューの書き込み… |
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
| エラー | errorAlreadyPosted | レビューを投稿できるのは1つだけです。 |
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

