---
description: Sident型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
title: buildSitenotesCollectionサイトメソッド
exl-id: c722baf2-91d4-4c05-97e1-ea585e91c416
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 8%

---

# buildSitenotesCollectionサイトメソッド{#buildsitenotescollection-site-method}

Sident型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例{#section_nyl_ycs_rz}

```
Collection collection = site.buildSidenotesCollection(title, articleId, url); 
```

## NodeJSの例{#section_xkd_gds_rz}

```
var collection = site.buildSidenotesCollection(title, articleId, url); 
```

## PHPの例{#section_ghf_gds_rz}

```
$collection = site->buildSidenotesCollection(title, articleId, url); 
```

## Pythonの例{#section_dwg_gds_rz}

```
collection = site.build_sidenotes_collection(title, articleId, url) 
```

## Rubyの例{#section_enh_gds_rz}

```
collection = site.build_sidenotes_collection(title, articleId, url) 
```
