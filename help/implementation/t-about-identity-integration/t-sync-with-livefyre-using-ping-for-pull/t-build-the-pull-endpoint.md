---
description: プルエンドポイントを構築して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
seo-description: プルエンドポイントを構築して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
seo-title: プルエンドポイントの構築
solution: Experience Manager
title: プルエンドポイントの構築
uuid: 1703152f-aaa7-4a88-aa33-d9f8957ad42b
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%

---


# プルエンドポイントの構築{#build-the-pull-endpoint}

プルエンドポイントを構築して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。

1. Livefyreリクエストを受け取り、最新のユーザーデータを含むJSONオブジェクトを使用して応答するHTTPSエンドポイントを作成します。

   >[!NOTE]
   >
   >このエンドポイントにアクセスできる必要があります。 また、リクエストと応答の両方をHTTPSプロトコル経由で送信することを強くお勧めします。

1. エンドポイントをStudioに登録します。
