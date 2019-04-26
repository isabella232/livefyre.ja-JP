---
description: メディアの投稿元となるソースと、メディア投稿の禁止元のソースを定義します。
seo-description: メディアの投稿元となるソースと、メディア投稿の禁止元のソースを定義します。
seo-title: 埋め込みメディアの管理
title: 埋め込みメディアの管理
uuid: d8621be1- dcfb-429f-954e- b21fdcf02715
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 埋め込みメディアの管理{#manage-embedded-media}

メディアの投稿元となるソースと、メディア投稿の禁止元のソースを定義します。

デフォルトでは、すべてのメディア添付ファイルをコメントに埋め込むことができます。サポートされるプロバイダーの一覧については、embed.ly/providersを参照してください。

Livefyreは、Embed. lyおよび標準のoEmbedプロトコルを使用して、メディアストリームにメディアを埋め込み、ソースによって提供されるすべてのメディアデータを渡します。

Embed. lyは、提供されたURLのメディアのタイトル、説明、サムネール、埋め込みコードなど、利用可能なすべての情報をパススルーします。これらの項目の可用性は、プロバイダーによって異なります。次に例を示します。Facebookはビデオのサムネールを返しません。埋め込まれたビデオのみを渡します。「再生」をクリックすると、ビデオが開始されます（YouTubeの表示形式と同様）。Twitterでは静的な画像のみが渡され、ビデオは送信されません。そのため、TwitterのネイティブビデオはLivefyreストリーム内から再生できないことがあります。

コメントストリームを埋め込むときに特定の添付ファイルがコメントに埋め込まれないことがあります。また、Studioを使用してネットワーク、サイトおよび会話レベルのすべてのEmbed. ly拡張を非表示にすることもできます。メディアに対するリンクは完全に埋め込まれていません。

この機能を使用するアプリ:

* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)

