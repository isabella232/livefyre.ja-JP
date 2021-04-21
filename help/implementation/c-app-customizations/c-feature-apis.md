---
description: 機能APIを使用してプロセスを自動化する
title: 機能API
exl-id: 765e47fe-a406-44e6-b4fb-b2e85fc83c01
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# 機能API{#feature-apis}

機能APIを使用してプロセスを自動化する

機能APIを使用して、コンテンツが特集されるプロセスを自動化します。 例えば、ライブブログやコメントアプリを作成する場合、選択したモデレーターが投稿したすべてのコンテンツを特集して会話の舵取りを行い、ストリーム内の一貫性を確立します。

Livefyreオファーの機能APIと機能解除APIの両方

## 機能 {#section_jpw_nqw_xz}

**リソース**

```
POST: https://{networkName}.quill.fyre.co/api/v3.0/collection/<collectionId>/feature/<commentId>/?lftoken=<base64userToken>
```

&#x200B;選択したモデレーターのユーザートークンを入力します。

**投稿データ**

```
{value: <number>} 
```

この値は、特集コンテンツの最大から最小の並べ替えに使用されます(10が特集コンテンツリストの1の前に表示されます)。 この値はデフォルトでエポック時に&#x200B;**now**&#x200B;に設定されるので、特集されたコメントは通常、新しい順に並べ替えられます。

**応答の例**

```
{"status": "ok", "code": 200, "data": null} 
```

>[!NOTE]
>
>データフィールドはまだ使用されていません。

## 機能{#section_knh_mqw_xz}を解除

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
