---
description: ユーザーがメディアを投稿するソースと、メディア投稿を禁止するソースを定義します。
title: 埋め込みメディアの管理
exl-id: f0cc257b-cc82-47bc-9d42-6aef3e0fe8a7
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# 埋め込みメディアの管理{#manage-embedded-media}

ユーザーがメディアを投稿するソースと、メディア投稿を禁止するソースを定義します。

デフォルトでは、すべてのメディア添付ファイルをコメントに埋め込むことができます。 サポートされるプロバイダーに関する包括的なリストについては、embed.ly/providersを参照してください。

Livefyreは、Embed.lyと標準のoEmbedプロトコルを使用して、メディアをアプリストリームに埋め込み、ソースから提供されるすべてのメディアデータを渡します。

Embed.lyは、提供されたURLのタイトル、説明、サムネール、埋め込みコードを含む、利用可能なすべての情報を渡します。 これらの項目が利用できるかどうかは、プロバイダーによって異なります。 次に例を示します。Facebookはビデオのサムネールを返さず、埋め込み可能なビデオのみを渡します。 「再生」をクリックすると、ビデオが開始されます(YouTubeの表示形式と同様)。 Twitterは静的な画像のみを渡し、ビデオは送信しません。 そのため、TwitterのネイティブビデオはLivefyreストリーム内から再生できない場合があります。

コメントストリームを埋め込む際に、コメントに添付ファイルが埋め込まれないようにすることができます。 また、Studioを使用して、ネットワーク、サイト、および会話レベルのEmbed.ly拡張をすべて非表示にし、メディアへのリンクのみを表示し、完全に埋め込まれたメディアは表示しないようにすることもできます。

この機能を使用するアプリ：

* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
