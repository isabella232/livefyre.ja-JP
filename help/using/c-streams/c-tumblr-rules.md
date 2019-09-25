---
description: Tumblrからコンテンツを取り込むストリームルールを作成できます。
seo-description: Tumblrからコンテンツを取り込むストリームルールを作成できます。
seo-title: Tumblrルール
solution: Experience Manager
title: Tumblrルール
uuid: fe9601ab-aa5e-48c6-a5bf-5543c179cb90
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Tumblrルール{#tumblr-rules}

Tumblrからコンテンツを取り込むストリームルールを作成できます。

Tumblrブログに基づいてTumblrルールを作成し、タグでフィルタリングします。 Tumblrストリームは5分ごとに更新され、フィード内の最初の20項目からLivefyreにまだ存在しないコンテンツを探します。 Livefyreは、フィード内の最初の20項目を超える項目をすべて無視します。

Tumblrルールを作成してTumblrからアプリまたはフォルダーにコンテンツを取り込むには、次のフィルターを使用します。

* **[!UICONTROL Blog]**

   * Tumblrブログ **[!UICONTROL Blog Name]** のを入力します。 URL(*staff.tumblr.com*)またはブログの名前(staff *)を入力し*&#x200B;ます。

   * 1つまでを含めて、特定の **[!UICONTROL Tag]** タグを含む投稿で結果をフィルターします。

* **[!UICONTROL Include recent items.]** これを次に設定すると、

   * **[!UICONTROL Enabled]**&#x200B;に設定されている場合、Livefyreは、投稿日に関係なく、フィードの最初の20個のコンテンツ項目をストリームに追加します。
   * **[!UICONTROL Disabled]**&#x200B;に設定されている場合、Livefyreは、ストリームルール作成日以降と同じ発行日を持つストリームに、フィード内の最初の20個のコンテンツ項目を追加します。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。
