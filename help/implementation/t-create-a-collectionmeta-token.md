---
description: Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-description: Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-title: CollectionMetaトークンを使用したコレクションの作成
solution: Experience Manager
title: CollectionMetaトークンを使用したコレクションの作成
uuid: 5a3e18e8-8568-45bb-9070-d0fa43dd819b
translation-type: tm+mt
source-git-commit: 5bf937c8cb1a9ca12216ee1884142b8787ff063e

---


# CollectionMetaトークンを使用したコレクションの作成{#create-a-collection-using-the-collectionmeta-token}

Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。

1. collectionMetaトークンを作成します。
1. チェックサムを作成します。

   コレクションに対して行った変更をLivefyreに通知する場合は、チェックサムが必要です。 Livefyreは、指定されたチェックサムが以前に送信されたチェックサムと異なる場合にのみ、コレクションを更新します。 チェックサムの作成は、トークンの作成と同じですが、 `collectionMeta` 呼び出す代わりに、を呼び出すこ `buildCollectionMetaToken` とになりま `buildChecksum`す。

Livefyreでの認証用のユーザートークンを作成します。