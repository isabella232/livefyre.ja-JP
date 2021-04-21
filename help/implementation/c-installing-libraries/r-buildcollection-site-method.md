---
title: buildCollectionサイトメソッド
description: buildCollectionサイトメソッド
exl-id: d5c9a2fb-2d30-44f4-8ebf-24b0ec7babee
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 15%

---

# buildCollectionサイトメソッド{#buildcollection-site-method}

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| type | CollectionType | コレクションの種類です。 |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例{#section_nyl_ycs_rz}

```
Collection collection = site.buildCollection(type, title, articleId, url); 
```

## NodeJSの例{#section_xkd_gds_rz}

```
var collection = site.buildCollection(type, title, articleId, url); 
```

## PHPの例{#section_ghf_gds_rz}

```
$collection = site->buildCollection(type, title, articleId, url); 
```

## Pythonの例{#section_dwg_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 
```

## Rubyの例{#section_enh_gds_rz}

```
collection = site.build_collection(type, title, articleId, url) 
```
