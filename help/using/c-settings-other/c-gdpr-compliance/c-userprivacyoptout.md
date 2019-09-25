---
description: サイト訪問者がこの追跡をオプトアウトできるように、userPrivacyOptOutフラグをページに追加します。
seo-description: サイト訪問者がこの追跡をオプトアウトできるように、userPrivacyOptOutフラグをページに追加します。
seo-title: userPrivacyOptOut
title: userPrivacyOptOut
uuid: a043c50e-0a02-4c83-bbce-54b9b51316a5
translation-type: tm+mt
source-git-commit: 9e01dd4515c01154e3566a39b367b8efa4ec082a

---


# userPrivacyOptOut{#userprivacyoptout}

ページにフ `userPrivacyOptOut` ラグを追加して、サイト訪問者がこの追跡をオプトアウトできるようにします。

Livefyreは、Livefyreアプリでのユーザーアクティビティを追跡するJavaScriptイベントを提供します。

Livefyreアプリを埋め込んで、訪問者が追跡に同意しない場合は、Livefyreを動的に設定して、訪問者のプライバシーを確保するための機能を無効にすることができます。

設定すると、Livefyreは次の処理を行います。

* アプリで認証サポートを無効にします。
* Livecountとイベントの生成の無効化
* ページ上の任意のアプリで作成された既存のcookieを削除します
* サードパーティがcookieを作成できないようにするために、サードパーティドメインからの画像を使用したプロキシメディア
* 閲覧に追加のクリックが必要なサードパーティビデオに対するビデオマスクのクリックスルーを有効にする

## ページのオプトアウト設定

Livefyreアプリを埋め込んだ統合では、サイト訪問者が単一のJavaScript変数を使用して同意を与えていない場合にLivefyreを設定できます。

説明:

1. ページの `userPrivacyOptOut` JavaScriptの前にフラグを追加し `Livefyre.js` ます。

   ```
   window.Livefyre = {userPrivacyOptOut: true};
   ```

1. 後の任 `Livefyre.js` 意の場所でページに追加しま `userPrivacyOptOut`す。

   Livefyreアプリは、管理者のプライバシー設定でインスタンス化されます。

   >[!NOTE]
   >
   >Livefyreアプリが読み込まれた後は、の値 `userPrivacyOptOut` を変更しないでください。

サイトの訪問者がオプトアウトを選択した場合は、同 `userPrivacyOptOut` 意ワークフローで「true」に設定されていることを確認します。
