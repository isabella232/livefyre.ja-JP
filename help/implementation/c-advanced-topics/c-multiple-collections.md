---
description: 単一ページで複数のコレクションを表示します。
seo-description: 単一ページで複数のコレクションを表示します。
seo-title: 複数のコレクション
solution: Experience Manager
title: 複数のコレクション
uuid: 9675ffd7-1a59-42a1-b3ba-40af1744cfd1
translation-type: tm+mt
source-git-commit: 5bf937c8cb1a9ca12216ee1884142b8787ff063e

---


# 複数のコレクション {#multiple-collections}

単一ページで複数のコレクションを表示します。

複数のコレクションをサイトの1つのページに含めることができます。 例えば、イベントを公開するには、イベント中にライブブログやチャットのディスカッションを行い、ページの横に別のアプリを配置して、ソーシャルWeb上の関連するキュレーション済みコンテンツを表示します。 または、記事の下にコメントアプリを含め、チャットを横に表示することもできます。

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
