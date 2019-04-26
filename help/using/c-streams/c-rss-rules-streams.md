---
description: RSSフィードからコンテンツを取り込むストリームルールを作成できます。
seo-description: RSSフィードからコンテンツを取り込むストリームルールを作成できます。
seo-title: RSSルール
solution: Experience Manager
title: RSSルール
uuid: 3c9e2069- bb85-41dc-8b35-6237642a538a
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# RSSルール{#rss-rules}

RSSフィードからコンテンツを取り込むストリームルールを作成できます。

RSSストリームは5分ごとに更新され、フィードの最初の50項目からLivefyreには存在しないコンテンツを探します。フィード内の最初の50項目を超えるすべての項目は無視されます。

RSSルールを作成して、RSSフィードからアプリまたはフォルダーにコンテンツを取り込むには、次のようにフィルタリングします。

* **[!UICONTROL URL]** 」を参照してください。
* **[!UICONTROL Include recent items.]** これが次のように設定されている場合:

   * **[!UICONTROL Enabled]**の場合、発行日に関係なく、フィード内の最初の50コンテンツアイテムがストリームに追加されます。
   * **[!UICONTROL Disabled]**の場合、フィード内の最初の50コンテンツアイテムがストリームルール作成日以降と同じパブリケーション日でストリームに追加されます。

* **[!UICONTROL Extract post information from item link (when disabled, post information is extracted from XML).]** アイテムリンクまたはXMLからの情報の取り込み。

**RSSルール**

Livefyreは、以下のRSS仕様に基づいてRSSフィードを解析します。

* [RSS2.0](https://en.wikipedia.org/wiki/RSS)
* [メディアRSS](https://en.wikipedia.org/wiki/Media_RSS)
* [Atomフィード](https://validator.w3.org/feed/docs/atom.html)

Livefyreはこれらの仕様に準拠していないフィードを読み取りません。そのコンテンツはストリームに取り込まれません。"WC3Feed Validation Service"を使用して、RSSフィードの構文をチェックし、有効であることを確認します。

すべてのストリームルール用の追加ストリームルールオプションについては、すべてのストリームルールの [ストリームルールオプションを参照](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)してください。
