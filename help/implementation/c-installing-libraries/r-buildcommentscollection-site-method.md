---
description: コメントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、CollectionオブジェクトからcreateOrUpdate（）を実行します。
seo-description: コメントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、CollectionオブジェクトからcreateOrUpdate（）を実行します。
seo-title: BuildCommentsCollectionサイトのメソッド
solution: Experience Manager
title: BuildCommentsCollectionサイトのメソッド
uuid: 0e5c062e-960d-4ab0- ba32-0965731a1571
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# BuildCommentsCollectionサイトのメソッド{#buildcommentscollection-site-method}

コメントタイプとしてインスタンス化されたCollectionオブジェクトを返します。ビルドプロセスを完了するには、CollectionオブジェクトからcreateOrUpdate（）を実行します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildCommentsCollection(title, articleId, url);
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildCommentsCollection(title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildCommentsCollection(title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 
```

## ルビの例 {#section_enh_gds_rz}

```
collection = site.build_comments_collection(title, articleId, url) 
```
