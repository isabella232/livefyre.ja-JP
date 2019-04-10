---
description: ユーザーが単一のページレイアウトとURLからコレクションをクリックできるようにします。
seo-description: ユーザーが単一のページレイアウトとURLからコレクションをクリックできるようにします。
seo-title: コレクションの変更
solution: Experience Manager
title: コレクションの変更
uuid: 81c8a554-375f-4659-9e25-5b3618824633
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# コレクションの変更 {#change-collection}

ユーザーが単一のページレイアウトとURLからコレクションをクリックできるようにします。

Livefyreアプリケーションが既に読み込まれている間、ページに表示されるコレクションを変更するには、コレクションデリゲートを使用して、ページに表示されるコレクションを変更します。この機能を使用して、ユーザーアクションの後に表示されるコレクションを変更する写真またはビデオギャラリーやその他のアプリを表示します。

例えば、ギャラリー内のビデオまたは写真をクリックすると、その選択に固有のコレクションが読み込まれ、ページのURLは変更されません。

単一ページから3つのコレクションのいずれか [を読み込む](../c-advanced-topics/t-display-comment-count.md#t_display_comment_count)には:

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
