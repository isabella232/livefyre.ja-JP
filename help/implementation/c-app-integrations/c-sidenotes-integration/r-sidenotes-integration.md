---
description: コアアプリケーションと同様のプロセスに従って、Sidenteアプリを統合します。
seo-description: コアアプリケーションと同様のプロセスに従って、Sidenteアプリを統合します。
seo-title: Sidents統合
solution: Experience Manager
title: Sidents統合
uuid: 4aa14ada-402a-482d-b43e-96f37afa6c53
translation-type: tm+mt
source-git-commit: fcee9dc152e7f8284e64248fdcc5bf81d39618ff
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 1%

---


# Sidents Integration{#sidenotes-integration}

コアアプリケーションと同様のプロセスに従って、Sidenteアプリを統合します。

一般的に、コアアプリケーションの統合が完了すると、`collectionMeta`オブジェクトを生成するために書き込まれたコードは、Sidentに対して再利用できます。

また、`fyre.conv`と共に作成した`auth`委任を（オプション）`authDelegate`フィールドのSidenotに指定することで、既存の`auth`委任を再利用することもできます。

>[!NOTE]
>
>Sidentsを使用すると、1つのオブジェクトに`network`、`siteId`、`articleId`を含めることができます。これらは、コンストラクターの他の部分で別々に渡す必要はありません。

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

「`collectionMeta`の構築」の節で説明したように、`collectionMeta`はエンコードされたJSONオブジェクトです。 上の例では、JSONオブジェクトはJWTエンコードされる前に次の形式を取ります。

```
{ 
"title":"Client Solutions Sidenotes", 
"url":"http:\/\/www.livefyre.com\/sidenotes", 
"articleId":"sidenotes_sample", 
"siteId":"304059", 
"type":"sidenotes" 
}
```

詳しくは、`collectionMeta`トークンを参照してください。

## モバイル設定

サイドは、モバイルデバイスでの使用に最適化されました。 モバイルバージョンのLivefyre Appで最良の結果を得るには、ユーザースケーラブルオプションを「いいえ」に設定します。 例：

```
<meta name="viewport" content="width=device-width, user-scalable=no">
```
