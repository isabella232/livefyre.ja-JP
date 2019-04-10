---
description: JavaScriptイベントを使用して、Mediaウォールで発生したイベントをリスニングし、選択した分析ツールに送信します。
seo-description: JavaScriptイベントを使用して、Mediaウォールで発生したイベントをリスニングし、選択した分析ツールに送信します。
seo-title: MediaウォールのJavaScriptイベント
solution: Experience Manager
title: MediaウォールのJavaScriptイベント
uuid: 8abc0529-4640-476a- b207-91b2c70101f0
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# MediaウォールのJavaScriptイベント{#javascript-events-for-media-wall}

JavaScriptイベントを使用して、Mediaウォールで発生したイベントをリスニングし、選択した分析ツールに送信します。

Livefyreアプリでユーザーアクティビティを追跡するためのJavaScriptイベントがLivefyreに提供されています。例えば、ユーザーがTwitterやFacebookにコンテンツを「いいね!"または共有したり、新しいコンテンツが投稿されたときにページを更新したりできます。

イベントの受信方法の例を以下に示します。コード `console.log` に置き換えて、Analytics統合（Dynamic Tag Management、Adobe Analytics JS、Google Analyticsなど）にイベントをマッピングして送信します。

```
document.body.addEventListener('insights', function (data) { 
 console.log('Received:', data.detail.type, data); 
});
```

サポートされているMediaウォールイベントのリスト:

## メディアウォールイベント

| イベント | Definition |
|---|---|
| `Init` | ページにメディアウォールが含まれるとき。 |
| `Load` | メディアウォールが位置に関係なくページに読み込まれたとき。 |
| `PostButtonClick` | ユーザがMediaウォールの「アップロード」ボタンをクリックしたとき。 |
| `RequestMore` | ユーザがメディアウォールにコンテンツを読み込むとき。 |
| `TwitterReplyClick` | ユーザーがMediaウォールからTwitterの返信ボタンをクリックしたとき。 |
| `TwitterRetweetClick` | ユーザがMediaウォールからTwitterリツイートボタンをクリックしたとき。 |
| `TwitterLikeClick` | ユーザーがMediaウォールから"Twitterのいいね!"または「お気に入り」ボタンをクリックしたとき。 |
| `ModalView` | ユーザがクリックして、より大きなモーダルウィンドウでMediaウォールコンテンツを表示する場合。 |
| `Like` | ユーザがMediaウォールから「いいね!"ボタンをクリックしたとき。 |
| `ShareButtonClick` | Mediaウォールカードの共有ボタンをユーザーがクリックしたとき。 |
| `ShareURL` | "URLで共有」テキスト領域がメディアウォールから選択/コピーされたとき。 |
| `ShareFacebook` | "Facebookで共有」がクリックされると、Mediaウォールからクリックされます。 |
| `ShareTwitter` | "Twitterで共有」がクリックされると、Mediaウォールからクリックされます。 |
