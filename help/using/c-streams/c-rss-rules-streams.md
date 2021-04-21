---
description: RSSフィードからコンテンツを取り込むストリームルールを作成できます。
title: RSSルール
exl-id: bfb3bbad-ab26-451e-b540-d6c41f54dc31
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# RSSルール{#rss-rules}

RSSフィードからコンテンツを取り込むストリームルールを作成できます。

RSSストリームは5分ごとに更新され、フィード内の最初の50項目から、Livefyreにまだ存在しないコンテンツを探します。 Livefyreは、フィード内の最初の50項目を超える項目をすべて無視します。

RSSフィードからコンテンツを取り込むRSSルールを作成するには、次のフィルタを使用します。

* **[!UICONTROL URL]** のRSSフィードの
* **[!UICONTROL Include recent items.]** 次に設定する場合：

   * **[!UICONTROL Enabled]**&#x200B;投稿日に関係なく、Livefyreは、フィード内の最初の50個のコンテンツ項目をストリームに追加します。
   * **[!UICONTROL Disabled]** Livefyreは、フィード内の最初の50個のコンテンツ項目を、ストリームルール作成日以降と同じ発行日付のストリームに追加します。

* **[!UICONTROL Extract post information from item link (when disabled, post information is extracted from XML).]** 項目リンクまたはXMLから情報を取得します。

**RSSルール**

Livefyreは、以下のRSS仕様に基づいてRSSフィードを解析します。

* [RSS 2.0](https://en.wikipedia.org/wiki/RSS)
* [メディアRSS](https://en.wikipedia.org/wiki/Media_RSS)
* [原子フィード](https://validator.w3.org/feed/docs/atom.html)

これらの仕様に従っていないフィードは読み取られず、そのコンテンツはストリームに取り込まれません。 WC3 Feed Validation Serviceを使用してRSSフィードの構文を確認し、有効であることを確認します。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。
