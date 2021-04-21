---
description: ビデオドメインを許可リストに含めることができます。
title: userPrivacyVideoWhitelist
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 0%

---


# userPrivacyVideoWhitelist{#userprivacyvideowhitelist}

独自のカスタムビデオおよびプレーヤーをLivefyreのビジュアライゼーションアプリに表示されるビデオの一部として使用する場合、ビデオドメインを許可リストできます。 ビデオドメインを許可リストに登録すると、カスタムビデオおよびプレーヤーのビデオマスクが削除されます。

>[!NOTE]
>
>特定のパスを使用して、安全なビデオのみを許可リストに記載します。 部分一致のパス（例：sampledomain.com）を指定すると、安全でないビデオを許可する場合があります。

* 追加`userPrivacyVideoWhitelist`を`userPrivacyOptOut`の後に置きます。 すべてのLivefyreのプライバシーフラグを、1つのLivefyreオブジェクトの一部として一度に追加できます。
* `userPrivacyVideoWhitelist` ソーシャルメディアに埋め込まれていないコンテンツにのみ適用されます。

次の例では、`sampledomain.com/cdn/videos`パスを持つアプリに表示されているビデオを一覧表示します。

```
userPrivacyVideoWhitelist: ["sampledomain.com/cdn/videos"]
```
