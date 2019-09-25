---
description: プル要求構造を作成して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
seo-description: プル要求構造を作成して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。
seo-title: プル要求構造
solution: Experience Manager
title: プル要求構造
uuid: bf6b9e45-d08a-48e6-acc6-e4fa56428d25
translation-type: tm+mt
source-git-commit: cf447db2cb3498fcb01b511848faeee4d1e48481

---


# プル要求構造{#pull-request-structure}

プル要求構造を作成して、ユーザーIDシステムへのアクセス要求を受け取り、応答します。

LivefyreがエンドポイントURLにプルリクエストを発行します。

例えば、プルエンドポイントURLが次のような場合、

```
https://example.yoursite.com/some_path/?id={id}
```

このエンドポイントへのLivefyre Pullリクエストは、次のようになります。

```
https://example.yoursite.com/some_path/?id={id}&lftoken={UserAuthToken}
```

ここで `lftoken` は、ネットワークキーで署名されたJSON webトークンで、Livefyreによって生 **[!UICONTROL {userAuthToken}]** 成されたユーザー認証トークンです。

1. Pingで取り込 `lftoken` みURLに対する要求が、悪意のあるエージェントではなくLivefyreによって送信されたことを検証する場合に使用します。
1. すべての受信要求に対して：

   * クエリ文字列がリク `lftoken` エストに存在することを確認します。
   * Livefyreライブラリ `validateLivefyreToken` のメソッドを使用して、がネットワークキーで署名さ `lftoken` れていることを確認します。

   * が存在し `lftoken` ない場合、または検証に失敗した場合は、エンドポイントにプロファイル情報の応答を許可しないでください。 代わりに、403 （禁止）ステータスコードを使用し、応答本文を使用しないで応答します。

1. `userAuthToken` は、ユーザーIDが「system」 `buildUserAuthToken` のLivefyreメソッドによって生成されます。 このユーザーは、新しいネットワークごとに最初に作成されるユーザーです。
