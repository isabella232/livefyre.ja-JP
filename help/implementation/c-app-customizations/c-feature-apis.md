---
description: 機能APIを使用したプロセスの自動化
seo-description: 機能APIを使用したプロセスの自動化
seo-title: 機能API
title: 機能API
uuid: eac3a156-0b60-4ffa-8b6f-e451eb03da77
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 機能API{#feature-apis}

機能APIを使用したプロセスの自動化

機能APIを使用して、コンテンツが特集されるプロセスを自動化します。 例えば、ライブブログやコメントアプリを作成する場合、選択したモデレーターによって投稿されたすべてのコンテンツを特集して会話の舵取りを行い、ストリーム内の一貫性を確立します。

Livefyreは、機能APIと機能解除APIの両方を提供しています。

## 機能 {#section_jpw_nqw_xz}

**リソース**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/feature/<commentId>/?lftoken=<base64userToken>
```

選択し&#x200B;たモデレーターのユーザートークンを入力します。

**投稿データ**

```
{value: <number>} 
```

この値を使用して、特集コンテンツを最大から最小の順に並べ替えます（10が重点コンテンツリストの1より前に表示されます）。 この値はデフォルトでエポ **ック時** になったので、特集されたコメントは通常、新しい順に並べ替えられます。

**応答の例**

```
{"status": "ok", "code": 200, "data": null} 
```

>[!NOTE]
>
>データフィールドはまだ使用されていません。

## 機能解除 {#section_knh_mqw_xz}

**リソース**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/unfeature/<commentId>/?lftoken=<base64userToken>
```

選択したモデレーターのユーザートークンを入力します。

**応答の例**

```
{"status": "ok", "code": 200, "data": null} 
```

>[!NOTE]
>
>データフィールドはまだ使用されていません。

