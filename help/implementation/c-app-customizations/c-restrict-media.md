---
description: アプリストリームに含めるメディアのタイプを制限する。
seo-description: アプリストリームに含めるメディアのタイプを制限する。
seo-title: メディアの制限
solution: Experience Manager
title: メディアの制限
uuid: c470c985-d221-4f39-8bd4-4e44ec14db95
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---


# メディアを制限{#restrict-media}

アプリストリームに含めるメディアのタイプを制限する。

デフォルトでは、すべてのメディア添付ファイルをアプリに埋め込むことができます。 Livefyreでは、このオプションを変更して、選択した添付ファイルの種類がアプリに投稿されないようにすることができます。

>[!NOTE]
>
>LivefyreとEmbedlyのパートナーがメディア統合に関与しています。 詳しくは、コンテンツの統合/統合を参照してください。 リンクの拡張やソースに関するご質問は、担当のテクニカルアカウントマネージャーにお問い合わせください。

次の例では、YouTubeおよびVimeoがコメントストリームから埋め込むのをブロックします。

```
var attachmentDelegate = function(embedObj) { 
   var providersToBlock = ['youtube', 'vimeo']; 
   for (var i=0, len=providersToBlock.length; i<len; i++) { 
      if (embedObj.provider_url.indexOf(providersToBlock[i]) > -1) { 
         return false; 
      } 
   } 
   return true; 
};
```

会話の読み込み時：

```
networkConfig["attachmentDelegate"] = attachmentDelegate; 
fyre.conv.load(networkConfig, [convConfig]);
```

