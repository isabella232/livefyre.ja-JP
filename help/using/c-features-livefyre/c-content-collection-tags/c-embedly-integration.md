---
description: embed.ly を使用して、複数のメディア形式を直接アプリに表示します。
seo-description: embed.ly を使用して、複数のメディア形式を直接アプリに表示します。
seo-title: Embedly 統合
solution: Experience Manager
title: Embedly 統合
uuid: 1f27e32c- c2c3-4f7c-93de- c9c7bf783d6a
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# Embedly 統合{#embedly-integration}

アプリに直接複数のメディア形式を表示する場合に使用 `embed.ly` します。

Googleマップ、YouTube、Flickr、Facebook、Instagram、SpotifyおよびTumblrなどの様々なソースからの埋め込みメディアコンテンツを有効にするために、Livefyreアプリでは、URL拡張用のサードパーティプロバイダーとしてEmbedlyを使用します。ユーザーまたはモデレーターに投稿にサポートされているリンクが含まれている場合、リンクに含まれるメディアは、コレクションに投稿されると展開されます。

これにより、埋め込みがサポートされる250種類以上の埋め込みメディアオプションにアクセスできるLivefyreアプリが提供されます。

>[!NOTE]
>
>Livefyreは、Embedlyのフルプロバイダーリストのサブセットのみを展開します。埋め込み画像は、プロバイダーがTwitter、YouTube、Imgur、Stu、WikipediaまたはSoundCloudの場合のみ、HTTPSページで展開されます。リンクの拡張またはソースについて詳しくは、テクニカルアカウントマネージャーにお問い合わせください。

このページには、一般的な埋め込みメディアの種類の例と、その使用可能なURLパターンの例が記載されています。`Embed.ly` では、新しいソースを継続的に追加しています。全プロバイダーの一覧については、先 `https://embed.ly/embed/features/providers`に進んでください。

>[!NOTE]
>
>埋め込み形式には完全な固定リンクが必要です。短縮リンクは機能しません。

埋め込み可能なコンテンツのみが埋め込み可能です。公開されていないコンテンツを埋め込むと、コンテンツへのリンクがブログ投稿に表示され、プレースホルダーアイコンが表示されます。リンクをクリックすると、友達のみの写真のFacebookメッセージなど、コンテンツがホストされているサービスからのエラーメッセージが表示されます。メディアが期待どおりに拡張されていないことがわかった場合は、担当のアカウントマネージャーにお問い合わせください。

## 埋め込みURLのサンプル

| タイプ | プロバイダ | URL |
|--- |--- |--- |
| マップ | Googleマップ | <ul><li>`https://maps.google.com/maps?*`</li><li>`https://maps.google.com/?*`</li><li>`https://maps.google.com/maps/ms?*`</li></ul><br>**注意**:URLは次から始まる必要が `http` あります `https.` |
| ソーシャルネットワーキング | Google Plus | <ul><li>`https://plus.google.com/*`</li><li>`https://www.google.com/profiles/*`</li><li> `https://plus.google.com/*`</li><li>`https://google.com/profiles/*`</li></ul> |
| Video | YouTube | <ul><li>`https://*youtube.com/watch*`</li><li> `https://*.youtube.com/v/*`</li><li>`https://*youtube.com/watch*` </li><li>`https://*.youtube.com/v/*`</li><li>`https://youtu.be/*`</li><li>`https://*.youtube.com/user/*` </li><li>`https://*.youtube.com/*#*/*`</li><li>`https://m.youtube.com/watch*`</li><li>`https://m.youtube.com/index*`</li><li>`https://*.youtube.com/profile*`</li><li>`https://*.youtube.com/view_play_list*`</li><li>`https://*.youtube.com/playlist*`</li></ul> |
| 写真 | Flickr | `https://www.flickr.com/photos/*`<br>`https://flic.kr/*` |
|  | Instagram | `https://instagr.am/p/*`<br>`https://instagram.com/p/*` |
|  | Twitpic | <ul><li>`https://twitpic.com/*`</li><li>`https://www.twitpic.com/*`</li><li>`https://twitpic.com/photos/*`</li><li>`https://www.twitpic.com/photos/*`</li></ul> |
|  | Facebook | `https://www.facebook.com/photo.php*` |
|  | `Ow.ly` （Hotsuiteのコンテンツアップロードサービス） | `https://ow.ly/i/*` |
| ポール | gopCollectionGo | `https://gopollgo.com/*`<br>`https://www.gopollgo.com/*` |
|  | Drodr | `https://d.pr/i/*` |
| オーディオ | SoundCloud | <ul><li>`https://soundcloud.com/*`</li><li>`https://soundcloud.com/*/*` </li><li>`https://soundcloud.com/*/sets/*` </li><li>`https://soundcloud.com/groups/*` </li><li>`https://snd.sc/*`</li></ul> |
|  | スワイプ | `https://open.spotify.com/*` |
| ブログ | Tumblr | `https://tumblr.com/*`<br>`https://*.tumblr.com/post/*` |

この機能を使用するアプリ:

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [ポール](/help/using/c-about-apps/c-polls-app/c-polls-app.md#c_polls_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Ssiindes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md#c_trending_app)
* [アップロードボタン](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)

