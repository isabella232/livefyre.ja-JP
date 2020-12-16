---
description: Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-description: Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-title: CollectionMetaトークンを使用したコレクションの作成
solution: Experience Manager
title: CollectionMetaトークンを使用したコレクションの作成
uuid: 5a3e18e8-8568-45bb-9070-d0fa43dd819b
translation-type: tm+mt
source-git-commit: 5bf937c8cb1a9ca12216ee1884142b8787ff063e
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# CollectionMetaトークンを使用したコレクションの作成{#create-a-collection-using-the-collectionmeta-token}

Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。

1. collectionMetaトークンを作成します。
1. チェックサムを作成します。

   コレクションに加えた変更をLivefyreに通知する場合は、チェックサムが必要です。 指定されたチェックサムが以前に送信されたチェックサムと異なる場合にのみ、Livefyreはコレクションを更新します。 チェックサムの作成は、`collectionMeta`トークンの作成と同様ですが、`buildCollectionMetaToken`を呼び出す代わりに`buildChecksum`を呼び出します。

Livefyreでの認証用のユーザートークンを作成します。