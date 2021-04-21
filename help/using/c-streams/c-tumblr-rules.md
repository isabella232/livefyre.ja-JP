---
description: Tumblrからコンテンツを引き出すストリームルールを作成できます。
title: Tumblrのルール
exl-id: 5d49b266-6d1f-4ec2-8891-5e98fcab14a2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 0%

---

# Tumblrルール{#tumblr-rules}

Tumblrからコンテンツを引き出すストリームルールを作成できます。

Tumblrのブログに基づいてTumblrルールを作成し、タグでフィルタリングします。 Tumblrストリームが5分ごとに更新され、フィードの最初の20項目から、Livefyreに存在しないコンテンツを探します。 Livefyreは、フィードの最初の20項目を超える項目をすべて無視します。

Tumblrのルールを作成してTumblrからコンテンツをアプリまたはフォルダーに取り込むには、次のフィルターを使用します。

* **[!UICONTROL Blog]**

   * Tumblrブログの&#x200B;**[!UICONTROL Blog Name]**&#x200B;を入力します。 URL(*staff.tumblr.com*)またはブログの名前(*staff*)を入力します。

   * 特定のタグを含む投稿で結果をフィルターするには、最大1つの&#x200B;**[!UICONTROL Tag]**&#x200B;を含めます。

* **[!UICONTROL Include recent items.]** 次に設定する場合：

   * **[!UICONTROL Enabled]**&#x200B;投稿日に関係なく、Livefyreは、フィードの最初の20個のコンテンツ項目をストリームに追加します。
   * **[!UICONTROL Disabled]** Livefyreは、フィード内の最初の20個のコンテンツ項目を、ストリームルール作成日以降と同じ発行日付のストリームに追加します。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。
