---
description: Facebookページからコンテンツを取り込むストリームルールを作成できます。
seo-description: Facebookページからコンテンツを取り込むストリームルールを作成できます。
seo-title: Facebookページルール
solution: Experience Manager
title: Facebookページルール
uuid: 2be63476-1a92-409d-a22f-e1ec66b6dcc8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Facebookページルール{#facebook-page-rules}

Facebookページからコンテンツを取り込むストリームルールを作成できます。

Facebookページルールを使用して、Facebookページから公開投稿されたコンテンツをストリーミング配信できます。 コンテンツは、SocialSyncと同じ頻度でアプリまたはフォルダーに取り込まれます。SocialSyncは、Facebookページや投稿のトラフィックパターンに基づいて変化します。 Facebookページ内のリンクもサポートされ、ストリームに表示されます。

Facebookページのルールを作成してFacebookページからコンテンツをアプリまたはフォルダーに取り込むには、次のようにフィルターします。

* **[!UICONTROL Facebook Page]**

   * ページの **[!UICONTROL Name]** を入力します。 URLの末尾のテキストのみを入力します。 **** 例：コンテンツを追加するに `https://facebook.com/KellysSuperFunFanPage`は、フィ *ールドに* KellysSuperFunFanPageと入 **[!UICONTROL Name]** 力します。

   * ページ **[!UICONTROL Include Facebook Comments for each post]** 投稿にユーザーコメントを含める場合は、オンにします。
   * 他のユ **[!UICONTROL Only Show Author Posts]** ーザーから投稿を除外する場合は、オンにします。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。

>[!NOTE]
>
>LivefyreはFacebookから受け取ったコンテンツに制限されているので、Facebookページ上のすべての投稿がストリームに含まれることを保証できません。

>[!NOTE]
>
>特定のFacebookページに対してFacebook SocialSyncとFacebookページルールの両方が有効になっていて、Facebookページルールに対してユーザーコメントが有効になっている場合、ストリームルールはSocialSyncを上書きします。 コンテンツは、Facebookページキュレーションルールに基づいてのみアプリにストリーミングされ、SocialSyncは使用されません。

Facebookページキュレーションでサポートされるコンテンツのタイプは次のとおりです。

* ページ所有者または管理者

   * ステータス
   * 写真
   * リンクとしてのビデオ

* 標準のFacebookユーザー

   * ステータス
   * 写真
   * リンクとしてのビデオ

* 第三者

   * ステータス

