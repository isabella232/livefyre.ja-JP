---
description: サイトまたはネットワークで最もアクティブなコレクションを紹介します。
seo-description: サイトまたはネットワークで最もアクティブなコレクションを紹介します。
seo-title: トレンド
solution: Experience Manager
title: トレンド
uuid: 3031523d- b487-4ea- bba6-5d8f9971874f
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# トレンド{#trending}

サイトまたはネットワークで最もアクティブなコレクションを紹介します。

「トレンド」を使用して、サイトまたはネットワークの最新のアクティビティでコレクションを表示します。

## 統合{#section_wtz_whb_c1b}

トレンドと最も迅速に統合できるのは、LivefyreのCDNでホストされているビルドバージョンです。

まず、ページに [Livefyre. js](https://github.com/Livefyre/Livefyre.js) を追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

次に、アプリが表示される要素を配置します。

```
<div id="trending"></div>
```

最後に、コンポーネントを構築 `Livefyre.require` します。

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

トレンドアプリが表示されるようになりました。この例で [は、すべてを実行](https://codepen.io/gobengo/pen/GijEy)中です。

## 設定 {#section_k5k_qhb_c1b}

`network`

コレクションを取り込むネットワーク。（必須）

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com' 
});
```

`siteId`

ネットワーク内の単一のサイトからのみコレクションを表示するようにサイトIDを指定します。（オプション）。

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4 
});
```

`tag`

単一のコレクションタグを指定して、そのタグを持つコレクションのみを表示します。（オプション）。

```
var trending = new Trending({ 
   el: document.getElementById('trending'), 
   network: 'livefyre.com', 
   siteId: 4, 
   tag: 'basketball' 
});
```

