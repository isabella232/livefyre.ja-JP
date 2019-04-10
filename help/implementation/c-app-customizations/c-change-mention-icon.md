---
description: プルダウンメニュー（@mention）で Livefyre ユーザーに表示されるアイコンを変更します。
seo-description: メンションプルダウンメニューの Livefyre ユーザーに表示されるアイコンを変更します。
seo-title: メンションアイコンを変更
solution: Experience Manager
title: アイコンを変更（@mention）
uuid: a395f4ff- a774-454a-8d94-4a3371d8cc2c
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 変更 `@mention` アイコン {#change-mention-icon}

`@mention` プルダウンメニューのLivefyreユーザーに表示されるアイコンを変更します。

`@mention` プルダウンメニューで使用されているLivefyreアイコンを選択したアイコンに変更し、コミュニティメンバーが自分のアイコンを使用していることを示します。

## 例

このアイコンを変更するには、スタイルシートに以下のCSSを追加します。<*your resource*> urlを選択した画像のURLに置き換えて、デフォルトのLivefyreバッジを置き換えます。

```
.fyre-editor-container .fyre-editor-toolbar > .fyre-mention-menu .fyre-mention-item .fyre-mention-item-livefyre { 
    background: url(<your resource url>) no-repeat center; 
    background-position: 0px 0px; 
    background-size: 22px 22px; 
}
```
