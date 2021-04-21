---
description: コメントアプリの埋め込みは、コアアプリの埋め込みの手順に従います。
title: コメントアプリの埋め込み
exl-id: 5eb191f8-ee52-4a9d-9180-90457a49fd4e
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 1%

---

# コメントアプリを埋め込む{#embed-a-comments-app}

コメントアプリの埋め込みは、コアアプリの埋め込みの手順に従います。

コメントアプリの埋め込みは、[アプリの埋め込み](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)で説明されているコアアプリの埋め込みの手順に従って行います

## 例

```
<html> 
  <head> 
    <script src="//cdn.livefyre.com/Livefyre.js"> 
    </script> 
  </head> 
<body> 
    <script type="text/javascript"> 
    var networkConfig = { 
      network: 'domainName' 
    }; 
    var convConfig = { 
      siteId: 'siteId', 
      articleId: 'articleId', 
      el: 'livefyre', 
      collectionMeta: 'collectionMeta', 
      checksum: 'checksum' 
    }; 
    
    Livefyre.require(['fyre.conv#3', 'auth'], function(Conv, auth) { 
        new Conv(networkConfig, [convConfig], function(commentsWidget) {}); 
        auth.delegate({ 
            login: function (callback) { 
                callback(null,{livefyre:'<userauthtoken>'}); 
            }, 
        }); 
    }); 
  
    </script> 
    <div id="livefyre"> 
    </div> 
   </body> 
</html>
```

「CollectionMetaの構築」の節で説明したように、CollectionMetaはエンコードされたJSONオブジェクトです。 上記の例では、JSONオブジェクトはJWTエンコードされる前に次の形式を取ります。

```
{ 
"url": "articleUrl",  
"articleId": "articleId",  
"type": "livecomments",  
"title": "articleTitle" 
}
```
