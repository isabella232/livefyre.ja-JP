---
description: ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。
seo-description: ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。
seo-title: Pingの構築
solution: Experience Manager
title: Pingの構築
uuid: cb8cc043-9ea5-407c-b70f-3f1e37accdae
translation-type: tm+mt
source-git-commit: f76dcd31e58b94856bf551009c2ac50c3233e516

---


# Pingの構築{#build-the-ping}

ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。

Livefyreは、とと共に更新通知を受け取る `networkName``user_id`と、プルURLを取得するためにPingにプル要求を送信します。

>[!NOTE]
>
>403/Not Authorized in response to your Pingは、無効な値がPing要求に追加されたこ `lftoken` とを示します。 がネットワーク所有者権限 `lftoken` を持つユーザーまたはシステムユーザー `user_id` のためのものであることを確認してください。 Livefyreライブラリを使用している場合は、この `buildLivefyreToken` 方法を使用して、リクエストに対して有効なシステムトークンを生成します。

1. ユーザーがプロファイルを追加更新したときにLivefyreにpingを送信するコード。 次のようにURLを作成します。

   ```
   POSThttps://{networkName}.quill.fyre.co/api/v3.0/user/{user_id}/refresh?lftoken={token}
   ```

   * **[!UICONTROL networkName:]** Livefyreから提供されたネットワーク名。
   * **[!UICONTROL user_id:]** ユーザーのID。
   * **[!UICONTROL token:]** 有効なシステムトークン。

1. リクエスト構造を取り込みます。
