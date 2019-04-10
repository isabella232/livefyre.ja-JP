---
description: Facebookページからコンテンツを取り込むストリームルールを作成できます。
seo-description: Facebookページからコンテンツを取り込むストリームルールを作成できます。
seo-title: Facebookページルール
solution: Experience Manager
title: Facebookページルール
uuid: 2be63476-1a92-409d- a22f- e1ec66b6dcc8
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Facebookページルール{#facebook-page-rules}

Facebookページからコンテンツを取り込むストリームルールを作成できます。

Facebookページルールを使用して、Facebookページから投稿されたコンテンツをストリーム再生できます。コンテンツは、SocialSyncと同じ頻度でアプリまたはフォルダーに取り込まれ、Facebookページおよび投稿のトラフィックパターンに基づいて変化します。Facebookページ内のリンクもサポートされ、ストリームに表示されます。

Facebookページルールを作成してFacebookページからアプリまたはフォルダーにコンテンツを取り込むには、次のようにフィルタリングします。

* **[!UICONTROL Facebook Page]**

   * ページ **[!UICONTROL Name]** を入力します。URLの末尾のテキストのみを入力します。**次に例を示します。** コンテンツを追加する `https://facebook.com/KellysSuperFunFanPage`には、フィールドに *"KellisSuperFandPagePage* 」と入力 **[!UICONTROL Name]** します。

   * ページ投稿にユーザーコメントを含める場合にオンに **[!UICONTROL Include Facebook Comments for each post]** します。
   * 他 **[!UICONTROL Only Show Author Posts]** のユーザーからの投稿を除外する場合にオンにします。

すべてのストリームルール用の追加ストリームルールオプションについては、すべてのストリームルールの [ストリームルールオプションを参照](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)してください。

>[!NOTE]
>
>LivefyreはFacebookから受け取ったコンテンツに制限されるので、Facebookページ上のすべての投稿がストリームに含まれることを保証できません。

>[!NOTE]
>
>Facebook SocialSyncとFacebookページルールが特定のFacebookページで有効になっており、ユーザーコメントがFacebookページルールで有効になっている場合、ストリームルールはSocialSyncを上書きします。コンテンツは、SocialSyncを使用しないでFacebookページのキュレーションルールのみに基づいてアプリにストリーミングされます。

Facebookページキュレーションでサポートされるコンテンツのタイプには以下が含まれます。

* ページ所有者または管理者

   * ステータス
   * 写真
   * リンクとしてのビデオ

* Standard Facebookユーザー

   * ステータス
   * 写真
   * リンクとしてのビデオ

* 第三者

   * ステータス

