---
description: 製品IDごとにUGCをフィルターすると、各ページに異なる製品固有のUGCを表示しながら、同一のアプリを複数のページに埋め込むことができます。
seo-description: 製品IDごとにUGCをフィルターすると、各ページに異なる製品固有のUGCを表示しながら、同一のアプリを複数のページに埋め込むことができます。
seo-title: 製品ID別のUGCのフィルター
title: 製品ID別のUGCのフィルター
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: 76efa427b59a709009a3c2d3744ea65e0c959816

---


# 製品ID別のUGCのフィルター {#filter-ugc-product-id}

製品IDごとにUGCをフィルターすると、各ページに異なる製品固有のUGCを表示しながら、同一のアプリを複数のページに埋め込むことができます。

製品IDでUGCをフィルターするには、次の手順に従います。

1. Livefyre Studioで、タブに **[!UICONTROL Apps]** 移動します。

1. 変更するアプリを選択します。

1. 左側のパネルで&quot;Designer&quot;タブを選択します。

1. 有効 **[!UICONTROL Filter UGC by Product ID]** 化

![](assets/filter-ugc-product-id.png)

1. UGCをフィルターする製品または製品を含むトップレベルの製品フォルダを選択します。
複数のフォルダを選択するには、CtrlまたはCommandキーを押しながらクリックします。

1. 無効 **[!UICONTROL Show related content]** にします。
有効にすると `data-lf-attr-product` 、属性を使用してフィルターされたコンテンツが最初に表示され、その後にアプリ内の他のすべてのコンテンツが表示されます。

1. **[!UICONTROL Publish]** をクリックします。

1. フィルタリングする製品IDを、結果のコードに挿入します。

>[!NOTE]
>
>製品IDを探すには、に移動 **[!UICONTROL Settings > Products]** します。目的の製品を見つけて選択し、IDを表示します。

例えば、Mediaウォールアプリ用に次のコードが生成されます。

```
<script type="text/javascript" src="https://cdn.livefyre.com/
Livefyre.js"></script><div class="lf-app-embed" data-lfapp="
59dc41fa-85a5-49ed-8d60-d74616b3ccd1/tagged/published" datalf-
env="prod" data-lf-read-only="" data-lf-attr-product="<product
 1>,<product 2>"></div><script>Livefyre.require(["app-embed#1.0.11"],
 function (appEmbed) {appEmbed.loadAll().done(function(embed)
 {embed = embed[0];if (embed.el.onload && embed.getConfig)
 {embed.el.onload(embed.getConfig());}});});</script>
```

製品にタグ付けするには、 `<product 1>``data-lf-attr-product` 属性内で目的の製品IDを置き換えます。コンマ区切りの製品IDを追加して、1つまたは複数の製品にタグを付けることができます。製品は、手順5で選択したトップレベルの製品フォルダーまたはフォルダー内に含まれている必要があります。

変更されたコードセグメントは次のように表示されます。

```
<script type="text/javascript" src="https://cdn.livefyre.com/
Livefyre.js"></script><div class="lf-app-embed" data-lfapp="
59dc41fa-85a5-49ed-8d60-d74616b3ccd1/tagged/published"
 data-lf-env="prod" data-lf-read-only="" data-lf-attrproduct="
109,47"></div><script>Livefyre.require(["app-embed#1.0.11"],
 function (appEmbed) {appEmbed.loadAll().done(function(embed)
 {embed = embed[0];if (embed.el.onload && embed.getConfig)
 {embed.el.onload(embed.getConfig());}});});</script>
```

これで、タグ付き製品IDのみがアプリケーションに表示されます。