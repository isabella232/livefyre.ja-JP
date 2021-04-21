---
description: Livefyre Appsに対する追加カスタムアクション。
title: 追加カスタムボタン
exl-id: a62d8605-59c2-4214-af26-805c1989aca1
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---

# 追加カスタムボタン{#add-custom-buttons}

Livefyre Appsに対する追加カスタムアクション。

Livefyreでは、コンテンツ上の既存のアクションボタン（**[!UICONTROL Share]**、**[!UICONTROL Flag]**&#x200B;など）の横にカスタムボタンを追加できます。

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

1. ConvConfigオブジェクトに、actionButtonsという名前の追加の引数を渡します。この引数には、追加する各ボタンを表すオブジェクトの配列が含まれます。
1. 各ボタンに表示するテキストのキーを定義します。
1. 各ボタン追加のclickイベント時に呼び出されるコールバック。

このコールバックは、2つのキーを持つオブジェクトで呼び出されます。`authorId`と`contentId`。
