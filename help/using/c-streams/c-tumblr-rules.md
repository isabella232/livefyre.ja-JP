---
description: Tumblrからコンテンツを取り込むストリームルールを作成できます。
seo-description: Tumblrからコンテンツを取り込むストリームルールを作成できます。
seo-title: Tumblrルール
solution: Experience Manager
title: Tumblrルール
uuid: fe9601ab- aa5e-48c6- a5bf-5543c179cb90
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Tumblrルール{#tumblr-rules}

Tumblrからコンテンツを取り込むストリームルールを作成できます。

Tumblrブログに基づいてTumblrルールを作成し、タグでフィルタリングします。Tumblrストリームは5分ごとに更新され、フィードの最初の20項目からLivefyreにはまだ存在しないコンテンツを探します。フィード内の最初の20項目をすべて無視します。

Tumblrルールを作成してTumblrからアプリまたはフォルダーにコンテンツを取り込むには、次のようにフィルタリングします。

* **[!UICONTROL Blog]**

   * Tumblrブログ **[!UICONTROL Blog Name]** を入力します。URL（*staff.tumblr.com*）またはブログ名（*スタッフ*）を入力します。

   * 特定のタグを含む投稿別に結果をフィルターする **[!UICONTROL Tag]** には、最大1つの結果を含めます。

* **[!UICONTROL Include recent items.]** これが次のように設定されている場合:

   * **[!UICONTROL Enabled]**の場合、発行日に関係なく、フィード内の最初の20コンテンツアイテムがストリームに追加されます。
   * **[!UICONTROL Disabled]**の場合、フィードの最初の20コンテンツアイテムがストリームルール作成日以降と同じパブリケーション日でストリームに追加されます。

すべてのストリームルール用の追加ストリームルールオプションについては、すべてのストリームルールの [ストリームルールオプションを参照](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)してください。
