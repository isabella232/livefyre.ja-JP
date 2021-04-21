---
description: Reviews型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
title: buildReviewsCollectionサイトメソッド
exl-id: 581ad24c-d115-4ffb-93eb-936c2da6e3fa
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 8%

---

# buildReviewsCollectionサイトメソッド{#buildreviewscollection-site-method}

Reviews型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |


## Javaの例{#section_nyl_ycs_rz}

```
Collection collection = site.buildReviewsCollection(title, articleId, url); 
```

## NodeJSの例{#section_xkd_gds_rz}

```
var collection = site.buildReviewsCollection(title, articleId, url); 
```

## PHPの例{#section_ghf_gds_rz}

```
$collection = site->buildReviewsCollection(title, articleId, url); 
```

## Pythonの例{#section_dwg_gds_rz}

```
collection = site.build_reviews_collection(title, articleId, url) 
```

## Rubyの例{#section_enh_gds_rz}

```
collection = site.build_reviews_collection(title, articleId, url) 
```
