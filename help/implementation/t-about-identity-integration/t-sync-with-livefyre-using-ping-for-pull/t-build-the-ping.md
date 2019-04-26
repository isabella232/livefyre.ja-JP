---
description: ユーザーがプロファイルを更新したときにページがLivefyreにpingされるようにpingを作成します。
seo-description: ユーザーがプロファイルを更新したときにページがLivefyreにpingされるようにpingを作成します。
seo-title: Pingを構築する
solution: Experience Manager
title: Pingを構築する
uuid: cb8cc043-9ea5-407c- b70f-3f1e37acccae
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Pingを構築する{#build-the-ping}

ユーザーがプロファイルを更新したときにページがLivefyreにpingされるようにpingを作成します。

Livefyreが更新通知を受信すると、PullリクエストがPing `networkName``user_id`for Pull URLに送信されます。

>[!NOTE]
>
>403/Pingに応答して認証されていない場合、Pingリクエストには無効 `lftoken` な追加が付加されます。ネットワーク所有者の権限 `lftoken` またはシステムユーザー `user_id` があることを確認してください。Livefyreライブラリを使用している場合は `buildLivefyreToken` 、そのリクエスト用に有効なシステムトークンを生成する方法を使用します。

1. ユーザーがプロファイルを更新したときにLivefyreをpingするページにコードを追加します。次のURLを作成します。

```
 POSThttps://{networkName}.quill.fyre.co/api/v3.0/user/{user_id}/refresh?lftoken={token}
```

* **[!UICONTROL networkName:]** Livefyreが提供するネットワーク名。
* **[!UICONTROL user_id:]** ユーザーのID。
* **[!UICONTROL token:]** 有効なシステムトークン。

1. リクエスト構造を取り込みます。
