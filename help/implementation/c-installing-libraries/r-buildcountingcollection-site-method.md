---
description: カウントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。
seo-description: カウントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。
seo-title: BuildCountingCollectionサイトのメソッド
title: BuildCountingCollectionサイトのメソッド
uuid: e293d66a-0025-4230-997e-295ce4625713
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# BuildCountingCollectionサイトのメソッド{#buildcountingcollection-site-method}

カウントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildCountingCollection(title, articleId, url); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildCountingCollection(title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildCountingCollection(title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_counting_collection(title, articleId, url) 
```

## ルビの例 {#section_enh_gds_rz}

```
collection = site.build_counting_collection(title, articleId, url) 
```

