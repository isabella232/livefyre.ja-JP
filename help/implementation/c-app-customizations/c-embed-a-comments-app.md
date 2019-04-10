---
description: コメントアプリを埋め込むと、コアアプリを埋め込むプロセスに従います。
seo-description: コメントアプリを埋め込むと、コアアプリを埋め込むプロセスに従います。
seo-title: コメントアプリの埋め込み
solution: Experience Manager
title: コメントアプリの埋め込み
uuid: e4982ad3- cab1-4805- a55c-594cca3b7203
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# コメントアプリの埋め込み{#embed-a-comments-app}

コメントアプリを埋め込むと、コアアプリを埋め込むプロセスに従います。

「アプリの埋め込み」で [説明されているコアアプリを埋め込むための、コメントアプリの埋め込み手順](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)

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

CollectionMetaセクションの作成に記載されているとおり、CollectionMetaはエンコードされたJSONオブジェクトです。上記の例では、JSONオブジェクトはJWTエンコード前に次の形式を使用します。

```
{ 
"url": "articleUrl",  
"articleId": "articleId",  
"type": "livecomments",  
"title": "articleTitle" 
}
```

