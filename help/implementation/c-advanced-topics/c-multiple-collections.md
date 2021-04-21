---
description: 1つのページに複数のコレクションを表示します。
title: 複数のコレクション
exl-id: 748b6ca6-635e-4bae-9b95-cfbd4651751f
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 1%

---

# 複数のコレクション{#multiple-collections}

1つのページに複数のコレクションを表示します。

サイトの1つのページに複数のコレクションを含めることができます。 例えば、イベントを投稿するには、イベント中にLive BlogやChatのディスカッションを行い、ページの横に別のアプリがあり、ソーシャルWebの周りに関連する厳選されたコンテンツが表示される場合があります。 または、記事の下にコメントアプリを追加し、チャットを横に表示することもできます。

ページ上で複数の会話を取得するには、配列に1つ以上の設定を追加し、その配列をload呼び出しに渡します。 次に例を示します。

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
