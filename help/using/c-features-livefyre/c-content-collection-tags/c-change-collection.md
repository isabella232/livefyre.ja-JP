---
description: ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。
seo-description: ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。
seo-title: コレクションの変更
solution: Experience Manager
title: コレクションの変更
uuid: 69bafcc7-c55e-47d6-bc79-b0db80fdf138
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# コレクションの変更{#change-collection}

ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。

Livefyreアプリが既に読み込まれている間にURLを変更せずに、ページに表示されるコレクションを変更するには、コレクションの委任を変更を使用します。 この機能を使用して、ユーザーが操作した後に表示されるコレクションが変更される写真やビデオギャラリー、または他のアプリを表示します。

例えば、ギャラリー内のビデオまたは写真をクリックすると、その選択に固有のコレクションが読み込まれますが、ページのURLは変更されません。

単一のコメント数ページから3つのコレクションのいずれかを読み込 [むには](/help/implementation/c-advanced-topics/t-display-comment-count.md) 、次の手順に従います。

```
<html> 
<head> 
<script src='//cdn.livefyre.com/Livefyre.js'></script> 
</head> 
<body> 
<script type="text/javascript"> 
convConfig1 = {"collectionMeta": <COLLECTION META 1>, 
             "checksum": <CHECKSUM 1>, 
             "siteId": <SITE ID>, 
             "articleId":"1", 
             "el":"livefyre"}; 
convConfig2 = {"collectionMeta": <COLLECTION META 2>, 
             "checksum": <CHECKSUM 2>, 
             "siteId": <SITE ID>, 
             "articleId":"2", 
             "el":"livefyre"}; 
convConfig3 = {"collectionMeta": <COLLECTION META 3>, 
             "checksum": <CHECKSUM 3>, 
             "siteId": <SITE ID>, 
             "articleId":"3", 
             "el":"livefyre"}; 
  
Livefyre.require(['fyre.conv#prod'],function(Conv) { 
    new Conv({"network": "<NETWORK NAME>"}, 
    [convConfig1], 
    function(app) {  
        window.changeConv = app.changeCollection; 
    } 
    ); 
}); 
</script> 
  
<div id="livefyre"></div> 
<button onclick="window.changeConv(convConfig1);">Conv 1</button> 
<button onclick="window.changeConv(convConfig2);">Conv 2</button> 
<button onclick="window.changeConv(convConfig3);">Conv 3</button> 
</body> 
</html>
```

