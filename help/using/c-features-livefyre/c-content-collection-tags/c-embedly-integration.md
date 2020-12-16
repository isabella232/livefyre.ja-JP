---
description: embed.ly を使用して、複数のメディア形式を直接アプリに表示します。
seo-description: embed.ly を使用して、複数のメディア形式を直接アプリに表示します。
seo-title: Embedly 統合
solution: Experience Manager
title: Embedly 統合
uuid: 1f27e32c-c2c3-4f7c-93de-c9c7bf783d6a
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 14%

---


# Embedly 統合 {#embedly-integration}

複数のメディア形式をアプリに直接表示するには、`embed.ly`を使用します。

Google Maps、YouTube、Flickr、Facebook、Instagram、Spotify、Tumblrなど、様々なソースから埋め込みメディアコンテンツをより有効にするため、LivefyreアプリはURL拡張のサードパーティプロバイダーとして明示的に使用します。 ユーザーまたはモデレーターが、サポートされているリンクを投稿に含めると、リンクに含まれるメディアは、コレクションへの投稿時に展開されます。

これにより、Livefyreアプリで、Embedlyがサポートする250種類以上の埋め込みメディアオプションにアクセスできます。

>[!NOTE]
>
>Livefyreは、Embedlyの完全なプロバイダーリストのサブセットのみを展開します。 埋め込み画像は、プロバイダーがTwitter、YouTube、Imgur、Vine、Wikipedia、SoundCloudの場合にのみ、HTTPSページで拡張されます。 リンクの拡張やソースに関するその他の質問は、テクニカルアカウントマネージャーにお問い合わせください。

このページには、一般的な埋め込みメディアの種類の例と、そのURLパターンの許容リストが示されています。 `Embed.ly` が新しいソースを継続的に追加しています。プロバイダの完全なリストについては、`https://embed.ly/embed/features/providers`を参照してください。

>[!NOTE]
>
>Embedly書式には、完全なパーマリンクが必要です。 短縮リンクは機能しません。

埋め込み可能なコンテンツは公開可能です。 公開以外のコンテンツを埋め込もうとすると、そのコンテンツへのリンクがブログ投稿に表示され、プレースホルダアイコンが付属します。 クリックすると、リンクにより、読者に対して、コンテンツがホストされているサービス（友達のみの写真のFacebookメッセージなど）のエラーメッセージが表示されます。 メディアが期待どおりに拡張されない場合は、担当のアカウントマネージャーにお問い合わせください。

## 埋め込みURLの例

| タイプ | ソーシャルプラットフォーム | URL |
|--- |--- |--- |
| マップ | Googleマップ | <ul><li>`https://maps.google.com/maps?*`</li><li>`https://maps.google.com/?*`</li><li>`https://maps.google.com/maps/ms?*`</li></ul><br>**注意**:URLはで始まる必要があ `http` り、始まらない  `https.` |
| ソーシャルネットワーキング | Google+ | <ul><li>`https://plus.google.com/*`</li><li>`https://www.google.com/profiles/*`</li><li> `https://plus.google.com/*`</li><li>`https://google.com/profiles/*`</li></ul> |
| ビデオ | YouTube | <ul><li>`https://*youtube.com/watch*`</li><li> `https://*.youtube.com/v/*`</li><li>`https://*youtube.com/watch*` </li><li>`https://*.youtube.com/v/*`</li><li>`https://youtu.be/*`</li><li>`https://*.youtube.com/user/*` </li><li>`https://*.youtube.com/*#*/*`</li><li>`https://m.youtube.com/watch*`</li><li>`https://m.youtube.com/index*`</li><li>`https://*.youtube.com/profile*`</li><li>`https://*.youtube.com/view_play_list*`</li><li>`https://*.youtube.com/playlist*`</li></ul> |
| 写真 | Flickr | `https://www.flickr.com/photos/*`<br>`https://flic.kr/*` |
|  | Instagram | `https://instagr.am/p/*`<br>`https://instagram.com/p/*` |
|  | TwitPic | <ul><li>`https://twitpic.com/*`</li><li>`https://www.twitpic.com/*`</li><li>`https://twitpic.com/photos/*`</li><li>`https://www.twitpic.com/photos/*`</li></ul> |
|  | Facebook | `https://www.facebook.com/photo.php*` |
|  | `Ow.ly` (Hootusite’s Content Uploading Service) | `https://ow.ly/i/*` |
| 投票 | GoPollGo | `https://gopollgo.com/*`<br>`https://www.gopollgo.com/*` |
|  | ドロプル | `https://d.pr/i/*` |
| Audio | SoundCloud | <ul><li>`https://soundcloud.com/*`</li><li>`https://soundcloud.com/*/*` </li><li>`https://soundcloud.com/*/sets/*` </li><li>`https://soundcloud.com/groups/*` </li><li>`https://snd.sc/*`</li></ul> |
|  | 指定 | `https://open.spotify.com/*` |
| ブログ | Tumblr | `https://tumblr.com/*`<br>`https://*.tumblr.com/post/*` |

この機能を使用するアプリ：

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [投票](/help/using/c-about-apps/c-polls-app/c-polls-app.md#c_polls_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenots](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)
* [アップロードボタン](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)

