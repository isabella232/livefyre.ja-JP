---
description: JavaScriptイベントを使用して、Media wallで発生するイベントをリッスンし、選択したAnalyticsツールに送信します。
seo-description: JavaScriptイベントを使用して、Media wallで発生するイベントをリッスンし、選択したAnalyticsツールに送信します。
seo-title: メディアウォールのJavaScriptイベント
solution: Experience Manager
title: メディアウォールのJavaScriptイベント
uuid: 8afc0529-4640-476a-b207-91b2c70101f0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# メディアウォールのJavaScriptイベント{#javascript-events-for-media-wall}

JavaScriptイベントを使用して、Media wallで発生するイベントをリッスンし、選択したAnalyticsツールに送信します。

Livefyreは、Livefyreアプリでのユーザーアクティビティを追跡するJavaScriptイベントを提供します。 例えば、ユーザーがTwitterやFacebookにコンテンツを「いいね！」したり共有したりした場合や、新しいコンテンツが投稿された場合に、ページを更新したい場合があります。

イベントの受け取り方法の例を次に示します。 イベ `console.log` ントをマッピングし、Analytics統合（Dynamic Tag Management、Adobe Analytics JS、Google Analyticsなど）に送信するコードで置き換えます。

```
document.body.addEventListener('insights', function (data) { 
 console.log('Received:', data.detail.type, data); 
});
```

サポートされるMedia wallイベントのリスト：

## メディアウォールイベント

| イベント | 定義 |
|---|---|
| `Init` | メディアウォールがページに含まれる場合。 |
| `Load` | 位置に関係なく、ページにメディアウォールが読み込まれたとき。 |
| `PostButtonClick` | ユーザがメディアウォールの「アップロード」ボタンをクリックしたとき。 |
| `RequestMore` | ユーザがメディアウォールに読み込むコンテンツの数が増えるとき。 |
| `TwitterReplyClick` | ユーザーがメディアウォールから「Twitter返信」ボタンをクリックしたとき。 |
| `TwitterRetweetClick` | ユーザーがメディアウォールから「Twitterリツイート」ボタンをクリックしたとき。 |
| `TwitterLikeClick` | ユーザーがメディアウォールから「Twitterの「いいね！」/「お気に入り」ボタンをクリックしたとき。 |
| `ModalView` | ユーザがクリックして、大きいモーダルウィンドウでMedia wallコンテンツを表示したとき。 |
| `Like` | ユーザがMedia wallから「いいね！」ボタンをクリックしたとき。 |
| `ShareButtonClick` | ユーザーがMedia Wallカードの共有ボタンをクリックするたびに表示されます。 |
| `ShareURL` | 「URLに共有」テキスト領域がメディアウォールから選択またはコピーされている場合。 |
| `ShareFacebook` | メディアウォールから「Facebookに共有」をクリックした場合。 |
| `ShareTwitter` | メディアウォールから「Twitterで共有」をクリックした場合。 |
