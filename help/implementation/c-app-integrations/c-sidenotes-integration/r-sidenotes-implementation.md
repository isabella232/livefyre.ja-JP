---
description: Sidenotes を .js 実装を使用して実装.
seo-description: Sidenotes を .js 実装を使用して実装.
seo-title: 導入について
solution: Experience Manager
title: 導入について
uuid: aa13852e- e2b0-4a86-97cd- d08ab5e2cfa
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 導入について{#sidenotes-implementation}

## Sidenotes を .js 実装を使用して実装

この機能を実装するには、オーバーライドする文字列の1-1オブジェクトマッピングをJavascript設定オブジェクトに渡します。フィールドを指定しない場合、デフォルトのテキストが使用されます。

### 例

```
var customStrings = { postAsButton: "New Post As Text", postEditButton: "New Post Edit Text"};networkConfig["strings"] = customStrings; fyre.conv.load( networkConfig, [convConfig], function(){});
```
