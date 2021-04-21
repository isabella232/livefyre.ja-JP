---
description: Comments型としてインスタンス化されたCollectionオブジェクトを返します。 CollectionオブジェクトからcreateOrUpdate()を実行して、ビルドプロセスを完了します。
title: buildCommentsCollectionサイトメソッド
exl-id: 9534c25a-fd1c-4a09-92e2-d196ac218ef3
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 8%

---

# buildCommentsCollectionサイトメソッド{#buildcommentscollection-site-method}

Comments型としてインスタンス化されたCollectionオブジェクトを返します。 CollectionオブジェクトからcreateOrUpdate()を実行して、ビルドプロセスを完了します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例{#section_nyl_ycs_rz}

```
Collection collection = site.buildCommentsCollection(title, articleId, url);
```

## NodeJSの例{#section_xkd_gds_rz}

```
var collection = site.buildCommentsCollection(title, articleId, url); 
```

## PHPの例{#section_ghf_gds_rz}

```
$collection = site->buildCommentsCollection(title, articleId, url); 
```

## Pythonの例{#section_dwg_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 
```

## Rubyの例{#section_enh_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 
```
