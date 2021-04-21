---
description: ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。
title: Pingの構築
exl-id: 626c200b-eaff-483f-b1eb-7d8993fe5e7c
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 0%

---

# Ping{#build-the-ping}を構築する

ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。

`networkName`と`user_id`のアップデート通知を受け取ると、PingにプルURLを要求するプル要求が送信されます。

>[!NOTE]
>
>403/Not Authorized in response to your Pingは、無効な`lftoken`がPing要求に追加されたことを示します。 `lftoken`がネットワーク所有者権限を持つ`user_id`またはシステムユーザー用であることを確認してください。 Livefyreライブラリを使用している場合は、`buildLivefyreToken`メソッドを使用して、リクエストに対して有効なシステムトークンを生成します。

1. ユーザーがプロファイルを追加更新したときにLivefyreにpingを送信するコード。 次のようにURLを作成します。

   ```
   POSThttps://{networkName}.quill.fyre.co/api/v3.0/user/{user_id}/refresh?lftoken={token}
   ```

   * **[!UICONTROL networkName:]** Livefyreから提供されたネットワーク名。
   * **[!UICONTROL user_id:]** ユーザーのID。
   * **[!UICONTROL token:]** 有効なシステムトークン。

1. リクエスト構造を取り込みます。
