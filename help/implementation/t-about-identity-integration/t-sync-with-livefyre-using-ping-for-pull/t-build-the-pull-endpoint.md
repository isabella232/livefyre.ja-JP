---
description: ユーザーIDシステムへのアクセスの要求を受信し、応答するために、プルエンドポイントを構築します。
seo-description: ユーザーIDシステムへのアクセスの要求を受信し、応答するために、プルエンドポイントを構築します。
seo-title: プルエンドポイントの構築
solution: Experience Manager
title: プルエンドポイントの構築
uuid: 1703152f- aaa7-4a88- aa33- d9f8957ad42b
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# プルエンドポイントの構築{#build-the-pull-endpoint}

ユーザーIDシステムへのアクセスの要求を受信し、応答するために、プルエンドポイントを構築します。

1. Livefyreリクエストを受信し、最新のユーザーデータを含むJSONオブジェクトで応答するHTTPSエンドポイントを作成します。

   >[!NOTE]
   >
   >このエンドポイントにアクセスできる必要があります。また、HTTPSプロトコルでリクエストと応答の両方を送信することを強くお勧めします。

1. エンドポイントをStudioに登録します。
