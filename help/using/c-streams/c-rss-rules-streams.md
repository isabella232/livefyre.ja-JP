---
description: RSSフィードからコンテンツを取り込むストリームルールを作成できます。
seo-description: RSSフィードからコンテンツを取り込むストリームルールを作成できます。
seo-title: RSSルール
solution: Experience Manager
title: RSSルール
uuid: 3c9e2069-bb85-41dc-8b35-6237642a538a
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# RSSルール{#rss-rules}

RSSフィードからコンテンツを取り込むストリームルールを作成できます。

RSSストリームは5分ごとに更新され、フィード内の最初の50項目から、Livefyreにまだ存在しないコンテンツを探します。 Livefyreは、フィード内の最初の50項目を超える項目をすべて無視します。

RSSフィードからコンテンツを取り込むRSSルールを作成するには、次の条件でフィルタリングします。

* **[!UICONTROL URL]** のRSSフィードを参照してください。
* **[!UICONTROL Include recent items.]** これを次に設定すると、

   * **[!UICONTROL Enabled]**&#x200B;に設定されている場合、Livefyreは、投稿日に関係なく、フィード内の最初の50個のコンテンツ項目をストリームに追加します。
   * **[!UICONTROL Disabled]**&#x200B;に設定されている場合、Livefyreは、ストリームルール作成日以降と同じ発行日を持つストリームに、フィード内の最初の50個のコンテンツ項目を追加します。

* **[!UICONTROL Extract post information from item link (when disabled, post information is extracted from XML).]** 項目リンクまたはXMLから情報を取得します。

**RSSルール**

Livefyreは、以下のRSS仕様に基づいてRSSフィードを解析します。

* [RSS 2.0](https://en.wikipedia.org/wiki/RSS)
* [メディアRSS](https://en.wikipedia.org/wiki/Media_RSS)
* [アトムフィード](https://validator.w3.org/feed/docs/atom.html)

Livefyreは、これらの仕様に準拠しないフィードを読み取らず、そのコンテンツはストリームに取り込まれません。 WC3 Feed Validation Serviceを使用してRSSフィードの構文を確認し、有効であることを確認します。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。
