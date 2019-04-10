---
description: アプリストリームに取り込むメディアのタイプを制限します。
seo-description: アプリストリームに取り込むメディアのタイプを制限します。
seo-title: メディアの制限
solution: Experience Manager
title: メディアの制限
uuid: c470c985- d221-4f39-8bd4-4e44ec14db95
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# メディアの制限{#restrict-media}

アプリストリームに取り込むメディアのタイプを制限します。

デフォルトでは、すべてのメディア添付ファイルをアプリに埋め込むことができます。Livefyreでは、選択した添付ファイルをユーザーがアプリに投稿できないようにするためのこのオプションを変更できます。

>[!NOTE]
>
>メディア統合用のLivefyreパートナー。詳しくは、コンテンツ統合/埋め込み統合を参照してください。リンクの拡張またはソースについては、テクニカルアカウントマネージャーにお問い合わせください。

次の例では、コメントストリームからYouTubeおよびVimeoの埋め込みをブロックします。

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

会話を読み込むとき:

```
networkConfig["attachmentDelegate"] = attachmentDelegate; 
fyre.conv.load(networkConfig, [convConfig]);
```

