---
description: Reviews型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
seo-description: Reviews型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
seo-title: buildReviewsCollectionサイトメソッド
solution: Experience Manager
title: buildReviewsCollectionサイトメソッド
uuid: 88af4c68-57de-4ae9-9394-550c94ede48f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 6%

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

