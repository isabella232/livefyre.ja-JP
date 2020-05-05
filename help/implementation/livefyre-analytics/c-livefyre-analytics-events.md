---
description: 'null'
seo-description: 'null'
seo-title: Livefyre Analyticsのイベント
solution: Experience Manager
title: Livefyre Analyticsのイベント
uuid: 4eb5a196-ca33-40f8-a96d-ed46469223de
translation-type: tm+mt
source-git-commit: 573e815799fbae2c2c4f1d98a01ea0ae04108a34

---


# Livefyre Analyticsのイベント {#livefyre-analytics-events}

## イベントオブジェクトの定義 {#section_dh1_yhn_pdb}

次のコードは、ページ上のanalyticsハンドラーが受け取るイベントオブジェクトのフィールドを定義します。

```
{
  evars: {
    appId : string : URN ID of the app
    appType : string : Type of the app
    contentType : string : Type of the content that this event pertains to
    contextId : string : URN ID of the contextual item that this event pertains to
    environment : string : Environment that this app is using
    networkId : string : Network that this app is using
    publishedDate : number : Epoch time when the app was published
    userLoggedIn : boolean : If a user is logged in
  },
  generator: {
    env : string: Environment that this app is using
    id : string: URN ID of the app
    name : string: Name of the app
    networkId : string: Network that this app is using
    source : string: URN of the collection
    version : string: Semver version of the app
  },
  startTime : number: Epoch time when event was created
  type : string: Event type (Table 1)
}
```

## Livefyre AnalyticsイベントとeVar {#section_u3k_tft_mcb}

Report Suite Managerを使用したレポートで使用するカスタムイベントにマッピングするLivefyreのイベントを以下に示します。 Adobe Analyticsのレポートスイートについて詳しくは、 [Report Suite Managerを参照してください](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)。 LivefyreイベントとReport Suite Managerの使用方法について詳しくは、を参照してくだ [](../livefyre-analytics/c-use-livefyre-with-adobe-analytics.md#section_iks_kgd_4cb)さい。

## Livefyre Analyticsのイベント

| イベント | 説明 |
|---|---|
| Init | 1つ以上のLivefyreアプリを含むページが読み込まれたとき |
| ロード | ユーザーの表示に関係なく、アプリがページに読み込まれた時 |
| 表示 | アプリが初めてビューポートに入ったとき。 |
| 投稿 | ユーザーがコメントやコンテンツの一部(例： 最上位レベルの投稿，返信，レビュー，メディアウォールのアップロード |
| 投稿済み | 投稿が成功したとき。 |
| Twitter_Reply | ユーザーがTwitterで返信した場合 |
| Twitter_Like | コンテンツの共有先： リツイート |
| Livefyre_Like | アプリケーションでlivefyreの「いいね！」機能が使用された場合は常に |
| Livefyre_Inlike | ユーザーがlivefyreの「いいね！」を取り消したとき |
| ShareOnPost | ユーザーがコンテンツを投稿し、投稿時に共有機能を使用するたびに |
| ShareButtonClick | ユーザーがコメントの共有ボタンをクリックしたとき |
| ShareTwitter | 「Twitterで共有」をクリックした場合 |
| ShareFacebook | 「Facebookで共有」をクリックした場合 |
| ShareURL | 「URLと共有」テキスト領域が選択またはコピーされたとき。 |
| ExpandReplies | ユーザーが「+」または「表示へ展開」リンクをクリックしたとき、最上位レベルの投稿でのすべての返信が表示されます。 |
| CollapseReplies | ユーザーが「 — 」または「表示へのリンクを折りたたむ」をクリックしたとき、最上位レベルの投稿ですべての返信が行われます。 |
| FlagClick | ユーザーがフラグモーダルを開くと常に |
| FlagSpam | ユーザーが内容にスパムフラグを付けた場合 |
| FlagDisagreet | ユーザーが内容に異議のフラグを付けた場合 |
| FlagOffense | ユーザーがコンテンツに攻撃的なフラグを付けた場合 |
| FlagOffTopic | ユーザーが内容にトピック以外のフラグを付けた場合 |
| FlagCancel | ユーザーがフラグを送信する際にXまたは「キャンセル」をクリックしたとき |
| FollowCollection | 会話がフォローされるたび（レビューで「興味がある」） |
| UnfollowCollection | 会話のフォローが解除されたとき |
| RequestMore | ユーザーがアプリにより多くのコンテンツを読み込んだとき（高速の場合にも必要） |
| ModalView | モーダル内の表示コンテンツに対してユーザーがクリックしたとき |
| TwitterRetweetClick | コンテンツの共有先： リツイート |
| PostButtonClick | ユーザーが投稿をクリックしたとき（「何を考えていますか？」）。 ボタン |
| ログイン | ユーザーがログインしたとき |
| ログアウト | ユーザーがログアウトしたとき |

以下は、Livefyreが提供するコンバージョン変数(eVar)のリストです。

## コンバージョン変数 — eVar

| イベント | 説明 |
|--- |--- |
| ネットワークID | LivefyreのネットワークID/名前 |
| アプリケーション ID | アプリのURN |
| コンテキストID | LivefyreのコンテンツID |
| アプリのタイプ | Livefyreアプリのタイプ オプション: <br><ul><li>ライブブログ  </li><li> 機能カード</li><li>カルーセル</li><li>チャット </li><li>コメント</li><li>Filmstrip</li><li>マップ</li><li>モザイク</li><li>メディアウォール</li><li>トレンド</li><li>アップロードボタン</li></ul> |
| コンテンツタイプ | Instagram、Twitter、Facebook、LiveFyre、YouTubeなど |

## 詳細情報 {#section_b3d_4yl_pdb}

このページで説明されているトピックの詳細については、次を参照してください。

* [Report Suite](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)[ManagerDTM](https://docs.adobe.com/content/help/en/livefyre/using/apps/filmstrip/c-filmstrip-app.html)

* [ルール](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/create-rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)