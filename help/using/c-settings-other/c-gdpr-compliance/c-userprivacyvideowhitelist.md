---
description: ビデオドメインのリストを許可できます。
seo-description: ビデオドメインのリストを許可できます。
seo-title: userPrivacyVideoWhitelist
solution: Experience Manager
title: userPrivacyVideoWhitelist
uuid: adfead18-b73b-4ac4-97a0-d39f528b7606
translation-type: tm+mt
source-git-commit: 52f59cd15f315aa93be198f6eb586f008c18a384
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---


# userPrivacyVideoWhitelist{#userprivacyvideowhitelist}

独自のカスタムビデオおよびプレーヤーをLivefyreのビジュアライゼーションアプリに表示されるビデオの一部として使用する場合、ビデオドメインのリストを許可できます。 ビデオドメインを許可リストに登録すると、カスタムビデオおよびプレーヤーのビデオマスクが削除されます。

>[!NOTE]
>
>特定のパスを使用して、安全なビデオのみを許可リストに記載します。 部分的なパス（例えば、sampledomain.com）を指定すると、安全でないビデオをリストできる場合があります。

* 追加 `userPrivacyVideoWhitelist``userPrivacyOptOut`後に すべてのLivefyreのプライバシーフラグを、1つのLivefyreオブジェクトの一部として一度に追加できます。
* `userPrivacyVideoWhitelist` ソーシャルメディアに埋め込まれていないコンテンツにのみ適用されます。

次の例では、 `sampledomain.com/cdn/videos` パスが指定されたアプリに表示されているビデオを一覧表示します。

```
userPrivacyVideoWhitelist: ["sampledomain.com/cdn/videos"]
```
