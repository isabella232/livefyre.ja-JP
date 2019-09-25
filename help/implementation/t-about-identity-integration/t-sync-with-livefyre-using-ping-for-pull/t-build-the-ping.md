---
description: ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。
seo-description: ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。
seo-title: Pingの構築
solution: Experience Manager
title: Pingの構築
uuid: cb8cc043-9ea5-407c-b70f-3f1e37accde
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Pingの構築{#build-the-ping}

ユーザーがプロファイルを更新したときにLivefyreにpingを送信するようにpingを作成します。

Livefyreがとと共に更新通知を受け取る `networkName` と、プ `user_id`ルURLを求めるプル要求がPingに送信されます。

>[!NOTE]
>
>「403/Not Authorized in response to your Ping」は、Ping要求に無効な値が追加さ `lftoken` れたことを示します。 がネットワーク所有者権限を `lftoken` 持つユーザーまたはシ `user_id` ステムユーザーのためのものであることを確認してください。 Livefyreライブラリを使用している場合は、このメソッドを使用 `buildLivefyreToken` して、リクエストに対して有効なシステムトークンを生成します。

1. ユーザーがプロファイルを更新したときにLivefyreにpingを送信するコードをページに追加します。 次のようにURLを作成します。

```
 POSThttps://{networkName}.quill.fyre.co/api/v3.0/user/{user_id}/refresh?lftoken={token}
```

* **[!UICONTROL networkName:]** Livefyreが提供するネットワーク名。
* **[!UICONTROL user_id:]** ユーザーのID。
* **[!UICONTROL token:]** 有効なシステムトークン。

1. リクエスト構造を取り込みます。
