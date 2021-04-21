---
description: facebookページからコンテンツを引き出すストリームルールを作成できます。
title: Facebookページルール
exl-id: 1dc728c6-81fa-4c6c-acba-d9a4aea71ed2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 1%

---

# Facebookページルール{#facebook-page-rules}

facebookページからコンテンツを引き出すストリームルールを作成できます。

facebookページルールを使用すると、Facebookページから公開投稿されたコンテンツをストリーミングできます。 コンテンツは、SocialSyncと同じ頻度でアプリまたはフォルダーに取り込まれます。SocialSyncは、Facebookページや投稿のトラフィックパターンに基づいて変化します。 facebookページ内のリンクもサポートされ、ストリームに表示されます。

facebookページのルールを作成して、Facebookページからコンテンツをアプリまたはフォルダーに取り込むには、次の条件でフィルターします。

* **[!UICONTROL Facebook Page]**

   * ページの&#x200B;**[!UICONTROL Name]**&#x200B;を入力します。 URLの末尾のテキストのみを入力します。 **例えば、コンテンツ** を追加するに `https://facebook.com/KellysSuperFunFanPage`は、フ ** ィールドに「 **[!UICONTROL Name]** KellysSuperFunFanPages」と入力します。

   * ページ投稿にユーザーコメントを含める場合は、**[!UICONTROL Include Facebook Comments for each post]**&#x200B;をオンに切り替えます。
   * 他のユーザーから投稿を除外する場合は、**[!UICONTROL Only Show Author Posts]**&#x200B;をオンにします。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。

>[!NOTE]
>
>LivefyreはFacebookから受け取ったコンテンツに制限されているので、Facebookページのすべての投稿がストリームに含まれることを保証できません。

>[!NOTE]
>
>特定のFacebookページに対してFacebookのSocialSyncとFacebookのページルールの両方が有効になっていて、Facebookのページルールに対してユーザーコメントが有効になっている場合、ストリームルールはSocialSyncを上書きします。 コンテンツは、Facebookページキュレーションルールに基づいてのみアプリにストリーミングされ、SocialSyncは使用されません。

facebookページキュレーションでサポートされるコンテンツのタイプは次のとおりです。

* ページ所有者または管理者

   * ステータス
   * 写真
   * リンクとしてのビデオ

* 標準Facebookユーザ

   * ステータス
   * 写真
   * リンクとしてのビデオ

* 第三者

   * ステータス
