---
description: Tumblrからコンテンツを引き出すストリームルールを作成できます。
seo-description: Tumblrからコンテンツを引き出すストリームルールを作成できます。
seo-title: Tumblrのルール
solution: Experience Manager
title: Tumblrのルール
uuid: fe9601ab-aa5e-48c6-a5bf-5543c179cb90
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '195'
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
