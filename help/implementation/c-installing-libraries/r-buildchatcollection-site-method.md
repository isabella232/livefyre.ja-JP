---
description: Chat型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
seo-description: Chat型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。
seo-title: buildChatCollectionサイトメソッド
solution: Experience Manager
title: buildChatCollectionサイトメソッド
uuid: 39ee32d0-29c9-47a8-a458-a3cf7a96db30
translation-type: tm+mt
source-git-commit: 2908c6988c706a49c391f0e607bb641bce3a7f0d

---


# buildChatCollectionサイトメソッド{#buildchatcollection-site-method}

Chat型としてインスタンス化されたCollectionオブジェクトを返します。 Collectionオブジェクトからcreate_or_update()を実行し、ビルドプロセスを完了します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| title | 文字列 | コレクションのタイトル。 |
| articleId | 文字列 | サイト内のコレクションを識別するために選択した一意の記事ID。 |
| url | 文字列 | このコレクションの正規の絶対URLです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
Collection collection = site.buildChatCollection(title, articleId, url); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var collection = site.buildChatCollection(title, articleId, url); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection = site->buildChatCollection(title, articleId, url); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection = site.build_chat_collection(title, articleId, url) 
```

## Rubyの例 {#section_enh_gds_rz}

```
collection = site.build_chat_collection(title, articleId, url)
```
