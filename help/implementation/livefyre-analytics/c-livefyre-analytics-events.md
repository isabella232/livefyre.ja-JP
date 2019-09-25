---
description: 'null'
seo-description: 'null'
seo-title: Livefyre Analyticsイベント
solution: Experience Manager
title: Livefyre Analyticsイベント
uuid: 4eb5a196-ca33-40f8-a96d-ed46469223de
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre Analyticsイベント {#livefyre-analytics-events}

## イベントオブジェクトの定義 {#section_dh1_yhn_pdb}

次のコードは、ページ上のAnalyticsハンドラーが受け取るイベントオブジェクトのフィールドを定義します。

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

Report Suite Managerを使用したレポートで使用するカスタムイベントにマッピングするLivefyreイベントを次に示します。 Adobe Analyticsのレポートスイートについて詳しくは、Report Suite Managerを [参照してください](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)。 Report Suite ManagerでLivefyreイベントを使用する方法について詳しくは、を参照してくださ [](../livefyre-analytics/c-use-livefyre-with-adobe-analytics.md#section_iks_kgd_4cb)い。

## Livefyre Analyticsイベント

| イベント | 説明 |
|---|---|
| Init | 少なくとも1つのLivefyreアプリを含むページが読み込まれたとき |
| ロード | ユーザービューに関係なく、アプリがページに読み込まれた時間 |
| 表示 | アプリが初めてビューポートに入ったとき。 |
| 投稿 | ユーザーがコメントやコンテンツの一部(例：最上位レベルの投稿，返信，レビュー，メディアウォールのアップロード |
| 投稿済み | 投稿が正常に完了したとき。 |
| Twitter_Reply | ユーザーがTwitterで返信したとき |
| Twitter_Like | コンテンツの共有先：リツイート |
| Livefyre_Like | アプリでlivefyreの「いいね！」機能が使用されるたび |
| Livefyre_Inlike | ユーザーがLivefyreの「いいね！」を取り消すたびに、 |
| ShareOnPost | ユーザーがコンテンツを投稿し、投稿時に共有機能を使用するたび |
| ShareButtonClick | ユーザーがコメントの共有ボタンをクリックするたび |
| ShareTwitter | 「Twitterで共有」をクリックした場合 |
| ShareFacebook | 「Facebookで共有」をクリックした場合 |
| ShareURL | 「URLに共有」テキスト領域が選択またはコピーされている場合。 |
| ExpandReplies | ユーザーが「+」または「展開」リンクをクリックして、最上位の投稿のすべての返信を表示したとき |
| CollapseReplies | ユーザーが「 — 」または「折りたたみ」リンクをクリックして、最上位の投稿のすべての返信を表示したとき |
| FlagClick | ユーザーがフラグモーダルを開くたびに |
| FlagSpam | ユーザーがコンテンツにスパムのフラグを付けたとき |
| FlagDisagree | ユーザーが内容に異議のフラグを付けた場合 |
| FlagOffense | ユーザーがコンテンツに不快なフラグを付けたとき |
| FlagOffTopic | ユーザーがコンテンツにトピック以外のフラグを付けたとき |
| FlagCancel | ユーザーがフラグを送信する際にXまたは「キャンセル」をクリックしたとき |
| FollowCollection | 会話がフォローされるたびに（レビューで「興味がある」） |
| UnfollowCollection | 会話がフォローされない場合 |
| RequestMore | ユーザーがアプリにより多くのコンテンツを読み込んだとき（高速度のためにも必要） |
| ModalView | ユーザーがクリックしてモーダルなコンテンツを表示するとき |
| TwitterRetweetClick | コンテンツの共有先：リツイート |
| PostButtonClick | ユーザーが投稿をクリックしたとき（「何を考えていますか？」）。ボタン |
| ログイン | ユーザーがログインしたとき |
| ログアウト | ユーザーがログアウトしたとき |

Livefyreが提供するコンバージョン変数(eVar)のリストを次に示します。

## コンバージョン変数 — eVar

| イベント | 説明 |
|--- |--- |
| ネットワークID | LivefyreのネットワークID/名前 |
| アプリケーション ID | アプリのURN |
| コンテキストID | LivefyreのコンテンツID |
| アプリの種類 | Livefyreアプリのタイプを参照してください。 オプション: <br><ul><li>ライブブログ  </li><li> 機能カード</li><li>カルーセル</li><li>チャット </li><li>コメント</li><li>Filmstrip</li><li>マップ</li><li>モザイク</li><li>メディアウォール</li><li>トレンド</li><li>アップロードボタン</li></ul> |
| コンテンツタイプ | Instagram、Twitter、Facebook、LiveFyre、YouTubeなど |

## 詳細情報 {#section_b3d_4yl_pdb}

このページで説明するトピックの詳細については、次を参照してください。

* [Report Suite](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)[ManagerDTM](https://marketing.adobe.com/resources/help/en_US/livefyre/c_filmstrip_app.html)

* [ルール](https://marketing.adobe.com/resources/help/en_US/dtm/rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)