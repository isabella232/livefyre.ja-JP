---
description: ビデオドメインをホワイトリストに登録することができます。
seo-description: ビデオドメインをホワイトリストに登録することができます。
seo-title: UserPrivacyVideoWhiteList
solution: Experience Manager
title: UserPrivacyVideoWhiteList
uuid: adfad18- b73b-4ac4-97a0- d39f528b7606
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# UserPrivacyVideoWhiteList{#userprivacyvideowhitelist}

独自のカスタムビデオおよびプレーヤーをLivefyreビジュアライゼーションアプリに表示するビデオの一部として使用する場合は、ビデオドメインをホワイトリストに登録できます。ビデオドメインをホワイトリストに登録すると、カスタムビデオおよびプレーヤーのビデオマスクが削除されます。

>[!NOTE]
>
>特定のパスを使用して、安全なビデオのみをホワイトリストに登録します。パスを広いパス（sampledomain.comなど）にすると、安全でないビデオをホワイトリストに登録できます。

* `userPrivacyVideoWhitelist` 後 `userPrivacyOptOut`に追加Livefyreのプライバシーフラグはすべて1つのLivefyreオブジェクトの一部として追加できます。
* `userPrivacyVideoWhitelist` は、ソーシャルメディアから埋め込まれていないコンテンツにのみ適用されます。

次の例で `sampledomain.com/cdn/videos` は、パスを含むアプリに表示されるビデオはホワイトリスト登録されています。

```
userPrivacyVideoWhitelist: ["sampledomain.com/cdn/videos"]
```
