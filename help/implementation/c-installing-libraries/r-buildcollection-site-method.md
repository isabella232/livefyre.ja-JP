---
description: 'null'
seo-description: 'null'
seo-title: BuildCollectionサイトのメソッド
solution: Experience Manager
title: BuildCollectionサイトのメソッド
uuid: 52abc42a-9506-4492- b219- f2e05eb79c5f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# BuildCollectionサイトのメソッド{#buildcollection-site-method}

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| type | CollectionType | コレクションのタイプ。 |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildCollection(type, title, articleId, url); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildCollection(type, title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildCollection(type, title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 
```

## ルビの例 {#section_enh_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 
```
