---
description: サイトまたはネットワーク上で最もアクティブなコレクションを表示します。
title: トレンド
exl-id: a3129e95-90e7-4107-bfd9-ed3b0dce20aa
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '140'
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
