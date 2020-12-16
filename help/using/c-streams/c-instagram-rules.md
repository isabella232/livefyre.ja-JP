---
description: Instagramからコンテンツを取り込むストリームルールを作成できます。
seo-description: Instagramからコンテンツを取り込むストリームルールを作成できます。
seo-title: Instagramのルール
title: Instagramのルール
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---


# Instagramルール{#instagram-rules}

Instagramからコンテンツを取り込むストリームルールを作成できます。

>[!NOTE]
>
>Instagramストリームを作成する前に、**[!UICONTROL Network Settings]**&#x200B;の&#x200B;**[!UICONTROL Social Accounts]**&#x200B;セクションに少なくとも1つのInstagramビジネスアカウントを追加する必要があります。 Instagramアカウントの構成方法について詳しくは、[Instagramアカウントについて](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

@メンションまたはハッシュタグに基づいてInstagramルールを作成します。

>[!NOTE]
>
>すべてのInstagramルールには、少なくとも1つのハッシュタグが必要です。 キーワードとルールのユーザ名を追加すると、両方のエントリを含むコンテンツが返されます。

Instagramのルールを作成し、Instagramのフィードからコンテンツをアプリまたはフォルダーに取り込むには、次のフィルターを使用します。

* **[!UICONTROL Words]**

   * **[!UICONTROL hashtags]**&#x200B;を入力して、Instagramのストリームに含めるか、除外します。 **[!UICONTROL Contains]**&#x200B;フィールドと&#x200B;**[!UICONTROL Does not contain]**&#x200B;フィールドの両方に値を指定すると、最初のフィールドを含む画像が返され、2番目のフィールドは含まれません。

   * 例えば、**[!UICONTROL Contains]**&#x200B;キーワードGiants、Posey、**[!UICONTROL Does not contain]**&#x200B;キーワードDodgerを入力すると、GiantsまたはPoseyを含み、Dodgerという語を含まないすべての投稿が返されます。

      >[!NOTE]
      >
      >Instagramルールは、発言者のコメントに一覧表示されたハッシュタグを含む投稿を返しますが、この投稿はストリームに表示されない場合があります。

* **[!UICONTROL Mentions]**

   * **[!UICONTROL @mentions]**&#x200B;を入力してストリームに取り込むか、ストリームから除外します。

* **[!UICONTROL Authors]**

   >[!NOTE]
   >
   >Instagramストリームルールで作成者検索を使用するには、LivefyreでInstagramビジネスアカウントを設定する必要があります。 LivefyreでのInstagramビジネスアカウントの設定について詳しくは、[Instagramアカウントについて](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

   * **[!UICONTROL @usernames]**&#x200B;と入力してストリームに取り込みます。 **@username**&#x200B;に関連付けられているアカウントは、Instagramのビジネスアカウントである必要があります。

   * ストリームから除外する&#x200B;**@usernames**&#x200B;を入力します。

* **[!UICONTROL Additional Filters]**

   * ストリームに&#x200B;**[!UICONTROL All Content]**、**[!UICONTROL Videos Only]**、**[!UICONTROL Photos Only]**&#x200B;のいずれを含めるかを選択します。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。
