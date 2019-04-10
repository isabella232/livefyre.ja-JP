---
description: 機能APIを使用してプロセスを自動化する
seo-description: 機能APIを使用してプロセスを自動化する
seo-title: 機能API
title: 機能API
uuid: eac3a156-0b60-4ffa-8b6f- e451eb03da77
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 機能API{#feature-apis}

機能APIを使用してプロセスを自動化する

機能APIを使用して、コンテンツが特集されているプロセスを自動化します。例えば、ライブブログまたはコメントアプリを作成する場合、選択したモデレーターが投稿したすべてのコンテンツについて、会話を停止し、ストリーム内の一貫性を確立します。

Livefyreは機能と機能機能のないAPIの両方を提供しています。

## 機能 {#section_jpw_nqw_xz}

**リソース**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/feature/<commentId>/?lftoken=<base64userToken>
```

選択したモデレーターのユーザートークンを入力します。

**投稿データ**

```
{value: <number>} 
```

この値は、特集コンテンツの並べ替えに使用されます。最大から最小までの最大値は、特集コンテンツリストの1より前に表示されます。この値はデフォルトで **エポック** 時に設定されるので、重点的なコメントは通常、新しい順に並べ替えられます。

**応答の例**

```
{"status": "ok", "code": 200, "data": null} 
```

>[!NOTE]
>
>データフィールドはまだ使用されていません。

## 機能不能 {#section_knh_mqw_xz}

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

