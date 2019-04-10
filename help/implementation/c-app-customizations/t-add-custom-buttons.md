---
description: Livefyreアプリにカスタムアクションを追加します。
seo-description: Livefyreアプリにカスタムアクションを追加します。
seo-title: カスタムボタンを追加
solution: Experience Manager
title: カスタムボタンを追加
uuid: 27d24c21- d83f-49df-9b3f-15d7abbd2bd7
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# カスタムボタンを追加{#add-custom-buttons}

Livefyreアプリにカスタムアクションを追加します。

Livefyreでは、コンテンツの一部に、既存のアクションボタン（および **[!UICONTROL Share]****[!UICONTROL Flag]**など）の横にカスタムボタンを追加できます。

モバイルデバイスでボタンを表示するかどうかを定義するには、mobile引数を使用します。

例えば、モバイルデバイスインターフェイスのカスタムアクションボタンを追加するには:

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

1. 追加する各ボタンを説明するオブジェクトの配列を含む、ActionButtonsという名前の追加の引数を、ActionButtonsオブジェクトに渡します。
1. 各ボタンに表示するテキストのキーを定義します。
1. 各ボタンのclickイベント時に呼び出されるコールバックを追加します。

The callback is invoked with an object with two keys: `authorId` and `contentId`.
