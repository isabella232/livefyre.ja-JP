---
description: サイトまたはネットワーク上で最もアクティブなコレクションを表示します。
seo-description: サイトまたはネットワーク上で最もアクティブなコレクションを表示します。
seo-title: トレンド
solution: Experience Manager
title: トレンド
uuid: 3031523d-b487-4eea-bba6-5d8f9971874f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

---


# トレンド{#trending}

サイトまたはネットワーク上で最もアクティブなコレクションを表示します。

「トレンド」を使用して、サイトまたはネットワーク内の最新のアクティビティでコレクションを表示します。

## 統合 {#section_wtz_whb_c1b}

トレンド分析との統合に最も迅速な方法は、LivefyreのCDN上でホストされているビルトバージョンを使用することです。

まず、[Livefyre.js](https://github.com/Livefyre/Livefyre.js)をページに追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

次に、アプリを表示する要素を配置します。

```
<div id="trending"></div>
```

最後に、`Livefyre.require`を使用してコンポーネントを構築します。

```
<script> 
Livefyre.require([ 
   'streamhub-hot-collections#0' 
], function(Trending) {     
   var app = new Trending({ 
      el: document.getElementById("trending"), 
      network: 'livefyre.com' 
   }); 
   app.start(); 
}); 
</script>
```

トレンド分析アプリが作成されました。 [この例](https://codepen.io/gobengo/pen/GijEy)で実際に起こっているものをすべて見て下さい。

## 設定 {#section_k5k_qhb_c1b}

`network`

コレクションの取り込み元のネットワークです。 (必須.)

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com' 
});
```

`siteId`

ネットワーク内の1つのサイトからのみコレクションを表示するサイトIDを指定します。 （オプション）

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4 
});
```

`tag`

単一のコレクションタグを指定して、そのタグを持つコレクションのみを表示します。 （オプション）

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4, 
   tag: 'basketball' 
});
```

