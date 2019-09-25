---
description: プルダウンメニュー（@mention）で Livefyre ユーザーに表示されるアイコンを変更します。
seo-description: メンションプルダウンメニューの Livefyre ユーザーに表示されるアイコンを変更します。
seo-title: メンションアイコンを変更
solution: Experience Manager
title: アイコンを変更（@mention）
uuid: a395f4ff-a774-454a-8d94-4a3371d8cc2c
translation-type: tm+mt
source-git-commit: 0d2ff61b1db6100de1d59e6e20c1175f015a78c5

---


# アイコンの `@mention` 変更 {#change-mention-icon}

Change the icon displayed for Livefyre users in the `@mention` pulldown menu.

プルダウンメニューで使用するLivefyreアイコ `@mention` ンを任意のアイコンに変更し、コミュニティのメンバーに独自のアイコンを指定できるようにします。

## 例

このアイコンを変更するには、スタイルシートに次のCSSを追加します。 &lt;*your resource*&gt; urlを、デフォルトのLivefyreバッジを置き換えるために選択した画像のURLに置き換えます。

```
.fyre-editor-container .fyre-editor-toolbar > .fyre-mention-menu .fyre-mention-item .fyre-mention-item-livefyre { 
    background: url(<your resource url>) no-repeat center; 
    background-position: 0px 0px; 
    background-size: 22px 22px; 
}
```
