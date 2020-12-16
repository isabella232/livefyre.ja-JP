---
description: サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。
seo-description: サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。
seo-title: updateAnchorsメソッド
solution: Experience Manager
title: Livefyre.js
uuid: null
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 1%

---


# updateAnchorsメソッド{#updateAnchorsMethod}

ページにサインの付いたコンテンツを動的に追加するには、updateAnchorsメソッドを使用します。

このメソッドは、ページネーションや、サイドで表示可能なコンテンツがページに動的に追加される場合に役立ちます。 このメソッドは、一致した要素に新しいアンカーを定義し、1つの引数を取ります。newSelectors。

**newSelectors**.サイトに追加するセレクターです。 これは、セレクター文字列、jQueryオブジェクト、または要素の配列（アプリの構築時に渡されるセレクター引数で受け入れられる任意の型）です。
形式：

```
app.updateAnchors(newSelectors);
```

例：

```
var app = new Livefyre.Sidenotes(convConfig);// Load more contentapp.updateAnchors('#content');
```
