---
description: Livefyreに渡されるCollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-description: Livefyreに渡されるCollectionMetaトークンを作成して、新しいコレクションを作成します。
seo-title: CollectionMetaトークンを使用したコレクションの作成
solution: Experience Manager
title: CollectionMetaトークンを使用したコレクションの作成
uuid: 5a3e18e8-8568-45bb-9070- d0fa43dd819b
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# CollectionMetaトークンを使用したコレクションの作成{#create-a-collection-using-the-collectionmeta-token}

Livefyreに渡されるCollectionMetaトークンを作成して、新しいコレクションを作成します。

1. CollectionMetaトークンを作成します。
1. チェックサムを作成します。

   コレクションに対して行った変更をLivefyreに通知する場合は、チェックサムが必要です。Livefyreは、提供されたチェックサムが以前に送信したチェックサムと異なる場合にのみ、コレクションを更新します。チェックサムの作成は、トークンを作成するのではなく `collectionMeta` 、トークンを作成するのと `buildCollectionMetaToken` 同じ `buildChecksum`です。

Livefyreを認証するためのユーザートークンを作成します。