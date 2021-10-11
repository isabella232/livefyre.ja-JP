---
description: 翻訳セットを使用すると、アプリに代替言語を指定できます。
title: 翻訳セット
exl-id: 1de99602-b97e-42e9-8450-39abd4ba2f9b
source-git-commit: 1d9088eecf797e1af881cb6be55b3c96284f75e5
workflow-type: tm+mt
source-wordcount: '1294'
ht-degree: 8%

---

# 翻訳セット{#translation-sets}

翻訳セットを使用すると、アプリに代替言語を指定できます。

翻訳設定を使用して、アプリを様々な言語でローカライズするか、Studio の 1 か所から複数のアプリの代替テキストを指定します。 例えば、すべてのスペイン語のサイトで、すべての「アプリ」フィールドにスペイン語を使用できます。 また、すべてのフィールドがサイトやネットワークの音声と操作性に一致するように、テキストを変更することもできます。

Storify 2 を除くすべてのアプリに対して、翻訳設定を指定できます。 ローカライズ可能なフィールドの詳細については、[ 文字列のローカライズ ](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md#c-localize-strings) を参照してください。

コメント、ライブブログ、チャットは、翻訳セット内で同じ文字列セットを共有します。

ネットワーク、サイト、アプリ、または API を使用して翻訳セットを指定します。

異なるレベルの翻訳セットは、次のパターンに従って互いに上書きされます。

API 翻訳セットは、任意のレベル（アプリ、ネットワーク、サイト）の翻訳セットを上書きします
アプリの翻訳セットは、ネットワークレベルおよびサイトレベルの翻訳セットを上書きします。
サイトレベルの翻訳セットは、ネットワークレベルの翻訳セットよりも優先されます。

## テキスト文字列の確認 {#c_review_text_strings}

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
| 評価サブパーツ | ratingSubpartPlaceholders | 配列. デフォルト = [] |
|  | ratingSubpartTitles | 配列. デフォルト = [] |
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
| 並べ替え | sortBy | *デフォルトでは空白です。* |
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

## Sidenotes テキスト文字列 {#c_sidenotes_text_strings}

Livefyre Sidenotes のテキスト文字列のカスタマイズ

このページでは、Sidenotes アプリでカスタマイズに使用できるすべての文字列を示し、説明します。 コア Livefyre アプリで使用できる文字列について詳しくは、文字列のカスタマイズを参照してください。

実装
認証
ストリーム情報
作成者/コンテンツ情報
ユーザーアクション
投稿関数
モデレーターインターフェイス
エラー

## 実装 {#section_wp2_ql4_xz}

この機能を実装するには、上書きする文字列の 1 対 1 のオブジェクトマッピングを JavaScript 設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

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
|  | menuAuthSignedInMsg | {action} にサインインする必要があります |
|  | menuUserEditProfile | プロファイルの編集 |
|  | menuUserAdmin | Admin Console |
|  | menuUserLogout | サインアウト |
|  | menuUserBackBtn | すべて |

## ストリーム情報 {#section_wpy_gl4_xz}

コンテンツストリームの情報および表示に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 情報メニューのオプション | menuInfoCopyright | © Livefyre, Inc. 2014 |
|  | menuInfoHelp | ヘルプ |
|  | menuInfoLivefyreLink | Livefyre.com にアクセス |

## 作成者/コンテンツ情報 {#section_dhb_gl4_xz}

作成者および個々のコンテンツ情報に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | commentModeratorTag | Mod |
|  | commentPendingTag | 保留 |
|  | commentReadMoreLink | 詳細情報 |
|  | commentReplyLink | {number} 件の返信を参照 |
|  | commentReplyLinkSing | 返信を参照 |
|  | commentVoteCount | 投票 |
|  | commentVoteCountSing | 件の投票 |
|  | datetimeMinutePrefix | m |
|  | datetimeMonths | 配列. デフォルト=[ &#39;January&#39;、&#39;Fubrary&#39;、&#39;March&#39;、&#39;April&#39;、&#39;May&#39;、&#39;June&#39;、&#39;July&#39;、&#39;August&#39;、&#39;September&#39;、&#39;October&#39;、&#39;十一月&#39;、&#39;a1/>] |
|  | questionExplation | 文、段落、画像、引用符に対するコメントの読み取りと書き込みを直接おこなうことができるようになりました。<br><br><span class="&rdquo;lf-highlight-text&rdquo;">テキス</span> トをハイライトし <span class="&rdquo;fycon-write&rdquo;"></span> てアイコンをクリックする <span class="&rdquo;fycon-action-view&rdquo;"></span> か、各段落の最後にあるアイコンをクリックします。 |
|  | questionMockText | 「慣れ親しんでいる」とは、単に「慣れ親しんでいる」という理由だけで、正しく知られていない。 |
|  | questionTitle | Sidefus とは |

## ユーザーアクション {#section_qxd_fl4_xz}

ユーザーアクションに使用できる文字列：既存のコンテンツにフラグを設定、共有、「いいね！」を設定する。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 返信メニューオプション | menuRepliesViewTitle | 詳細 |
|  | menuRepliesViewReply | 会話に返信 |
| 共有メニューオプション | menuShareOptionFacebook | Facebook |
|  | menuShareOptionTwitter | Twitter |
|  | menuShareTitle | 共有 |
| フラグメニューオプション | menuFlagOptionDisagree | 同意しない |
|  | menuFlagOptionOffensing | 攻撃 |
|  | menuFlagOptionOffTopic | トピック外 |
|  | menuFlagOptionSpam | スパム |
|  | menuFlagTitle | フラグの設定… |
|  | facebookShareCaption | Sidenotes(「{title}」) |
| モバイルユーザーオプション | sliderCommentTally | of |
|  | sliderInviteRead | 詳しくは、 |
|  | sliderInviteWrite | 書き込み |
|  | sliderLoading | ロードしています… |
|  | sliderWriteText | どう思う？ タップして書き込みます。 |

## 投稿関数 {#section_xzf_2l4_xz}

ユーザーがコンテンツを投稿する際に使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | editorEditBtn | 保存 |
|  | editorEditPosting | 保存中… |
|  | editorEditReplyTitle | 返信の編集 |
|  | editorEditTitle | サイドを編集 |
|  | editorPlaceholder | どう思う？ |
|  | editorPostBtn | ポスト側面 |
|  | editorPostBtnMobile | 投稿 |
|  | editorPosting | 投稿中… |
|  | editorReplyBtn | 返信を投稿 |
|  | editorReplyTitle | 返信の書き込み |
|  | editorTitle | 書き込みサイド |
|  | emptyImageBlockTxt | どう思う？ |
|  | emptyTextBlockTxt | + |
|  | replyBtn | 返信 |
|  | threadReplyBtn | 会話に返信 |
| 削除メニューオプション | menuConfirmAccept | はい、{action} |
|  | menuConfirmCancel | キャンセル |
|  | menuConfirmTitle | よろしいですか？ |
| Etc メニューオプション | menuEtcOptionApprove | 承認 |
|  | menuEtcOptionDelete | 削除 |
|  | menuEtcOptionEdit | 編集 |
|  | menuEtcOptionFlag | Flag |
|  | menuEtcOptionShare | 共有 |
|  | menuEtcPostedAt | 投稿日： {date} |
|  | menuEtcTitle | 詳細情報 |

## モデレーターインターフェイス {#section_o5f_dl4_xz}

ユーザー認証モデレーターインターフェイスで使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
| 「その他」メニューからの確認メッセージ | notificationApproved | 承認済み |
|  | notificationDeleted | 削除済み |
|  | notificationFlagged | フラグあり |

## エラー {#section_gtk_cl4_xz}

一般的なエラーメッセージに使用できる文字列。

| 要素 | キー | デフォルトのテキスト |
|---|---|---|
|  | errorConnection | ああ。 あなたは良いつながりがないようです。 |
|  | errorDuplicate | 私たちもあなたのメモが好きですが、2 回は投稿できません。 |
|  | errorGeneral | エラーが発生しました. もう一度やり直してください。 |
|  | errorServer | サーバーで問題が発生しました。 もう一度？ |
