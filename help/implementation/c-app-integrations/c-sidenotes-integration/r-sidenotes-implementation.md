---
description: Sidenotes を .js 実装を使用して実装.
seo-description: Sidenotes を .js 実装を使用して実装.
seo-title: サイドの実装
solution: Experience Manager
title: サイドの実装
uuid: aa13852e-e2b0-4a86-97cd-d08ab5e2cfab
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# サイドの実装{#sidenotes-implementation}

## Sidenotes を .js 実装を使用して実装

この機能を実装するには、上書きする文字列の1 ～ 1個のオブジェクトマッピングをJavaScript設定オブジェクトに渡します。 フィールドを指定しない場合は、デフォルトのテキストが使用されます。

### 例

```
var customStrings = { postAsButton: "New Post As Text", postEditButton: "New Post Edit Text"};networkConfig["strings"] = customStrings; fyre.conv.load( networkConfig, [convConfig], function(){});
```
