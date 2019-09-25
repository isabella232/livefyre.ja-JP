---
description: コアアプリケーションと同様のプロセスに従って、Sidentアプリを統合します。
seo-description: コアアプリケーションと同様のプロセスに従って、Sidentアプリを統合します。
seo-title: サイド統合
solution: Experience Manager
title: サイド統合
uuid: 4aa14ada-402a-482d-b43e-96f37afa6c53
translation-type: tm+mt
source-git-commit: fcee9dc152e7f8284e64248fdcc5bf81d39618ff

---


# サイド統合{#sidenotes-integration}

コアアプリケーションと同様のプロセスに従って、Sidentアプリを統合します。

一般的に、コアアプリケーションの統合が完了すると、オブジェクトを生成するために書き込まれたコードは、Sidentに対し `collectionMeta` て再利用できるようになります。

また、（オプション）フィールドで作成し `auth` た代理オブジェクトを[サ `auth` イド]に指定す `fyre.conv` ることで、既存の代理オブジェクトを再利用することもで `authDelegate` きます。

>[!NOTE]
>
>Sidentを使用すると、コンストラク `network`ターの他の部分に別々に渡すのではなく、、、お `siteId``articleId` よびを単一のオブジェクトに含めることができます。

```
<!DOCTYPE html> 
<html> 
<head> 
<!-- First add Livefyre.js to the page --> 
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
</head> 
<body> 
<script type="text/javascript"> 
var convConfig = { 
 network: 'client-solutions.fyre.co', 
 selectors:'span.lyrics-sidenote', 
 siteId: '356373', 
 articleId: 'sidenotes-sample', 
 collectionMeta: 'eyJhbGciOiAiSFMyNTYiLCAidHlwIjogIkpXVCJ9.eyJ1cmwiOiAiaHR0cDovL3d3dy5zaWRlbm90ZXMtZGVtby5jb20vbHlyaWNzIiwgInNpdGVJZCI6ICIzMDQwNTkiLCAidHlwZSI6ICJzaWRlbm90ZXMiLCAiYXJ0aWNsZUlkIjogInNpZGVub3Rlc19zYW1wbGUiLCAidGl0bGUiOiAiQ2xpZW50IFNvbHV0aW9ucyBTaWRlbm90ZXMifQ.2gxnsM0TS8dfp-Jokb5uW1kuMl-DqIlqfJSCBwJgf1k' 
}; 
  
Livefyre.require(['sidenotes#1', 'auth'], function (Sidenotes, Auth) { 
 new Sidenotes(convConfig); 
 Auth.delegate({ 
 login: function (callback) { 
 callback(null,{livefyre:'<userauthtoken>'}); 
 } 
 }); 
 }); 
</script> 
</body> 
</html>
```

「Building」の節で説明したように、はエ `collectionMeta` ンコードさ `collectionMeta` れたJSONオブジェクトです。 上の例では、JSONオブジェクトはJWTエンコードされる前に次の形式をとります。

```
{ 
"title":"Client Solutions Sidenotes", 
"url":"http:\/\/www.livefyre.com\/sidenotes", 
"articleId":"sidenotes_sample", 
"siteId":"304059", 
"type":"sidenotes" 
}
```

詳しくは、トークンを参照してくだ `collectionMeta` さい。

## モバイル設定

サイドは、モバイルデバイスでの使用に最適化されました。 モバイルバージョンのLivefyre appで最良の結果を得るには、ユーザースケーラブルオプションを「いいえ」に設定します。 次に例を示します。

```
<meta name="viewport" content="width=device-width, user-scalable=no">
```
