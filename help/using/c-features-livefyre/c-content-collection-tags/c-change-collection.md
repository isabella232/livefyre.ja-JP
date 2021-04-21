---
description: ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。
title: コレクションの変更
exl-id: 5cfae2c6-e328-4d2c-b08b-709be94e4c54
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 0%

---

# コレクションの変更{#change-collection}

ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。

Livefyreアプリが既に読み込まれている間にURLを変更せずに、ページに表示されるコレクションを変更するには、コレクションの変更の委任を使用します。 この機能を使用すると、フォトやビデオギャラリー、またはユーザーが操作した後に表示されるコレクションが変更される他のアプリを表示できます。

例えば、ギャラリー内のビデオまたは写真をクリックしても、その選択範囲に固有のコレクションが読み込まれますが、ページのURLは変更されません。

1つの[コメント数](/help/implementation/c-advanced-topics/t-display-comment-count.md)ページから3つのコレクションのいずれかを読み込むには：

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
