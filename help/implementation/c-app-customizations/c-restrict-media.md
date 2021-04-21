---
description: アプリストリームに含めるメディアのタイプを制限する。
title: メディアの制限
exl-id: ae09a058-41de-4b63-8654-cc82f5abad14
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 0%

---

# メディアを制限{#restrict-media}

アプリストリームに含めるメディアのタイプを制限する。

デフォルトでは、すべてのメディア添付ファイルをアプリに埋め込むことができます。 Livefyreでは、このオプションを変更して、選択した添付ファイルの種類がアプリに投稿されないようにすることができます。

>[!NOTE]
>
>LivefyreとEmbedlyのパートナーがメディア統合に関与しています。 詳しくは、コンテンツの統合/統合を参照してください。 リンクの拡張やソースに関するご質問は、担当のテクニカルアカウントマネージャーにお問い合わせください。

次の例では、YouTubeとVimeoがコメントストリームから埋め込むのをブロックします。

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
