---
description: Livefyreアプリにカスタムアクションを追加します。
seo-description: Livefyreアプリにカスタムアクションを追加します。
seo-title: カスタムボタンの追加
solution: Experience Manager
title: カスタムボタンの追加
uuid: 27d24c21-d83f-49df-9b3f-15d7abbd2bd7
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# カスタムボタンの追加{#add-custom-buttons}

Livefyreアプリにカスタムアクションを追加します。

Livefyreでは、コンテンツ上の既存のアクションボタン（、など）の横にカ **[!UICONTROL Share]**&#x200B;スタムボ **[!UICONTROL Flag]**&#x200B;タンを追加できます。

mobile引数を使用して、ボタンをモバイルデバイスに表示するかどうかを定義します。

例えば、モバイルデバイスインターフェイスにカスタムアクションボタンを追加するには：

```
var convConfig = {...}; // Should have siteId, articleId, etc. 
convConfig.actionButtons = [ 
   { 
      mobile: true,  
      // (optional) sets whether the button will appear on mobile devices 
      key: 'Do Something', 
      callback: function(contentInfo) { 
         console.log('Author of content is ' + contentInfo.authorId); 
         console.log('id of content is ' + contentInfo.contentId); 
      } 
   }, 
    ... 
]; 
  
fyre.conv.load(networkConfig, [convConfig]);
```

1. ConvConfigオブジェクトに、追加する各ボタンを説明するオブジェクトの配列を含むactionButtonsという名前の追加の引数を渡します。
1. 各ボタンに表示するテキストのキーを定義します。
1. 各ボタンのクリックイベント時に呼び出されるコールバックを追加します。

このコールバックは、2つのキーを持つオブジェクトを使用して呼び出されます。 `authorId` と `contentId`。
