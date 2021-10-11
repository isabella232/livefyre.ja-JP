---
title: Livefyre Analytics イベント
description: Livefyre Analytics イベント
exl-id: ec32414c-0580-44dc-ae5b-6df0b42c0ec3
source-git-commit: 53aead87db517e6f68266a66115889509287a287
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Livefyre Analytics イベント

## イベントオブジェクトの定義 {#section_dh1_yhn_pdb}

次のコードは、ページ上の Analytics ハンドラーが受け取るイベントオブジェクトのフィールドを定義します。

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

## Livefyre Analytics のイベントと eVar {#section_u3k_tft_mcb}

次の Livefyre イベントは、Report Suite Manager を使用して、レポートで使用するカスタムイベントにマッピングされます。 Adobe Analyticsのレポートスイートについて詳しくは、[Report Suite Manager](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=en) を参照してください。 Livefyre イベントを Report Suite Manager で使用する方法について詳しくは、[](../livefyre-analytics/c-use-livefyre-with-adobe-analytics.md#section_iks_kgd_4cb) を参照してください。

## Livefyre Analytics イベント

| イベント | 説明 |
|---|---|
| Init | 少なくとも 1 つの Livefyre アプリを含むページが読み込まれたとき |
| ロード | ユーザービューに関係なく、アプリがページに読み込まれた時間 |
| 表示 | アプリが初めてビューポートに入ったとき。 |
| 投稿 | ユーザーがコメントやコンテンツの一部を投稿するとき ( 例：トップレベルの投稿、返信、レビュー、メディアウォールのアップロード |
| 投稿済み | 投稿が成功したとき。 |
| Twitter_Reply | ユーザーがTwitterで返信したとき |
| Twitter_Like | コンテンツの共有先：リツイート |
| Livefyre_Like | Livefyre の「いいね！」機能がアプリでいつ使用されても |
| Livefyre_Inliked | ユーザーが Livefyre の「いいね！」を取り消したとき |
| ShareOnPost | ユーザーがコンテンツを投稿し、投稿時に共有機能を使用するたびに |
| ShareButtonClick | ユーザーがコメントの共有ボタンをクリックするといつでも |
| ShareTwitter | 「Twitterに共有」をクリックしたとき |
| ShareFacebook | 「Facebookに共有」をクリックしたとき |
| ShareURL | 「 URL に共有」テキスト領域が選択またはコピーされたとき。 |
| ExpandReplies | ユーザーが+リンクまたは展開リンクをクリックして、トップレベルの投稿に対するすべての返信を表示したとき |
| CollapseReplies | ユーザーが「 — 」リンクまたは「折りたたむ」リンクをクリックして、最上位の投稿に対するすべての返信を表示したとき |
| FlagClick | ユーザーがフラグモーダルを開くたびに |
| FlagSpam | ユーザーがコンテンツにスパムのフラグを付けたとき |
| FlagDisagnee | ユーザーがコンテンツに「同意しない」フラグを設定したとき |
| FlagOffensive | ユーザーがコンテンツに攻撃的なフラグを設定したとき |
| FlagOffTopic | ユーザーがコンテンツにトピック以外のフラグを設定したとき |
| FlagCancel | ユーザーがフラグの送信時に X または「キャンセル」をクリックしたとき |
| FollowCollection | 会話がフォローされるたびに（「レビュー」で「興味を持つ」） |
| UnfollowCollection | 会話のフォローが解除されたとき |
| RequestMore | ユーザーがアプリに読み込んだコンテンツの量を増やすたびに（高速でも必要） |
| ModalView | ユーザーが「 」をクリックしてモーダルのコンテンツを表示するとき |
| TwitterRetweetClick | コンテンツの共有先：リツイート |
| PostButtonClick | ユーザーが投稿をクリックすると（「何を考えていますか？」）、 ボタン |
| ログイン | ユーザーがログインしたとき |
| ログアウト | ユーザーがログアウトしたとき |

次に、Livefyre が提供するコンバージョン変数 (eVar) のリストを示します。

## コンバージョン変数 — eVar

| イベント | 説明 |
|--- |--- |
| ネットワーク ID | Livefyre のネットワーク ID/名前 |
| アプリケーション ID | アプリの URN |
| コンテキスト ID | Livefyre のコンテンツ ID |
| アプリの種類 | Livefyre アプリのタイプ。 オプション: <br><ul><li>ライブブログ  </li><li> 機能カード</li><li>カルーセル</li><li>チャット </li><li>コメント</li><li>Filmstrip</li><li>マップ</li><li>モザイク</li><li>メディアウォール</li><li>トレンド</li><li>アップロードボタン</li></ul> |
| コンテンツタイプ | Instagram、Twitter、Facebook、LiveFyre、YouTubeなど |

## 詳細情報 {#section_b3d_4yl_pdb}

このページで取り上げるトピックの詳細は、次を参照してください。

* [Report Suite ](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=en)[ManagerDTM](https://experienceleague.adobe.com/docs/livefyre/using/apps/filmstrip/c-filmstrip-app.html?lang=en)

* [ルール](https://experienceleague.adobe.com/docs/dtm/using/resources/rules/create-rules.html?lang=en)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
