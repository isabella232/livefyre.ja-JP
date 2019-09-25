---
description: ユーザーがメディアを投稿するソースと、メディア投稿を禁止するソースを定義します。
seo-description: ユーザーがメディアを投稿するソースと、メディア投稿を禁止するソースを定義します。
seo-title: 埋め込みメディアの管理
title: 埋め込みメディアの管理
uuid: d8621be1-dcfb-429f-954e-b21fdcf02715
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 埋め込みメディアの管理{#manage-embedded-media}

ユーザーがメディアを投稿するソースと、メディア投稿を禁止するソースを定義します。

デフォルトでは、すべてのメディア添付ファイルをコメントに埋め込むことができます。 サポートされるプロバイダーの詳細なリストについては、embed.ly/providersを参照してください。

Livefyreは、Embed.lyおよび標準のoEmbedプロトコルを使用して、メディアをAppストリームに埋め込み、ソースから提供されるすべてのメディアデータを渡します。

Embed.lyは、指定されたURLのメディアのタイトル、説明、サムネール、埋め込みコードなど、利用可能なすべての情報を渡します。 これらの項目の提供状況は、提供元によって異なります。 例：Facebookはビデオのサムネールを返さず、埋め込み可能なビデオのみを渡します。 「再生」をクリックすると、ビデオが開始されます（YouTubeの表示形式と同様）。 Twitterは静的な画像のみを渡し、ビデオは送信しません。 したがって、TwitterのネイティブビデオはLivefyreストリーム内から再生されない場合があります。

コメントストリームを埋め込むときに、コメントに特定の添付ファイルが埋め込まれない場合があります。 また、Studioを使用して、ネットワーク、サイト、および会話レベルのEmbed.ly展開をすべて非表示にし、メディアへのリンクのみを表示し、完全に埋め込まれたメディアは表示しないようにすることもできます。

この機能を使用するアプリ：

* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)

