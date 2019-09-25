---
description: Livefyre Reviews用のテキスト文字列のカスタマイズを参照してください。
seo-description: Livefyre Reviews用のテキスト文字列のカスタマイズを参照してください。
seo-title: テキスト文字列の確認
solution: Experience Manager
title: テキスト文字列の確認
uuid: 86251e49-bc73-4eec-9f9b-b4b0a5b42099
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# テキスト文字列の確認{#review-text-strings}

Livefyre Reviews用のテキスト文字列のカスタマイズを参照してください。

このページには、Reviewアプリケーションのカスタマイズに使用できる文字列の一覧と説明が含まれています。 ここに示す文字列は、Livefyreコアアプリのデフォルト文字列に加えて、文字列のカスタマイズに表示される文字列よりも優先されます。 重複が表示される場合は、これらの表に示す文字列がレビューアプリのデフォルトの文字列になります。

ImplementationReview/Rating InterfaceStream infoAuthor/Content infoUser ActionsPost関数エラー

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
|--- |--- |--- |
| ボタン | editReviewBtn | レビューの編集 |
|  | reviewBtn | [レビューの書き込み](https://d.pr/i/QscA) |
|  | reviewsClosed | [終了したレビュー](https://d.pr/i/zr7M) |
|  | showReviewBtn | [レビューを表示](https://d.pr/i/onxU) |
|  | フォロー | 興味がある |
|  | shareText | 私はただレビューを書いただけです。 見ろ！ |
| 評価ツールチップ | ratingValues | 配列. デフォルト= `[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]`; <br>注意：各星の左半分と右半分に同じ名前を割り当てるには、配列内の値を複製する必要があります。 |
| 評価サブパーツ | ratingSubpartPlaceholders | 配列. デフォルト = `[]` |
|  | ratingSubpartTitles | 配列. デフォルト = `[]` |
|  | reviewStreamTitle | デフォルトでは空白です。 レビューの概要セクションのタイトル。 |
| その他 | averageRating | [平均ユーザー評価](https://d.pr/i/QscA) |
|  | breakdownHeader | [評価の内訳](https://d.pr/i/QscA) |
|  | 役立つ | %s/%sが役に立ちました |
|  | hempluralPlural | %s/%sが役に立ちました |
|  | outOf | / |
|  | ratingType | 星 |

## ストリーム情報 {#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 並べ替え | sortBy | デフォルトでは空白です。 |
|  | sortHighestRated | [最高評価](https://d.pr/i/huTd) |
|  | sortLowestRated | [最低評価](https://d.pr/i/huTd) |
|  | sortMostHemplive | [最も役に立つ](https://d.pr/i/huTd) |
| ストリームその他 | showMore | 詳細を表示 |
| 高速ストリーム | newComment | 新規レビュー |
|  | newComments | 新しいレビュー |
| リスナー数 | listenerCount | 聞く人 |
|  | listenerCountPlural | 聞く人 |
| コメント数 | commentCountLabel | LiveReviews<strong> | </strong>%s |
|  | commentCountLabelPlural | LiveReviews<strong> | </strong>%s |
| コメント通知数 | commentNotifier | 新規レビュー |
|  | commentNotifierPlural | 新しいレビュー |

## 作成者/コンテンツ情報 {#section_osx_xj4_xz}

発言者および個々のコンテンツ情報に関する設定。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| スレッド分割 | reviewsContentNotFoundMsg | [このレビューは表示されなくなりました](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション {#section_tlx_wj4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを付け、共有し、役立つものとしてマークする。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| コメントフッター | wasReviewHenvelupe | [役に立つ？](https://d.pr/i/Q0mA) |
|  | wasReviewHenpliceMobile | 役に立つ？ |
|  | ownWasReviewHenpled | [役に立ちました。](https://d.pr/i/Q0mA) |
|  | reviewWasHenvelupe | [○](https://d.pr/i/Q0mA) |
|  | helpDivider | [&amp;vert;](https://d.pr/i/Q0mA) |
|  | reviewWasNotHemple | [×](https://d.pr/i/Q0mA) |
| 投票モーダル | voteTitle | このレビューは役に立ちましたか？ |
|  | voteDownvote | × |
|  | voteReplyTitle | この返事は役に立ちましたか。 |
|  | voteTitle | このコメントは役に立ちましたか？ |
|  | voteUpvote | ○ |
| フラグモーダル | flagTitle | フラグ%sのレビュー |
|  | flagSuccessMsg | レビューにフラグが付けられました。 |
| フラグモバイル | flagConfirmationMessage | %sのレビューに%sのフラグを付けますか？ |
| メンションモーダル | mentionDefaultText | ライブフィレのレビューで言った！ |
| 共有モーダル | shareTitle | レビューを共有 |

## 投稿関数 {#section_yl1_wj4_xz}

レビューを投稿するユーザーが使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 編集者 | bodyPlaceholder | レビューの書き込み… |
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
| エラー | errorAlreadyPosted | レビューは1つだけ投稿できます。 |
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

