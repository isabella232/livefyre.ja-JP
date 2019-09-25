---
description: You can whitelist your video domain using .
seo-description: を使用して、ビデオドメインをホワイトリストに登録できます。
seo-title: userPrivacyVideoWhitelist
solution: Experience Manager
title: userPrivacyVideoWhitelist
uuid: adfead18-b73b-4ac4-97a0-d39f528b7606
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# userPrivacyVideoWhitelist{#userprivacyvideowhitelist}

独自のカスタムビデオおよびプレーヤーをLivefyreビジュアライゼーションアプリに表示するビデオの一部として使用する場合、ビデオドメインをホワイトリストに登録できます。 ビデオドメインをホワイトリストに登録すると、カスタムビデオおよびプレーヤーのビデオマスクが削除されます。

>[!NOTE]
>
>特定のパスを使用して、安全なビデオのみをホワイトリストに登録します。 部分一致のパス（例：sampledomain.com）を設定すると、安全でないビデオをホワイトリストに登録できます。

* 後に追 `userPrivacyVideoWhitelist` 加しま `userPrivacyOptOut`す。 すべてのLivefyreプライバシーフラグを、1つのLivefyreオブジェクトの一部として一度に追加できます。
* `userPrivacyVideoWhitelist` ソーシャルメディアに埋め込まれていないコンテンツにのみ適用されます。

次の例では、パスが指定されたアプリに表示されるビデオはホワイトリス `sampledomain.com/cdn/videos` トに登録されています。

```
userPrivacyVideoWhitelist: ["sampledomain.com/cdn/videos"]
```
