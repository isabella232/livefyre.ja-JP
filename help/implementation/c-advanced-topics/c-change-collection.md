---
description: ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。
seo-description: ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。
seo-title: コレクションの変更
solution: Experience Manager
title: コレクションの変更
uuid: 81c8a554-375f-4659-9e25-5b3618824633
translation-type: tm+mt
source-git-commit: 5bf937c8cb1a9ca12216ee1884142b8787ff063e

---


# コレクションの変更 {#change-collection}

ユーザーが単一のページレイアウトとURLからコレクションをクリックスルーできるようにします。

Livefyreアプリが既に読み込まれている間にURLを変更せずに、ページに表示されるコレクションを変更するには、コレクションの委任を変更を使用します。 この機能を使用して、ユーザーが操作した後に表示されるコレクションが変更される写真やビデオギャラリー、または他のアプリを表示します。

例えば、ギャラリー内のビデオまたは写真をクリックすると、その選択に固有のコレクションが読み込まれますが、ページのURLは変更されません。

1つのペ [ージから3つのコレクションのいずれかを読み込むには](../c-advanced-topics/t-display-comment-count.md#t_display_comment_count):

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
