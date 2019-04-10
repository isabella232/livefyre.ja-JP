---
description: コアアプリケーションと同様のプロセスに従って、アプリをSocializeに統合します。
seo-description: コアアプリケーションと同様のプロセスに従って、アプリをSocializeに統合します。
seo-title: Sidees統合
solution: Experience Manager
title: Sidees統合
uuid: 4aa14ada-402a-482d- b43e-96f37afa6c53
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Sidees統合{#sidenotes-integration}

コアアプリケーションと同様のプロセスに従って、アプリをSocializeに統合します。

原則として、コアアプリケーション統合が完了している場合、 `collectionMeta` オブジェクトを生成するために記述されたコードは、Sideingで再利用できます。

（オプション）フィールドのSideingによって作成された委任を指定することで、既存 `auth``auth``fyre.conv` のデリゲートを再利用 `authDelegate` することもできます。

>[!NOTE]
>
>siposingを使用すると、 `network`コンストラクター `siteId``articleId` の他の部分で個別に渡す代わりに、単一のオブジェクトを含めることができます。

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

"Building `collectionMeta` 」セクションに記述されているとおり、 `collectionMeta` エンコードされたJSONオブジェクトです。上記の例では、JSONオブジェクトはJWTエンコード前に次の形式を使用しています。

```
{ 
"title":"Client Solutions Sidenotes", 
"url":"http:\/\/www.livefyre.com\/sidenotes", 
"articleId":"sidenotes_sample", 
"siteId":"304059", 
"type":"sidenotes" 
}
```

詳しくは `collectionMeta` 、トークンを参照してください。

## モバイル設定

Socialは、モバイルデバイスでの使用に最適化されています。Livefyreアプリケーションのモバイルバージョンで最良の結果を得るには、ユーザーにスケーラブルなオプションを設定しないでください。次に例を示します。

```
<meta name="viewport" content="width=device-width, user-scalable=no">
```
