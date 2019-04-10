---
description: null
seo-description: null
seo-title: Livefyre Analyticsイベント
solution: Experience Manager
title: Livefyre Analyticsイベント
uuid: 4eb5a196- ca33-40f8- a96d- ed46469223de
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyre Analyticsイベント {#livefyre-analytics-events}

## イベントオブジェクト定義 {#section_dh1_yhn_pdb}

次のコードは、ページ上のAnalyticsハンドラーによって受信されるイベントオブジェクトのフィールドを定義します。

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

## Livefyre AnalyticsイベントおよびeVar {#section_u3k_tft_mcb}

Report Suite Managerを使用してレポートで使用するカスタムイベントにマップするLivefyreイベント。Adobe Analyticsのレポートスイートについて詳しくは [、Report Suite Manager](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)を参照してください。Report Suite ManagerでLivefyreイベントを使用する方法について [](../livefyre-analytics/c-use-livefyre-with-adobe-analytics.md#section_iks_kgd_4cb)詳しくは、を参照してください。

## Livefyre Analyticsイベント

| イベント | 説明 |
|---|---|
| Init | 少なくとも1つのLivefyreアプリケーションを含むページが読み込まれる場合 |
| Load | ユーザー表示に関係なく、ページにアプリが読み込まれたとき |
| 表示 | アプリが初めてビューポートに入ったとき。 |
| Post | ユーザーがコメントまたはコンテンツの一部を投稿するときは、いつでも投稿を投稿できます。トップレベルの投稿，返信，レビュー，メディアウォールのアップロード |
| 投稿済み | 投稿が正常に完了したとき。 |
| Twitter_ Reply | Twitterでユーザーが返信した時間 |
| Twitter_ Like | コンテンツが共有された場所:リツイート |
| Livefyre_ Like | アプリケーションでのLIivefyreの機能の使用 |
| Livefyre_ Different | ユーザーが「いいね!"を取り消したときの「いいね!"の取り消し |
| shareOnPost | ユーザーがコンテンツを投稿して投稿機能で共有を使用するたび |
| ShareButtonClick | ユーザーがコメントの共有ボタンをクリックするたびに |
| ShareTwitter | Twitterで共有をクリックしたとき |
| ShareFacebook | "Facebookで共有」がクリックされたとき |
| shareURL | "URLで共有」テキスト領域が選択/コピーされたとき。 |
| expandReplies | ユーザーが"+"または「展開」リンクをクリックすると、上位レベルの投稿に対するすべての返信が表示されます |
| collapseLeilies | ユーザーが-または折りたたみリンクをクリックして最上位レベルの投稿上のすべての返信を表示するとき |
| flagClick | ユーザーがフラグモーダルを開くたびに |
| flagスパム | ユーザーがコンテンツをスパムとしてフラグ付けする場合 |
| flagInfix | ユーザーがコンテンツに同意しない場合 |
| フラグ付き攻撃 | ユーザーがコンテンツに不快なフラグを付けたとき |
| flagOffTopic | ユーザーがコンテンツをトピックとしてフラグ付けしたとき |
| flagCancel | フラグを送信するときにユーザーがXまたは「キャンセル」をクリックしたとき |
| followCollection | 会話にはいつでも入ります（レビューでは"I'm relite""）。 |
| unfollowCollection | 会話の後に |
| requestMore | ユーザーがアプリケーションにより多くのコンテンツをロードしたとき（高速度にするために必要） |
| modalView | ユーザーがモーダルでコンテンツを表示するときにいつでもクリック |
| TwitterResetTweetClick | コンテンツが共有された場所:リツイート |
| postButtonClick | ユーザーが投稿をクリックすると（"Whats（お客様の心）」）。」）ボタン |
| ログイン | ユーザーがログインしたときにいつでも |
| ログアウト | ユーザーがログアウトしたときのいつでも |

Livefyreが提供するコンバージョン変数（eVar）のリストを次に示します。

## コンバージョン変数- eVar

| イベント | 説明 |
|--- |--- |
| ネットワークID | LivefyreのネットワークID/名前 |
| アプリID | アプリケーションの終了 |
| コンテキストID | LivefyreのコンテンツID |
| アプリケーションのタイプ | Livefyreアプリケーションのタイプオプション: <br><ul><li>Live Blog  </li><li> Feature Card</li><li>カルーセル</li><li>チャット </li><li>コメント</li><li>フィルムストリップ</li><li>マップ</li><li>モザイク</li><li>メディアウォール</li><li>トレンド</li><li>アップロードボタン</li></ul> |
| コンテンツタイプ | Instagram、Twitter、Facebook、Livefyre、YouTubeなど |

## 詳細情報 {#section_b3d_4yl_pdb}

このページで説明するトピックについて詳しくは、以下を参照してください。

* [Report Suite ManagerDTM](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)[](https://marketing.adobe.com/resources/help/en_US/livefyre/c_filmstrip_app.html)

* [ルール](https://marketing.adobe.com/resources/help/en_US/dtm/rules.html)
* [Livefyre. js](/help/implementation/c-livefyre.js.md)