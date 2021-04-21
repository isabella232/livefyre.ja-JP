---
description: サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。
title: Livefyre.js
uuid: null
exl-id: 5f60ce54-5669-4768-912d-c1b13946d8b8
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

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
