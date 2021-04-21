---
description: Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。
title: CollectionMetaトークンを使用したコレクションの作成
exl-id: d2dafc90-de21-4998-8e85-83f970524329
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# CollectionMetaトークンを使用したコレクションの作成{#create-a-collection-using-the-collectionmeta-token}

Livefyreに渡すcollectionMetaトークンを作成して、新しいコレクションを作成します。

1. collectionMetaトークンを作成します。
1. チェックサムを作成します。

   コレクションに加えた変更をLivefyreに通知する場合は、チェックサムが必要です。 指定されたチェックサムが以前に送信されたチェックサムと異なる場合にのみ、Livefyreはコレクションを更新します。 チェックサムの作成は、`collectionMeta`トークンの作成と同様ですが、`buildCollectionMetaToken`を呼び出す代わりに`buildChecksum`を呼び出します。

Livefyreでの認証用のユーザートークンを作成します。
