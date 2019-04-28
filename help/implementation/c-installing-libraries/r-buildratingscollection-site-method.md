---
description: レーティングタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。
seo-description: レーティングタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。
seo-title: BuiltDratingsCollectionサイトメソッド
title: BuiltDratingsCollectionサイトメソッド
uuid: 5eea2ba3-48e1-4cd2- aa73- ea81788af1df
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# BuiltDratingsCollectionサイトメソッド{#buildratingscollection-site-method}

レーティングタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildRatingsCollection(title, articleId, url); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildRatingsCollection(title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildRatingsCollection(title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_ratings_collection(title, articleId, url) 
```

## ルビの例 {#section_enh_gds_rz}

```
collection = site.build_ratings_collection(title, articleId, url) 
```

