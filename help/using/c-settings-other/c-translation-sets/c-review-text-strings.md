---
description: Livefyre レビュー用のテキスト文字列のカスタマイズ。
title: テキスト文字列の確認
exl-id: 82ced091-d573-4514-9b91-3451a94ed5d3
source-git-commit: 1d9088eecf797e1af881cb6be55b3c96284f75e5
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 6%

---

# テキスト文字列の確認{#review-text-strings}

Livefyre レビュー用のテキスト文字列のカスタマイズ。

このページでは、Review アプリのカスタマイズに使用できる文字列の一覧と説明を示します。 ここに示す文字列は、Livefyre コアアプリのデフォルト文字列に加えて、文字列のカスタマイズに記載されている文字列を上書きします。 重複がリストされている場合、これらの表にリストされている文字列は、レビューアプリのデフォルトの文字列です。

実装
レビュー/評価インターフェイス
ストリーム情報
作成者/コンテンツ情報
ユーザーアクション
投稿関数
エラー

## 実装 {#section-vsy-1k4-xz}

この機能を実装するには、上書きする文字列の 1 対 1 のオブジェクトマッピングを JavaScript 設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

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

「レビューと評価」ユーザーインターフェイスで使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|--- |--- |--- |
| ボタン | editReviewBtn | レビューの編集 |
|  | reviewBtn | 書き込みレビュー |
|  | reviewsClosed | 終了したレビュー |
|  | showReviewBtn | レビューを表示 |
|  | フォロー | 興味がある |
|  | shareText | 私はただレビューを書いただけです。 見ろ！ |
| 評価のツールチップ | ratingValues | 配列. デフォルト= `[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]`;<br> 注意：配列内の値を複製して、各星の左半分と右半分の両方に同じ名前を割り当てる必要があります。 |
| 評価サブパーツ | ratingSubpartPlaceholders | 配列. デフォルト = `[]` |
|  | ratingSubpartTitles | 配列. デフォルト = `[]` |
|  | reviewStreamTitle | デフォルトでは空白です。 レビューの概要セクションのタイトル。 |
| その他 | averageRating | 平均ユーザー評価 |
|  | breakdownHeader | 評価の分類 |
|  | 参考 | %s / %s が役立ちました |
|  | enverlisePlural | %s / %s が役立ちました |
|  | outOf | / |
|  | ratingType | 星 |

## ストリーム情報 {#section_wmv_yj4_xz}

コンテンツストリームの情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 並べ替え | sortBy | デフォルトでは空白です。 |
|  | sortHighestRated | 最高評価 |
|  | sortLowestRated | 最低評価 |
|  | sortMostAnverlious | 最も役に立つ |
| ストリームのその他 | showMore | 詳細を表示 |
| ストリームの高速度 | newComment | 新規レビュー |
|  | newComments | 新規レビュー |
| リスナー数 | listenerCount | 聞く人 |
|  | listenerCountPlural | 聞く人 |
| コメント数 | commentCountLabel | LiveReviews<strong> | </strong> |
|  | commentCountLabelPlural | LiveReviews<strong> | </strong>%s |
| コメント通知の数 | commentNotifier | 新規レビュー |
|  | commentNotifierPlural | 新規レビュー |

## 作成者/コンテンツ情報 {#section_osx_xj4_xz}

作成者および個々のコンテンツ情報に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| ねじ部分 | reviewsContentNotFoundMsg | このレビューは表示されなくなりました |
|  | backToComments | レビューに戻る |

## ユーザーアクション {#section_tlx_wj4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを付け、共有し、役立つものとしてマークする。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| コメントフッター | wasReviewAnverice | 役に立つ？ |
|  | wasReviewAnvericeMobile | 役に立つ？ |
|  | ownWasReviewAnverice | 役に立ちました。 |
|  | reviewWasAnverice | ○ |
|  | adviledDivider | &amp;vert; |
|  | reviewWasNotAnverice | × |
| 投票モーダル | voteTitle | このレビューは役に立ちましたか？ |
|  | voteDownvote | × |
|  | voteReplyTitle | この返事は役に立ちましたか？ |
|  | voteTitle | このコメントは役に立ちましたか？ |
|  | voteUpvote | ○ |
| フラグモーダル | flagTitle | %s のレビューにフラグを付ける |
|  | flagSuccessMsg | レビューにフラグが設定されました。 |
| モバイルにフラグを設定 | flagConfirmationMessage | %s のレビューに%s のフラグを付けますか？ |
| メンションモーダル | mentionDefaultText | Livefyre のレビューで言及しました！ |
| 共有モーダル | shareTitle | レビューの共有 |

## 投稿関数 {#section_yl1_wj4_xz}

レビューを投稿するユーザーが使用できる文字列です。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 編集者 | bodyPlaceholder | レビューの書き込み… |
|  | postEditButton | 編集 |
|  | postEditCancelButton | キャンセル |
|  | postAsButton | レビュー後の形式 |
|  | postButton | レビュー後 |
|  | postReplyAsButton | 次の形式で投稿… |
|  | postReplyButton | 投稿 |
|  | shareButton | 共有 |
|  | titlePlaceholder | タイトル… |

## エラー {#section_jbc_vj4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| エラー | errorAlreadyPosted | レビューは 1 つだけ投稿できます。 |
|  | errorAuthError | この会話のレビューを投稿する権限がありません |
|  | errorCommentsNotAllowed | 現時点ではレビューを投稿できません |
|  | errorDislikeOwnComment | 自分の批評を嫌うことはできない |
|  | errorDuplicate | レビューを好きなだけ、2 回投稿することはできません。 |
|  | errorEditDuplicate | レビューの本文は、編集時に変更する必要があります。 |
|  | errorEditNotAllowed | この会話のレビューを編集できません。 |
|  | errorEditTimeExceeded | レビューの編集期間が終了しました。 |
|  | errorEmpty | 空のレビューを投稿しようとしています。 |
|  | errorEmptyTitle | 空のタイトルを投稿しようとしているようです |
|  | errorFieldRating | 評価 |
|  | errorFieldReview | レビュー |
|  | errorFieldTitle | title |
|  | errorMaxChars | レビューが長すぎます。 編集して、もう一度やり直してください。 |
|  | errorMissingFields | 入力してください |
|  | errorRatingEmpty | 空の評価を送信することはできません |
|  | errorRatingNotSet | すべての評価を設定する必要があります |
|  | errorRatingNotValid | 評価はオブジェクトである必要があります |
|  | errorShowMore | レビューの読み込み中にエラーが発生しました。 |
|  | errorTitleMaxChars | 申し訳ございませんが、タイトルが長すぎます。 編集して、もう一度やり直してください。 |
|  | errorVoteOwnComment | 自分のレビューで投票することはできません |
