---
description: Facebookページからコンテンツを引き出すストリームルールを作成できます。
seo-description: Facebookページからコンテンツを引き出すストリームルールを作成できます。
seo-title: Facebookページのルール
solution: Experience Manager
title: Facebookページのルール
uuid: 2be63476-1a92-409d-a22f-e1ec66b6dcc8
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%

---


# Facebookページルール{#facebook-page-rules}

Facebookページからコンテンツを引き出すストリームルールを作成できます。

Facebookページルールを使用して、Facebookページから公開投稿されたコンテンツをストリーミングできます。 コンテンツは、SocialSyncと同じ頻度でアプリまたはフォルダーに取り込まれます。SocialSyncは、Facebookページや投稿のトラフィックパターンに基づいて変化します。 Facebookページ内のリンクもサポートされ、ストリームに表示されます。

Facebookページのルールを作成してFacebookページからコンテンツを取り込み、アプリまたはフォルダーに送るには、次の条件を満たすフィルターを使用します。

* **[!UICONTROL Facebook Page]**

   * ページの&#x200B;**[!UICONTROL Name]**&#x200B;を入力します。 URLの末尾のテキストのみを入力します。 **例えば、コンテンツ** を追加するに `https://facebook.com/KellysSuperFunFanPage`は、フ ** ィールドに「 **[!UICONTROL Name]** KellysSuperFunFanPages」と入力します。

   * ページ投稿にユーザーコメントを含める場合は、**[!UICONTROL Include Facebook Comments for each post]**&#x200B;をオンに切り替えます。
   * 他のユーザーから投稿を除外する場合は、**[!UICONTROL Only Show Author Posts]**&#x200B;をオンにします。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。

>[!NOTE]
>
>LivefyreはFacebookから受け取ったコンテンツに制限されているので、Facebookページ上のすべての投稿がストリームに含まれることを保証できません。

>[!NOTE]
>
>Facebook SocialSyncとFacebookページルールの両方が特定のFacebookページに対して有効になっており、Facebookページルールに対してユーザーコメントが有効になっている場合、ストリームルールはSocialSyncを上書きします。 コンテンツは、Facebookページキュレーションルールに基づいてのみアプリにストリーミングされ、SocialSyncは使用されません。

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

