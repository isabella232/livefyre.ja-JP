---
description: メンションプルダウンメニューの Livefyre ユーザーに表示されるアイコンを変更します。
title: メンションアイコンを変更
exl-id: e078ef7f-7f16-4f5d-9152-95ae7fe7e4bd
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 19%

---

# `@mention`アイコン{#change-mention-icon}を変更

`@mention`プルダウンメニューで、Livefyreユーザーに表示されるアイコンを変更します。

`@mention`プルダウンメニューで使用するLivefyreアイコンを選択したアイコンに変更します。これにより、コミュニティのメンバーを自分のアイコンで示すことができます。

## 例

このアイコンを変更するには、スタイルシートに次のCSSを追加します。 &lt;*リソース*>のurlを、デフォルトのLivefyreバッジの置き換え用に選択した画像のURLに置き換えます。

```
.fyre-editor-container .fyre-editor-toolbar > .fyre-mention-menu .fyre-mention-item .fyre-mention-item-livefyre { 
    background: url(<your resource url>) no-repeat center; 
    background-position: 0px 0px; 
    background-size: 22px 22px; 
}
```
