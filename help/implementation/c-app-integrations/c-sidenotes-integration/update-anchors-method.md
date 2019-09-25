---
description: サイトでLivefyreを動力付与するために使用するコアLivefyreライブラリ。
seo-description: サイトでLivefyreを動力付与するために使用するコアLivefyreライブラリ。
seo-title: updateAnchorsメソッド
solution: Experience Manager
title: Livefyre.js
uuid: null
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# updateAnchorsメソッド {#updateAnchorsMethod}

ページに動的にサイド付きコンテンツを追加するには、updateAnchorsメソッドを使用します。

このメソッドは、ページネーションや、サイト表示可能なコンテンツが動的にページに追加される場合に役立ちます。 このメソッドは、一致した要素に対して新しいアンカーを定義し、単一の引数を取ります。newSelectors.

**newSelectors**. サイドに追加するセレクターです。 これは、セレクター文字列、jQueryオブジェクト、または要素の配列（アプリの構築中に渡されるセレクター引数で受け取る任意の型）です。
形式：

```
app.updateAnchors(newSelectors);
```

例：

```
var app = new Livefyre.Sidenotes(convConfig);// Load more contentapp.updateAnchors('#content');
```
