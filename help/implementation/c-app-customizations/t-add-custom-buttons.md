---
description: Livefyre Appsに対する追加カスタムアクション。
seo-description: Livefyre Appsに対する追加カスタムアクション。
seo-title: 追加カスタムボタン
solution: Experience Manager
title: 追加カスタムボタン
uuid: 27d24c21-d83f-49df-9b3f-15d7abbd2bd7
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '136'
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
