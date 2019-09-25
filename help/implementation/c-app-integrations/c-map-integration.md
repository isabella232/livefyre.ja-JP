---
description: ユーザコンテンツをインタラクティブマップにプロットします。
seo-description: ユーザコンテンツをインタラクティブマップにプロットします。
seo-title: マップ
solution: Experience Manager
title: マップ
uuid: 1c3e399d-a610-4b80-a3b2-a5502b31480d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# マップ{#map}

ユーザコンテンツをインタラクティブマップにプロットします。

Mapを使用すると、ジオタグ付きのコンテンツを世界地図上にストリーミングし、ニュースやライブイベントの発生に関するソーシャルバズを見つけることができます。 テキスト、コメント、写真、ツイートを含む、該当するすべてのコンテンツが表示されます。

>[!NOTE]
>
>マップは「 [OpenStreetMap」で動作します](https://www.openstreetmap.org/copyright)。これは、Livefyreがマップをレンダリングする際に使用するデータを提供します。

## 統合 {#section_w2m_db2_d1b}

Mapを最もすばやく使用するには、LivefyreのCDN上でホストされているビルドバージョンを使用します。

まず、 [Livefyre.jsをページに追加します](https://github.com/Livefyre/Livefyre.js) 。

```
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
```

次に、Map appが表示される要素を配置します。

```
<div id="map" style="height: 500px;"></div>
```

最後に、Livefyre.requireを使用してマップを作成し、streamhub-sdkからパイプインするコレクションを取得します。 マップに表示できるのは、ジオタグ付きメタデータを含むコンテンツのみです。 この機能は、TwitterおよびInstagram Curateでサポートされています。 最高のパフォーマンスを確保するには、コレクションのキュレーションルールすべてに位置情報フィルターを含めます。

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

このライブ例をご [覧ください](https://codepen.io/cheung31/pen/wkmbF)。

## 設定 {#section_jc5_gxb_c1b}

`initial`

コレクションから読み込んでマップに表示する初期項目数。 この番号が読み込まれると、ユーザーはボタンをクリックしてさらに表示できます。 （オプション。初期設定は50です)。

```
var map = new Map({ 
    el: document.getElementById('map'), 
    initial: 100 
});
```

`leafletMapOptions`

基になるリーフレットマップに渡すオ [プション](https://leafletjs.com/) 。Mapはこのマップをレンダリングに使用します。 このオプションを使用して、「チ [ラシマップのオプション](https://leafletjs.com/reference.html#map-options)」（マップの初期中心点を含む）と、初期ズームレベルと最大ズームレベルを設定します。 （オプション）

```
var map = new Map({ 
    el: document.getElementById('map'), 
    leafletMapOptions: { 
        center: [37.774, -122.4], 
        zoom: 15 
    } 
});
```

