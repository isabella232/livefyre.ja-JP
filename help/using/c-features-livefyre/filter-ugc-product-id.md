---
description: 製品IDでUGCをフィルタリングすると、複数のページに完全に同じアプリを埋め込み、各ページに異なる製品固有のUGCを表示できます。
seo-description: 製品IDでUGCをフィルタリングすると、複数のページに完全に同じアプリを埋め込み、各ページに異なる製品固有のUGCを表示できます。
seo-title: 製品IDでUGCをフィルター
title: 製品IDでUGCをフィルター
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: 76efa427b59a709009a3c2d3744ea65e0c959816

---


# 製品IDでUGCをフィルター {#filter-ugc-product-id}

製品IDでUGCをフィルタリングすると、複数のページに完全に同じアプリを埋め込み、各ページに異なる製品固有のUGCを表示できます。

製品IDでUGCをフィルタリングするには、次の手順に従います。

1. Livefyre studioで、タブに移動し **[!UICONTROL Apps]** ます。

1. 変更するアプリを選択します。

1. 左側のパネルで「Designer」タブを選択します。

1. Enable **[!UICONTROL Filter UGC by Product ID]**.

![](assets/filter-ugc-product-id.png)

1. UGCをフィルターする1つまたは複数の製品を含む最上位の製品フォルダーを選択します。
複数のフォルダを選択するには、CtrlキーまたはCommandキーを押しながらクリックします。

1. Disable **[!UICONTROL Show related content]**.
有効にすると、属性を使用してフィルタリングされたコン `data-lf-attr-product` テンツが最初に表示され、その後アプリ内の他のすべてのコンテンツが表示されます。

1. Click **[!UICONTROL Publish]**.

1. フィルターに使用する製品IDを結果のコードに挿入します。

>[!NOTE]
>
>製品IDを探すには、に移動しま **[!UICONTROL Settings > Products]**&#x200B;す。 目的の製品を見つけて選択すると、IDが表示されます。

例えば、Media Wallアプリ用に次のコードが生成されます。

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

製品にタグを付けるには、属性 `<product 1>` 内のを `data-lf-attr-product` 目的の製品IDに置き換えます。 コンマ区切りの製品IDを追加して、1つ以上の製品にタグを付けることができます。 製品は、手順5で選択した最上位の製品フォルダー内に含まれている必要があります。

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

現在は、タグ付き製品IDのみが表示されます。