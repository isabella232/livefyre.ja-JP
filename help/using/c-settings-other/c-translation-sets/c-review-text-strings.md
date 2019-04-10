---
description: Livefyreレビューのテキスト文字列のカスタマイズ
seo-description: Livefyreレビューのテキスト文字列のカスタマイズ
seo-title: レビューテキスト文字列
solution: Experience Manager
title: レビューテキスト文字列
uuid: 86251e49- bc73-4eec-9f9b9b- b4b0a5b42099
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# レビューテキスト文字列{#review-text-strings}

Livefyreレビューのテキスト文字列のカスタマイズ

このページには、レビューアプリでのカスタマイズに使用できる文字列の一覧と説明が記載されています。ここに示す文字列は、Livefyreコアアプリのデフォルト文字列と、文字列のカスタマイズに一覧表示されているデフォルトの文字列の上書きです。重複がリストされている場合、これらのテーブルに一覧表示されている文字列は、レビューアプリのデフォルトです。

実装レビュー/評価インターフェイスストリーム情報作成者/コンテンツ情報ユーザーアクション投稿関数エラー

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
|--- |--- |--- |
| ボタン | editViewBtn | レビューの編集 |
|  | ReviewBtn | [レビューの書き込み](https://d.pr/i/QscA) |
|  | ReviewSclosed | [レビュー終了](https://d.pr/i/zr7M) |
|  | showReviewBtn | [レビューを表示](https://d.pr/i/onxU) |
|  | フォロー | 関心があること |
|  | ShareText | レビューを作成しました。チェックアウトしてください。 |
| レーティングツールチップ | rateingValues | 配列。Default= `[‘Poor’, ‘Poor’, ‘Fair’, ‘Fair’, ‘Average’, ‘Average’, ‘Good’, ‘Good’, ‘Excellent’, ‘Excellent’]`; <br>注意:各星の左側と右側の両方を同じ名前に割り当てるには、配列内の値を複製する必要があります。 |
| 評価サブパーツ | ragingSubpartPlaceholder | 配列。デフォルト= `[]` |
|  | ragingSubpartTitles | 配列。デフォルト= `[]` |
|  | reviewStreamTitle | デフォルトでは空白です。レビューの概要セクションのタイトル。 |
| Misc | averageSetting | [平均ユーザー評価](https://d.pr/i/QscA) |
|  | breakDownHeader | [評価分類](https://d.pr/i/QscA) |
|  | 役立つ | % s/% sが役に立ちました |
|  | HelpfulMultiple | % s/% sが役に立ちました |
|  | OutOf | / |
|  | rateingType | 星形 |

## ストリーム情報 {#section_wmv_yj4_xz}

コンテンツストリーム情報および表示に使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| 並べ替え | sortBy | デフォルトでは空白です。 |
|  | sortHighestRate | [最高レーティング](https://d.pr/i/huTd) |
|  | sortLoaded | [最低評価](https://d.pr/i/huTd) |
|  | sortOmsful | [最も役に立つ](https://d.pr/i/huTd) |
| ストリームの不一致。 | showMore | 表示を増やす |
| 高速度ストリーム | newComment | 新しいレビュー |
|  | newComments | 新しいレビュー |
| リスナー数 | listenerCount | リスニングするユーザー |
|  | listenerCountMultiple | 訪問者 |
| コメント数 | commentCountLabel | libeReviews<strong> | </strong>% s |
|  | commentCountLabelMultiple | libeReviews<strong> | </strong>% s |
| コメント通知のカウント | CommentNofier | 新しいレビュー |
|  | CommentNoIdentifierMultiple | 新しいレビュー |

## 作成者/コンテンツ情報 {#section_osx_xj4_xz}

作成者および個々のコンテンツ情報に使用できるステリング。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| スレッドアウトアウト | ReviewsContentNotFoundMsg | [このレビューは表示されません](https://d.pr/i/svXs) |
|  | backToComments | レビューに戻る |

## ユーザーアクション {#section_tlx_wj4_xz}

ユーザーアクションで使用できる文字列:フラグ付け、共有、既存のコンテンツの便利なマーク付け。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| コメントフッター | WasreviewPaful | [役に立つか。](https://d.pr/i/Q0mA) |
|  | WasreviewURPfulmobile | 役に立つか。 |
|  | OwnWasReviewPaful | [便利です。](https://d.pr/i/Q0mA) |
|  | ReviewWasful | [はい](https://d.pr/i/Q0mA) |
|  | HelpFulldivider | [& amp;vert;](https://d.pr/i/Q0mA) |
|  | ReviewWasNoSupport | [いいえ](https://d.pr/i/Q0mA) |
| 投票モーダル | videTitle | このレビューは役に立ちましたか。 |
|  | videDown投票 | いいえ |
|  | videePrivacTitle | この返信は役に立ちましたか。 |
|  | videTitle | このコメントは役に立ちましたか。 |
|  | videup投票 | はい |
| フラグモーダル | flagTitle | フラグ% sのレビュー |
|  | flagSuccessMsg | レビューがフラグ付けされました。 |
| Mobile Mobile | flagConfirmationMessage | % sのレビューを% sとしてフラグ付けしますか? |
| メンションモーダル | mentContextDefaultText | Livefyreレビューであなたに問い合わせました。 |
| 共有モーダル | shareTitle | 共有レビュー |

## 投稿関数 {#section_yl1_wj4_xz}

ユーザーがレビューを投稿するために使用できる文字列。

| 要素 | キー | デフォルトテキスト |
|---|---|---|
| エディター | bodyPlaceHolder | レビューの書き込み… |
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
| エラー | errorAlreadyPost | 1つのレビューのみ投稿できます。 |
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

