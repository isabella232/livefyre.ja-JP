---
description: サイト上のLivefyreのパワーに使用されるLivefyreライブラリ。
seo-description: サイト上のLivefyreのパワーに使用されるLivefyreライブラリ。
seo-title: updateAnchorsメソッド
solution: Experience Manager
title: Livefyre. js
uuid: null
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# updateAnchorsメソッド {#updateAnchorsMethod}

ページに動的にsidindedコンテンツを追加するには、updateAnchorsメソッドを使用します。

このメソッドはページ番号付けに役立ちます。また、ページにサイトを動的に追加する場合は、その他のケースでも使用できます。このメソッドは、一致する要素の新しいアンカーを定義し、1つの引数を取ります。newSelector.

**newSelector**.Sideingに追加するセレクター。セレクター文字列、jQueryオブジェクト、または要素の配列（アプリケーションの構築時に渡されるセレクター引数によって受け入れられたタイプのいずれか）を使用できます。
フォーマット:

```
app.updateAnchors(newSelectors);
```

例：

```
var app = new Livefyre.Sidenotes(convConfig);// Load more contentapp.updateAnchors('#content');
```
