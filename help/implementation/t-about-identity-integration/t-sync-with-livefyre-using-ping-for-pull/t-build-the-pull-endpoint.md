---
description: プルエンドポイントを構築して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
title: プルエンドポイントの構築
exl-id: cc66365b-0d5f-4a0b-954f-ee014e75d4a2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 0%

---

# プルエンドポイントの構築{#build-the-pull-endpoint}

プルエンドポイントを構築して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。

1. Livefyreリクエストを受け取り、最新のユーザーデータを含むJSONオブジェクトを使用して応答するHTTPSエンドポイントを作成します。

   >[!NOTE]
   >
   >このエンドポイントにアクセスできる必要があります。 また、リクエストと応答の両方をHTTPSプロトコル経由で送信することを強くお勧めします。

1. エンドポイントをStudioに登録します。
