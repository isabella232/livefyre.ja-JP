---
description: Commentsアプリの埋め込みは、コアアプリの埋め込みのプロセスに従います。
seo-description: Commentsアプリの埋め込みは、コアアプリの埋め込みのプロセスに従います。
seo-title: コメントアプリの埋め込み
solution: Experience Manager
title: コメントアプリの埋め込み
uuid: e4982ad3-cab1-4805-a55c-594cca3b7203
translation-type: tm+mt
source-git-commit: 268dc91369d346a254b7120706264eb91da8257e

---


# コメントアプリの埋め込み{#embed-a-comments-app}

Commentsアプリの埋め込みは、コアアプリの埋め込みのプロセスに従います。

コメントアプリの埋め込みは、アプリの埋め込みで説明されているコアアプリの埋め込みの [プロセスに従います](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)

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

「Building CollectionMeta」セクションで述べたように、CollectionMetaはエンコードされたJSONオブジェクトです。 上の例では、JSONオブジェクトはJWTエンコードされる前に次の形式をとります。

```
{ 
"url": "articleUrl",  
"articleId": "articleId",  
"type": "livecomments",  
"title": "articleTitle" 
}
```

