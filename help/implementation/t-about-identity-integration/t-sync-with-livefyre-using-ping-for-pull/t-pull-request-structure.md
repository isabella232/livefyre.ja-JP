---
description: ユーザーIDシステムへのアクセスの要求を受信し、応答するためのプルリクエスト構造を構築します。
seo-description: ユーザーIDシステムへのアクセスの要求を受信し、応答するためのプルリクエスト構造を構築します。
seo-title: プルリクエストの構造
solution: Experience Manager
title: プルリクエストの構造
uuid: bf6b9e45- d08a-48e6- acc6- e4fa56428d25
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# プルリクエストの構造{#pull-request-structure}

ユーザーIDシステムへのアクセスの要求を受信し、応答するためのプルリクエスト構造を構築します。

エンドポイントURLにプル要求を発行します。

例えば、プルエンドポイントURLが次のようになっているとします。

```
https://example.yoursite.com/some_path/?id={id}
```

このエンドポイントへのLivefyre Pullリクエストは次のようになります。

```
https://example.yoursite.com/some_path/?id={id}&lftoken={UserAuthToken}
```

は `lftoken` 、ネットワークキーで署名されたJSON Webトークンで、 **[!UICONTROL {userAuthToken}]** Livefyreによって生成されるユーザー認証トークンです。

1. Ping `lftoken` for Pull URLに対するPingへのリクエストが、悪意のあるエージェントではなくLivefyreに送信されることを検証するために使用します。
1. すべての受信リクエストの場合:

   * クエリ文字列が `lftoken` リクエストに存在することを確認します。
   * Livefyreライブラリの `validateLivefyreToken` メソッドを使用して、ネットワークキーで署名 `lftoken` されていることを確認します。

   * 存在しないか `lftoken` 、検証に失敗した場合は、エンドポイントがプロファイル情報で応答することを許可しないでください。代わりに、403（Forbidden）ステータスコードに応答し、応答本文を使用しないでください。

1. `userAuthToken` はユーザーのLivefyre `buildUserAuthToken` メソッドによって生成され、ユーザーIDは"system"になります。このユーザーは、新規ネットワークごとに作成される最初のユーザーです。
1. ページをテストするには、Ping for [Pull](https://livefyre-p4p-wizard.herokuapp.com/home) Testerを使用して、すべてが期待どおりに動作することを確認してください。
