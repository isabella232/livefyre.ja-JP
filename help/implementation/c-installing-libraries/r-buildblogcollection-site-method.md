---
description: ブログタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_
  or_ update（）を実行します。
seo-description: ブログタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_
  or_ update（）を実行します。
seo-title: buildbLogCollectionサイトのメソッド
solution: Experience Manager
title: buildbLogCollectionサイトのメソッド
uuid: 6a5ec6b9- bc32-467a- aba6- a57c6defe067
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# buildbLogCollectionサイトのメソッド{#buildblogcollection-site-method}

ブログタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、Collectionオブジェクトからcreate_ or_ update（）を実行します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildBlogCollection(title, articleId, url); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildBlogCollection(title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildBlogCollection(title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_blog_collection(title, articleId, url) 
```

## ルビの例 {#section_enh_gds_rz}

```
collection = site.build_blog_collection(title, articleId, url) 
```

