---
description: ページにUserPrivacyOptOutフラグを追加して、サイト訪問者がこのトラッキングをオプトアウトできるようにします。
seo-description: ページにUserPrivacyOptOutフラグを追加して、サイト訪問者がこのトラッキングをオプトアウトできるようにします。
seo-title: UserPrivacyOptOut
title: UserPrivacyOptOut
uuid: a043c50e-0a02-4c83- bce-54b9b51316a5
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# UserPrivacyOptOut{#userprivacyoptout}

ページに `userPrivacyOptOut` フラグを追加して、サイト訪問者がこのトラッキングをオプトアウトできるようにします。

Livefyreアプリでユーザーアクティビティを追跡するためのJavaScriptイベントがLivefyreに提供されています。

Livefyreアプリを埋め込むと、訪問者のプライバシーを確保する機能を無効にするLivefyreを動的に設定できます。

設定時、Livefyreは次のことを行います。

* アプリの認証サポートを無効にします。
* Livecountとイベントの生成の無効化
* ページにある任意のアプリによって作成された既存のcookieを削除する
* サードパーティドメインの画像を使用して、サードパーティのcookieを作成しないようにするプロキシメディア
* 追加のクリックを必要とするサードパーティ製ビデオのビデオマスククリックスルーを有効にする

## オプトアウト用のページの設定

Livefyreアプリの埋め込みでは、サイト訪問者が単一のJavaScript変数を使用して同意していない場合にLivefyreを設定できます。

手順:

1. JavaScriptの前に `userPrivacyOptOut` ページにフラグを追加 `Livefyre.js` します。

   ```
   window.Livefyre = {userPrivacyOptOut: true};
   ```

1. 後でページ `Livefyre.js` に追加 `userPrivacyOptOut`します。

   Livefyreアプリケーションは、プライバシー設定を使用してインスタンス化されます。

   >[!NOTE]
   >
   >Livefyreアプリケーションが読み込ま `userPrivacyOptOut` れたときの値は変更しないでください。

サイト訪問者がオプトアウトを選択した場合に、同意ワークフローでtrue `userPrivacyOptOut` に設定してください。
