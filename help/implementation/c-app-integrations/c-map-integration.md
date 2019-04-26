---
description: インタラクティブマップにユーザーコンテンツをプロットします。
seo-description: インタラクティブマップにユーザーコンテンツをプロットします。
seo-title: マップ
solution: Experience Manager
title: マップ
uuid: 1c3e399d- a610-4b80- a3b2- a5502b31480d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# マップ{#map}

インタラクティブマップにユーザーコンテンツをプロットします。

マップを使用すると、地理的なコンテンツを世界地図にストリーミングでき、ニュースやライブイベントの周囲にソーシャルバズを見つけることができます。テキスト、コメント、写真、ツイートなど、すべての該当するコンテンツが表示されます。

>[!NOTE]
>
>マップは [、LiveFyreがマップをレンダリングするデータを提供する© OpenStreamMap](https://www.openstreetmap.org/copyright)によって動作します。

## 統合{#section_w2m_db2_d1b}

Mapを最も迅速に使用するには、LivefyreのCDNでホストされているビルドバージョンを使用します。

まず、ページに [Livefyre. js](https://github.com/Livefyre/Livefyre.js) を追加します。

```
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
```

次に、アプリをマップする要素を配置します。

```
<div id="map" style="height: 500px;"></div>
```

最後に、Livefyre.を使用してMapを構築し、StreamHub- sdkからパイプするコレクションを取得します。マップには、ジオタグ付きメタデータを含むコンテンツのみが表示されることに注意してください。TwitterおよびInstagramキュレーションでは、この機能がサポートされています。最高のパフォーマンスを確保するには、コレクションのすべてのキュレーションルールに位置情報フィルターを含めます。

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

[このライブ例](https://codepen.io/cheung31/pen/wkmbF)をご覧ください。

## 設定 {#section_jc5_gxb_c1b}

`initial`

コレクションから読み込んでマップに表示する項目の初期数です。この番号が読み込まれると、ユーザーはボタンをクリックしてさらに表示できます。（オプション）。初期設定は50です。）

```
var map = new Map({ 
    el: document.getElementById('map'), 
    initial: 100 
});
```

`leafletMapOptions`

基本 [的なスポットライト](https://leafletjs.com/) マップに渡すオプションで、レンダリングによってレンダリングが使用されます。このオプションを使用すると、マップの初期中心点と最大ズームレベルを含む [、スポットライトマップオプション](https://leafletjs.com/reference.html#map-options)を設定できます。（オプション）。

```
var map = new Map({ 
    el: document.getElementById('map'), 
    leafletMapOptions: { 
        center: [37.774, -122.4], 
        zoom: 15 
    } 
});
```

