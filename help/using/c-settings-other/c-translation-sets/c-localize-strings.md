---
description: Livefyreアプリの文字列のカスタマイズ
seo-description: Livefyreアプリの文字列のカスタマイズ
seo-title: 文字列のローカライズ
solution: Experience Manager
title: 文字列のローカライズ
uuid: c0ab352d-5d3a-45d7- bbd0- aed165835646
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 文字列のローカライズ{#localize-strings}

Livefyreアプリの文字列のカスタマイズ

LivefyreアプリケーションのほとんどのHTML要素のテキスト文字列はカスタマイズできます。これにより、任意の有効なUTF-8文字列に&quot;Post As&quot;ボタン、&quot;Comment Count&quot;テキスト、&quot;Sign In&quot;ボタンなどのレンダリングされたHTML要素のテキストを柔軟に変更できます。この機能を使用して、ストリームの実装に個性を追加したり、ユーザーベースのアプリ内の言語をローカライズしたりします。

* コメント、チャット、ライブブログ

   * [導入](#c-localize-strings/section_im4_224_xz)
   * [アカウントアクセス](#c-localize-strings/section_cm3_d24_xz)
   * [ストリーム情報](#c-localize-strings/section_wx1_c24_xz)
   * [ストリームの並べ替え](#c-localize-strings/section_ih2_124_xz)
   * [コンテンツ情報](#c-localize-strings/section_llv_yd4_xz)
   * [重点コンテンツ](#c-localize-strings/section_gmw_vd4_xz)
   * [テキストエディター](#c-localize-strings/section_ky5_td4_xz)
   * [応答オプション](#c-localize-strings/section_zvt_qd4_xz)
   * [コメント通知](#c-localize-strings/section_qqt_pd4_xz)
   * [エラーメッセージ](#c-localize-strings/section_omz_jxn_xz)

* [時刻と日付形式](#c-localize-strings/section_yz4_g5n_xz)
* [メディアウォール](#c-localize-strings/section_vwt_d5n_xz)
* [マップ](#c-localize-strings/section_fxv_c5n_xz)
* [モザイク](#c-localize-strings/section_e2s_b5n_xz)
* [カルーセル](#c-localize-strings/section_l2z_hkn_xz)
* [Feature Card](#c-localize-strings/section_mw2_hkn_xz)
* [ポール](#c-localize-strings/section_pdg_fwh_xz)
* [Livefyre ID](#c-localize-strings/section_zc3_xvh_xz)
* 詳細情報:
   * [レビューテキスト文字列](/help/using/c-settings-other/c-translation-sets/c-review-text-strings.md#c_review_text_strings)
   * [Ssiindes](/help/using/c-settings-other/c-translation-sets/c-sidenotes-text-strings.md#c_sidenotes_text_strings)

## 導入 {#section_im4_224_xz}

この機能を実装するには、オーバーライドする文字列の1-1オブジェクトマッピングをJavaScript設定オブジェクトに渡します。フィールドを指定しない場合、デフォルトのテキストが使用されます。

例：

```
var customStrings = {     
   postAsButton: "New Post As Text",     
   postEditButton: "New Post Edit Text"  
};   
   convConfig["strings"] = customStrings; fyre.conv.load(     
   networkConfig,     
   [convConfig],     
   function(){}  
);
```

このページには、Livefyre Coreアプリケーション用にカスタマイズできるすべてのテキスト文字列が一覧表示されます。

## アカウントアクセス {#section_cm3_d24_xz}

認証プロセスで使用できる文字列、および認証済みのユーザーメニューから使用できます。

![](assets/strings_threadheader-150x40.png)

| 要素 | キー | デフォルトテキスト |
|---|---|---|
|  | displayName | % s |
|  | editProfile | プロファイルの編集 |
|  | NotificationSettings | 通知設定 |
|  | siteAdmin | 管理コンソール（Studioへのリンク） |
|  | signOut | サインアウト |

## ストリーム情報 {#section_wx1_c24_xz}

コンテンツストリーム情報および表示に使用できる文字列。訪問者の数、アプリへの投稿数、ユーザーがログインしたり、アカウント情報にアクセスしたりできます。

| キー | デフォルトテキスト | ストリームデータ |
|---|---|---|
|  | commentCountLabelZero | % sコメント |
|  | commentCountLabel | % sコメント |
|  | commentCountLabelMultiple | % sコメント |
|  | listenerCount | リスニングするユーザー |
|  | listenerCountMultiple | 訪問者 |
|  | liveBlogpostCountLabelZero | post |
|  | liveBlogpostCountLabel | post |
|  | LiveBlogpostCountLabelMultiple | post |
| スレッドオプション | ThreadBreakoutButton | スレッド全体を表示 |
|  | toggleCollapse | 折りたたみを切り替え |
| 速度/キューに登録されたコメント | 更新 | 更新 |
|  | newComment | 新しいコメント |
|  | newComments | 新しいコメント |
|  | newReply | 新しい返信 |
|  | newReplies | 新しい返信 |

## ストリームの並べ替え {#section_ih2_124_xz}

年齢または人気度で返されたコンテンツを並べ替えることができます。

![](assets/strings_newestoldesttop-1-150x56.png)

| キー | デフォルトテキスト | ヘッダーオプション |
|---|---|---|
|  | sortNew | 新機能 |
|  | sortToDesest | 最も古い |
|  | sortToComments | 上位のコメント |
|  | sortHTThreads | ホットスレッド |
|  | sortSeparator |  |  |
|  | streamSort | ロード中 |
|  | topCommentsContentNotFoundMsg | まだ「いいね!&quot;が足りません。 |
|  | hotThreadsContentNotFoundMsg | まだスレッドが足りません。 |
|  | streamRefreshMsg | 新機能を参照してください。 |
| フッターオプション | archiveHeaderTitle | アーカイブから |
|  | archiveShowMore | 表示を増やす |
|  | showMore | コメントをさらに表示 |
|  | showMorelveBlog | 投稿の表示 |

![](assets/strings_threadend-150x47.png)

## コンテンツ情報 {#section_llv_yd4_xz}

投稿情報を一覧表示します。ユーザー名、適用されたユーザータグ、および投稿時間。

![](assets/strings_authorinfo-150x52.png)  ![](assets/strings_posttime-150x45.png)

| キー | デフォルトテキスト | 作成者 |
|---|---|---|
|  | モデレーター | モデレーター |
|  | hoverCardViewProfile | フルプロファイルを表示 |
| 投稿情報 | TimeJustNow | 今すぐ |
|  | TimeMinutesago | 分前 |
|  | TimeMinuteSageMultiple | 分前 |
|  | Timehoursago | 1時間前 |
|  | timeThoursPageMultiple | 時間前まで |
|  | Timedaysago | 日前 |
|  | TimedaysgoMultiple | 日前 |
|  | kicesMultiple | いいね! |
|  | kicesUsingular | いいね! |
|  | moderatorEditTimestamp | モデレーターによる編集 |
|  | commentTomBray | このコメントは削除されました |
|  | permalInNotFoundMsg | このコメントは表示されなくなりました。 |
|  | QuickProfileTooltip | クイックプロファイル |

## 重点コンテンツ {#section_gmw_vd4_xz}

有効な場合、特集コンテンツはストリームの上部に表示されます。

|  | キー | デフォルトテキスト |
|---|---|---|
| 特集ラベル |  |  |
| ![](assets/strings_featuredcontent-150x40.png) | featureCommentsTag | 重点的 |
|  | featureCommentMatchleMultiple | 重点コメント |

## テキストエディター {#section_ky5_td4_xz}

デフォルトでは、すべてのユーザーに対してページの上部に使用できます。

![](assets/strings_texteditor-1-150x77.png)

|  | キー | デフォルトテキスト |
|---|---|---| 
| エディターボタン | フォロー | +フォロー |
|  | フォロー解除 | - フォロー解除 |
|  | liveBLogフォロー | ライブブログに従う |
|  | liveBlogunフォロー | ライブブログのフォロー解除 |
|  | postButton（ログインユーザーに使用可能） | コメントを投稿 |
|  | postAsButton（未認証ユーザーに使用可能） | コメントを投稿する… |
|  | postEditButton | コメントを編集 |
|  | postEditAsButton | コメントを編集する… |
|  | postEditCancelButton | キャンセル |
|  | editorDisabled | この会話は現在、新しいコメントには閉じられています。 |
| チャットオプション | LiveCatatButtonLabel | Post |
|  | liveCatalogEditButton | 編集 |
|  | LiveCatasWindows | Ctrl+ Enterキーを押して投稿 |
|  | LiveCatalogInstructions | Command+ Enterキーを押して投稿 |

## 応答オプション {#section_zvt_qd4_xz}

特に記載されていない限り、ログインユーザー全員が使用できます。コンテンツパネルにマウスポインターを置いてアクセスします。

![](assets/strings_banusermodal-150x36.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| User Response Options | エンドユーザーに使用できます。 |  |
| flagButton | フラグ |
|  | flagCommentToolTip | フラグ |
|  | EditButton（有効になっている場合は作成者およびモデレーターにのみ使用可能） | 編集 |
|  | deleteButton（有効になっている場合は作成者およびモデレーターにのみ使用可能） | 削除 |
|  | deleteCommenttoolTip | 削除 |
|  | shareButton | 共有 |
|  | ShareCommentToolTip | 共有 |
|  | keepButton | いいね! |
|  | unkequeButton | 異なり |
|  | replyButton | Reply |
|  | replyButtonSingular（チャットおよびライブブログで使用可能） | Reply |
|  | replyButtonMultiple（チャットおよびライブブログで使用可能） | 返信 |

![](assets/strings_responseoptions-150x35.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| フラグモーダル | flagTitle | フラグ% sのコメント |
|  | フラグ字幕 | フラグフラグ |
|  | flagDefaultSelectOption | 選択 |
|  | flagスパム | スパム |
|  | flagSPamButton | スパム |
|  | flagSPAMCommentToolTip | スパム |
|  | フラグ付き攻撃 | 不快な不快行為 |
|  | flagOffacterButton | 不快な不快行為 |
|  | flagOffacterCommentCommenttoolTip | 不快な不快行為 |
|  | flagInfix | 同意しない |
|  | flagDisAgreeButton | 同意しない |
|  | flagDisAgreementCommenttoolTip | 同意しない |
|  | flagOffTopic | トピックなし |
|  | flagOffTopicButton | トピックなし |
|  | flagOffToPictureCommentToolTip | トピックなし |
|  | flagEmail | 電子メール |
|  | flagEmailPlaceHolder | you@example.com |
|  | FlagNotes | メモ |
|  | flagNotesPlaceHolder | ここに入力してください… |
|  | flagConfirmButton | OK |
|  | flagCancelButton | キャンセル |
|  | flagConfirmationMessage | % sのコメントを% sとしてフラグ付けしますか? |
|  | flagSuccessMsg | コメントがフラグ付けされました。 |

![](assets/strings_flagmodal-150x87.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| 共有モーダル | shareTitle | 共有コメント |
|  | sharePlaceholderText | どう思いますか。 |
|  | shareLabel | 共有: |
|  | ShareTextTwitter | blank |
|  | shareTextFacebook | blank |
|  | ShareTextLinkedIn | blank |
|  | ShareButtonText | 共有 |
|  | SharePermLink | Permalink |
|  | loadingPermLink | 短いURLをロード中… |
|  | ShareText | コメントを投稿しました。チェックアウトしてください。 |

![](assets/strings_sharemodal-150x59.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| Replyモーダル | postReplayButton | コメントを投稿する… |
|  | postReplyButton（ログインユーザーに使用可能） | コメントを投稿 |
|  | backToHotThreads | ホットスレッドに戻る |

![](assets/strings_backto-150x48.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| Twitter@メンションモーダル | mentOnTitle | 共有メンション |
|  | mentOnSubtitletWidter | ツイートを共有: |
|  | mentContextDefaultText | Livefyreコメントであなたに問い合わせました。 |
|  | mentOnlyConfirmButton | OK |
|  | mentOnCancelButton | キャンセル |
|  | mentOnErrorGeneral | Os!問題が発生しました。Livefyreは警告されました。 |
|  | mentOnErrorNonesSelected | 少なくとも1つのメンションが有効になっている必要があります。 |
|  | mentMenuUtilspace | 友達を確認して言及するには |
|  | mentOnTwitterConnect | Twitterに接続 |
|  | mentOnTwitterRetriing | 友達の取得中… |
|  | mentOnSuccessMsg | メンションは正常に送信されました。 |

![](assets/strings_sharemention-150x60.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| モーダルを編集 | Studio管理者、ユーザーマネージャーまたはモデレーターが利用可能 |  |
| @（@メンション） | &lt;/&gt;（カスタムHTMLウィンドウを開きます）。 |  |
|  | customHTMLDialogTitle（モーダルのヘッダーとして表示） | カスタムHTMLの追加 |

![](assets/strings_moderatoreditmodal-150x49.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| モデレーター応答オプション | Studio管理者、ユーザーマネージャーまたはモデレーターが使用できます。 |  |
| pendingComment | 保留中 |
|  | banUserButton | 禁止ユーザー |
|  | bandUserToolTip | Ban User |
|  | boZoButton | Boszo |
|  | bozoCommentToolTip | Boszo |
|  | featureButton | 機能 |
|  | featureRecommendIcon | 機能 |
|  | UnfeatureButton | 機能不能 |
|  | featureCommentToolTip | 機能不能 |

![](assets/strings_adminoptions-150x33.png)

| キー | デフォルトテキスト |  |
|---|---|---|
| Bun Userモーダル | Studio管理者、ユーザーマネージャーまたはモデレーターが使用できます。 |  |
| bantitlle | Ban User |  |
|  | bandConfirmation | このユーザーを禁止しますか。 |
|  | bageConfirmButton | OK |
|  | banceCellButton | キャンセル |

## コメント通知 {#section_qqt_pd4_xz}

有効になっている場合は、すべてのLivefyre会話アプリのページ下部にあります。

![](assets/strings_notifier-150x112.png)

|  | キー | デフォルトテキスト |
|---|---|---|
| 通知ラベル | CommentNofier | 新しいコメント |
|  | CommentNoIdentifierMultiple | 新しいコメント |
|  | LiveBlogNoNofier | 新しい投稿 |
|  | LiveBlogNoIdentifierMultiple | 新しい投稿 |

## エラーメッセージ {#section_omz_jxn_xz}

カスタマイズ可能なエラーメッセージに使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| errorAuthError | この会話にコメントを投稿する権限がありません |
| errorCommentSnowAllowed | コメントはこの会話では使用できません |
| errorDefault | エラーが発生しました。再試行してください。 |
| errorDuplicate | コメントを「いいね!&quot;するだけで、2回投稿することはできません。 |
| errorEditDuplicate | コメントの本文を編集するときは、本文を変更する必要があります。 |
| errorEditNotAllowed | この会話に対するコメントの編集は許可されていません。 |
| errorEditTimeExced | コメント編集期間が有効期限切れです。 |
| errorEmpty | 空のコメントを投稿しようとしています。 |
| errorExpired | セッションの有効期限が切れました。ページを再読み込みしてください。 |
| errorFlagNotSelected | フラグタイプを選択してください。 |
| errorGuestLiked | アカウントを持つユーザーのみがコンテンツを好みます。 |
| errorInsufficientPermissions | 権限の不十分 |
| errorInvalidChar | 無効な文字を投稿しようとしています。 |
| errorLikeOwnComment | 独自のコメントを使用することはできません |
| errorFormat | 誤ったコンテンツを投稿しようとしています。 |
| errorMaxChars | コメントが長すぎます。編集して再試行してください。 |
| errorMediaNotAvailable | メディアが表示されなくなりました。 |
| errorShowMore | コメントの読み込み中にエラーが発生しました。 |
| multipleMediaNotAllowedError | 権限では、一度に1つのメディア添付ファイルのみを付与します。 |

## 時刻と日付形式 {#section_yz4_g5n_xz}

視覚化アプリケーション内でのコンテンツカードの日付の表示形式を変換してカスタマイズします。

| キー | デフォルトテキスト |
|---|---|
| Hoursago | {number} h |
| hoursMagoSingic | {number} h |
| JustNow | 1s |
| Minuteago | {number} m |
| minutegageSingic | {number} m |
| MonthDayFormat | {day}{MonthableV} |
| MonthDayyeyFormat | {day}{MonthableV}{year} |
| MonthNames | 1月、2月、3月、4月、5月、7月、8月、8月、10月、11月、12月 |
| MonthNameTaskV | Jan、Feb、Mar、Apr、May、Jun、Jul、Aug、Sep、Oct、Nov、Dec |
| Secondsago | {number} s |
| secondsameComplex | {number} s |

## メディアウォール {#section_vwt_d5n_xz}

Mediaウォールアプリで使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| featureText | 重点的 |
| ShareButtonText | 共有 |

| キー | デフォルトテキスト |
|---|---|
| postButtonText | どうしたらいいですか。 |
| postModalTitle | コメントを投稿 |
| postModalButton | コメントを投稿 |
| postModalPlaceHolder | 何を言いますか。 |
| showMoreButtonText | もっとロード |
| ShareButtonText | 共有 |

## マップ {#section_fxv_c5n_xz}

マップで使用可能な文字列。

| キー | デフォルトテキスト |
|---|---|
| featureText | 重点的 |
| ShareButtonText | 共有 |

## モザイク {#section_e2s_b5n_xz}

モザイクに使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| featureText | 重点的 |
| ShareButtonText | 共有 |

## カルーセル {#section_l2z_hkn_xz}

カルーセルで使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| featureText | 重点的 |
| ShareButtonText | 共有 |

## Feature Card {#section_mw2_hkn_xz}

機能カードで使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| featureText | 重点的 |
| ShareButtonText | 共有 |

## アプリをアップロード {#section_grc_gkn_xz}

アプリのアップロードで使用できる文字列。

| キー | デフォルトテキスト |
|---|---|
| postButtonText | どうしたらいいですか。 |
| postModalTitle | コメントを投稿 |
| postModalButton | コメントを投稿 |
| postModalTitlePlaceHolder | タイトルを入力する |
| postModalPlaceHolder | 何を言いますか。 |
| postModalConfirtionTitle | 投稿していただきありがとうございます。 |
| postModalConfirmationMessage | 投稿がレビュー中です。 |
| postModalConfirmationButton | Done |
| title |  |
| message |  |
| editorErrorAttachmentsRequired | 添付ファイルが必要です |
| editorErrorBody | メッセージを追加してください |
| editorErrorDuplicate | メモが必要なだけで、 |
| editorErrorGeneric | エラーが発生しました |
| editorErrorTitleRequired | タイトルが必要です |

## ポール {#section_pdg_fwh_xz}

ポールで使用可能な文字列。

| キー | デフォルトテキスト |
|---|---|
| totalVoesLabel | 合計得票数% s |
| shareStringText | 投票を% sに投票しましたか。 |
| pollClosedLabel | このポールは現在閉じています |

## Livefyre ID {#section_zc3_xvh_xz}

Livefyre IDで使用できる文字列。

| キー | デフォルトテキスト |
|--- |--- |
| automaticallyForCostations | 結合した会話に自動的に従う |
| back | 戻る |
| bio | プロフィール |
| create | 作成 |
| CreateANWAccount | 新規アカウントの作成 |
| CreateNewAccountWithEmail | 電子メールでの新しいアカウントの作成 |
| ChangeAvar | アバターの変更 |
| ChooseFile | ファイルの選択 |
| completeAccount | コンプリートアカウント |
| emailWhenSomeeResies | ユーザーが自分に返信したときに電子メールが送信される |
| EmailCommentsNew | フォローする会話でコメントを電子メールで送信する |
| emailsenttoSetPassword | 電子メールが送信されました。パスワードをリセットするためのリンクを受信者に確認してください |
| emailVerificationSent | 電子メールの検証送信 |
| firstName | 名 |
| forgPassword | パスワードを忘れた場合 |
| forgourPassword | パスワードを忘れた場合 |
| forgoourPasswordInstructions | ユーザ名または電子メールアドレスを下に入力して、パスワードを変更するためのリンクを送信します。 |
| formInputCloseButtonText | 閉じる |
| formInputCancelButtonText | キャンセル |
| formInputSaveButtonText | 保存 |
| hasNotLeftInComments | コメントを残さない |
| locationIsFrom | 次の場所から |
| labelAvar | アバター |
| labelComments | コメント |
| labelConfirmNewPassword | 新しいパスワードの確認 |
| labelConfirmPassword | パスワードの確認 |
| labelEmail | 電子メールアドレス |
| labelLikes | いいね! |
| labelLoading | ロード中 |
| labelNewPassword | 新しいパスワード |
| labelNotification | 通知 |
| labelPassword | パスワード |
| labelProfile | プロファイル |
| labelUserName | ユーザー名 |
| labelUserNameOrEmail | ユーザー名または電子メール |
| lastName | 姓 |
| LiveFyReAccount | Livefyreアカウント |
| location | ロケーション |
| loadingProfile | プロファイルのロード中 |
| newPassword | 新しいパスワード |
| oldPassword | 古いパスワード |
| on | on |
| または | または |
| passwordLinkExpired | パスワードのリセットにクリックしたリンクの有効期限が切れました。もう一度パスワードをリセットして、新しいリンクを送信します。 |
| platecheckemailToComplete | 電子メールをチェックして登録を完了してください。 |
| post | 投稿済み |
| PoweredBy | powered by |
| profileNotificationすぐ | すぐに |
| profileNotificationTimeTime | 時間単位 |
| profileInitiationNever | never |
| recentComments | 最近のコメント |
| reset | リセット |
| resetPassword | パスワードをリセット |
| signIn | サインイン |
| signInWith | サインインしてサインイン |
| signInWithEmail | 電子メールでサインイン |
| signUp | サインアップ |
| SocialAccount | Socialアカウント |
| successSpassWordChanged | 成功!パスワードが変更され、現在ログインしている |
| termsAndConditions | 利用条件 |
| termsAndConditionsIntro | サインアップすることにより、 |
| multerOfUse | 利用条件 |
| multOfUseIntro | ログインすると、 |
| thisUser | このユーザー |
| verifyPassword | Verify Password |
| fileSizeLimit | 2MBの最大値 |
| accountnotfound | アカウントが見つかりません |
| avalTargetImageExcedSize | アバター画像が2MBのファイル制限を超えています |
| fieldRequired | フィールドは整数のみを使用できます |
| fieldlyacceptsqvalidemail | フィールドのみ有効な電子メールを受信 |
| fieldlyacceptescopter | フィールドのみレターを受け入れる |
| fileSizeSummary belessThanMB | ファイルサイズはMB未満にする必要 {#}があります |
| invalidusernamorpassword | 無効なユーザ名またはパスワード |
| minimumthrottocharacters | {#} 最低文字長 |
| maxmaximrothofcharacters | 文字の {#} 最大長 |
| thewasanerror | エラーが発生しました |
| thisfieldrequired | このフィールドは必須です。 |
| validfileextensions | 有効なファイル拡張子 |
| valueumstmatch | 値は一致する必要があります |
| passwordLength | は、6~32文字です。 |
| passwordChars | には大文字と小文字の両方の文字を含めます。 |
| passwordSymbols | に少なくとも1つの数字と1つの記号を含めます。 |
| passwordUserName | ユーザー名が含まれていません。 |
| passwordPoagarTitle | パスワードは次の必要があります。 |
| passwordErrorContainsFirstName | 入力したパスワードには、ユーザ名、名、姓が表示されます。セキュリティ上の理由から、ユーザ名、名、姓を含まないパスワードを入力してください。パスワードには以下を含める必要もあります。6~32文字の大文字のA小文字のA記号 |
| passwordErrorContainsLastName | 入力したパスワードには、ユーザ名、名、姓が表示されます。セキュリティ上の理由から、ユーザ名、名、姓を含まないパスワードを入力してください。パスワードには以下を含める必要もあります。6~32文字の大文字のA小文字のA記号 |
| passwordErrorContainsUserName | 入力したパスワードには、ユーザ名、名、姓が表示されます。セキュリティ上の理由から、ユーザ名、名、姓を含まないパスワードを入力してください。パスワードには以下を含める必要もあります。6~32文字の大文字のA小文字のA記号 |
| passwordErrorTooShort | patwordの最低6文字 |
| passwordErrorToLong | パスワードの最大32文字 |
| passwordErrorMissingUp大 | パスワードには少なくとも1文字の大文字を含める必要があります |
| passwordErrorMissingLowerCase | Pasthwordに最低1文字の小文字を含める必要がある |
| passwordErrorMissingSymbol | パスワードに少なくとも1つの記号をセット内に含める `!@#$%^&*()?.,<>\’;:”[]{}|` |


