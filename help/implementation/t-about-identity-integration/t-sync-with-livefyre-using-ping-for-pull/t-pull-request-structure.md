---
description: プル要求構造を構築し、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
title: プル要求構造
exl-id: 70203b23-9d7c-4a22-94ba-2a763e200972
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# プル要求構造{#pull-request-structure}

プル要求構造を構築し、ユーザーIDシステムへのアクセス要求を受け取り、応答します。

LivefyreがエンドポイントURLに対してプルリクエストを発行します。

例えば、プルエンドポイントURLが次のような場合、

```
https://example.yoursite.com/some_path/?id={id}
```

このエンドポイントへのLivefyreのプルリクエストは、次のようになります。

```
https://example.yoursite.com/some_path/?id={id}&lftoken={UserAuthToken}
```

`lftoken`はネットワークキーで署名されたJSON Webトークンで、**[!UICONTROL {userAuthToken}]**&#x200B;はLivefyreによって生成されるユーザー認証トークンです。

1. `lftoken`を使用して、プルURLに対するPingへの要求が悪質なエージェントではなくLivefyreによって送信されたことを検証します。
1. すべての受信要求に対して、次の処理を行います。

   * リクエストに`lftoken`クエリ文字列が存在することを確認します。
   * Livefyreライブラリの`validateLivefyreToken`メソッドを使用して、`lftoken`がネットワークキーで署名されたことを確認します。

   * `lftoken`が存在しない場合、または検証に失敗した場合は、エンドポイントにプロファイル情報の応答を許可しないでください。 代わりに、403（禁止）ステータスコードで応答し、応答本文はありません。

1. `userAuthToken` は、ユーザーのLivefyre `buildUserAuthToken` メソッドによって生成され、ユーザーidは「system」です。このユーザーは、新しいネットワークごとに最初に作成されるユーザーです。
