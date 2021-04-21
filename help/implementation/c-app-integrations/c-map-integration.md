---
description: ユーザコンテンツをインタラクティブマップにプロットします。
title: マップ
exl-id: 836b475e-0ec6-49f8-b89f-3af3209cf1f2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 2%

---

# マップ{#map}

ユーザコンテンツをインタラクティブマップにプロットします。

Mapを使用すると、ジオタグ付きのコンテンツをワールドマップにストリーミングし、ニュースやライブイベントの周りのソーシャルバズを見つけることができます。 テキスト、コメント、写真、ツイートなど、該当するすべてのコンテンツが表示されます。

>[!NOTE]
>
>マップには[©OpenStreetMap](https://www.openstreetmap.org/copyright)が電源を供給します。これは、マップのレンダリングにLivefyreが使用するデータを提供します。

## 統合 {#section_w2m_db2_d1b}

Mapを最もすばやく使用するには、LivefyreのCDN上でホストされているビルドバージョンを使用します。

まず、[Livefyre.js](https://github.com/Livefyre/Livefyre.js)をページに追加します。

```
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
```

次に、マップアプリが表示される要素を配置します。

```
<div id="map" style="height: 500px;"></div>
```

最後に、Livefyre.requireを使用してマップを作成し、streamhub-sdkからパイプインするコレクションを取得します。 マップには、ジオタグ付きメタデータを含むコンテンツのみを表示できることに注意してください。 この機能は、twitterとInstagramキュレートでサポートされています。 最高のパフォーマンスを確保するには、コレクションのキュレーションルールすべてに位置情報フィルターを含めます。

```
<script> 
Livefyre.require(['streamhub-map#1', 'streamhub-sdk#2'], 
function (Map, SDK) { 
    var map = new Map({ 
        el: document.getElementById('map') 
    }); 
    var collection = new SDK.Collection({ 
        network: 'strategy-prod.fyre.co', 
        siteId: 340628, 
        articleId: 'custom-1389845009515' 
    }); 
    collection.pipe(map); 
}); 
</script>
```

この[ライブサンプル](https://codepen.io/cheung31/pen/wkmbF)をご覧ください。

## 設定 {#section_jc5_gxb_c1b}

`initial`

コレクションから読み込んでマップに表示する初期項目数。 この数値が読み込まれた後、ユーザーがボタンをクリックすると、さらに表示される場合があります。 （オプション。初期設定は50です)。

```
var map = new Map({ 
    el: document.getElementById('map'), 
    initial: 100 
});
```

`leafletMapOptions`

基になる[Breeflet](https://leafletjs.com/)マップに渡すオプション。Mapはこのマップをレンダリングに使用します。 このオプションを使用して、マップの初期中心点、初期ズームレベルと最大ズームレベルを含む、[チラシマップオプション](https://leafletjs.com/reference.html#map-options)を設定します。 （オプション）

```
var map = new Map({ 
    el: document.getElementById('map'), 
    leafletMapOptions: { 
        center: [37.774, -122.4], 
        zoom: 15 
    } 
});
```
