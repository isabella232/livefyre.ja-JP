---
description: JavaScriptイベントを使用して、メディアウォールで発生するイベントをリッスンし、選択した解析ツールに送信します。
seo-description: JavaScriptイベントを使用して、メディアウォールで発生するイベントをリッスンし、選択した解析ツールに送信します。
seo-title: メディアウォールのJavaScriptイベント
solution: Experience Manager
title: メディアウォールのJavaScriptイベント
uuid: 8afc0529-4640-476a-b207-91b2c70101f0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---


# メディアウォールのJavaScriptイベント{#javascript-events-for-media-wall}

JavaScriptイベントを使用して、メディアウォールで発生するイベントをリッスンし、選択した解析ツールに送信します。

Livefyreは、Livefyre Appsでユーザーのアクティビティを追跡するJavaScriptイベントを提供しています。 例えば、ユーザーがTwitterやFacebookにコンテンツに「いいね！」をしたり共有したりした場合、または新しいコンテンツが投稿された場合に、ページを更新したい場合があります。

イベントの受信方法の例を以下に示します。 `console.log`を、Analytics統合(Dynamic Tag Management、Adobe AnalyticsJS、Google Analyticsなど)にマッピングしてイベントを送信するためのコードに置き換えます。

```
document.body.addEventListener('insights', function (data) { 
 console.log('Received:', data.detail.type, data); 
});
```

サポートされるメディアウォールイベントのリスト:

## メディアウォールイベント

| イベント | 定義 |
|---|---|
| `Init` | メディアウォールがページに含まれる場合。 |
| `Load` | 位置に関係なく、ページにメディアウォールが読み込まれたとき。 |
| `PostButtonClick` | ユーザがメディアウォールの「アップロード」ボタンをクリックしたとき。 |
| `RequestMore` | ユーザがMedia Wallに読み込むコンテンツの数を増やしたとき。 |
| `TwitterReplyClick` | ユーザーがメディアウォールから「Twitter返信」ボタンをクリックしたとき。 |
| `TwitterRetweetClick` | ユーザーがメディアウォールから「Twitterリツイート」ボタンをクリックしたとき。 |
| `TwitterLikeClick` | ユーザーがメディアウォールから「Twitterの「いいね！」/お気に入り」ボタンをクリックしたとき。 |
| `ModalView` | 大きいモーダルウィンドウで表示のメディアウォールのコンテンツをクリックしたとき。 |
| `Like` | ユーザがメディアウォールから「いいね！」ボタンをクリックしたとき。 |
| `ShareButtonClick` | ユーザーがMedia Wallカードの共有ボタンをクリックしたとき。 |
| `ShareURL` | 「URLに共有」テキスト領域がメディアウォールから選択またはコピーされた場合。 |
| `ShareFacebook` | メディアウォールから「Facebookで共有」をクリックした場合。 |
| `ShareTwitter` | メディアウォールから「Twitterで共有」をクリックした場合。 |
