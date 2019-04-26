---
description: Instagramからコンテンツを取り込むストリームルールを作成できます。
seo-description: Instagramからコンテンツを取り込むストリームルールを作成できます。
seo-title: Instagramルール
title: Instagramルール
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# Instagramルール{#instagram-rules}

Instagramからコンテンツを取り込むストリームルールを作成できます。

>[!NOTE]
>
>Instagramストリームを作成する前に **[!UICONTROL Social Accounts]** 、そのセクションに少なくとも1つのInstagramビジネスアカウントを追加する必要 **[!UICONTROL Network Settings]**があります。Instagramアカウントの設定方法について詳しくは、Instagramアカウント [について](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

@メンションまたはハッシュタグに基づいてInstagramルールを作成します。

>[!NOTE]
>
>すべてのInstagramルールには、少なくとも1つのハッシュタグが必要です。ルールのキーワードとユーザー名を追加すると、両方のエントリを含むコンテンツが返されます。

Instagramのルールを作成してInstagramフィードからアプリまたはフォルダーにコンテンツを取り込むには、次のようにフィルタリングします。

* **[!UICONTROL Words]**

   * Instagramストリームに含める **[!UICONTROL hashtags]** か、除外するように入力します。両方 **[!UICONTROL Contains]** の **[!UICONTROL Does not contain]** フィールドとフィールドの値を指定すると、最初の画像を含む画像が返され、2つ目のフィールドは含まれません。

   * 例えば、キー **[!UICONTROL Contains]** ワード"Giants"、"Poey"、 **[!UICONTROL Does not contain]** キーワード"Domedger"を入力すると、"Giants"または"Poey"という単語を含むすべての投稿が返され、"Didger"という単語は含まれません。

      >[!NOTE]
      >
      >Instagramルールは、発言者のコメントに一覧表示されたハッシュタグを含む投稿を返します。この投稿はストリームに表示されません。

* **[!UICONTROL Mentions]**

   * ストリーム **[!UICONTROL @mentions]** に取り込むか、ストリームから除外します。

* **[!UICONTROL Authors]**

   >[!NOTE]
   >
   >Instagramストリームルールで作成者検索を使用するには、LivefyreでInstagramのビジネスアカウントが設定されている必要があります。LivefyreでのInstagramビジネスアカウントの設定について詳しくは、Instagramアカウント [について](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

   * を入力 **[!UICONTROL @usernames]** してストリームに取り込みます。**@ username** に関連付けられているアカウントは、Instagramのビジネスアカウントである必要があります。

   * ストリームから除外する **@ username** を入力します。

* **[!UICONTROL Additional Filters]**

   * ストリームを含める **[!UICONTROL All Content]**か、ストリーム **[!UICONTROL Videos Only]****[!UICONTROL Photos Only]** に含めるかを選択します。

すべてのストリームルール用の追加ストリームルールオプションについては、すべてのストリームルールの [ストリームルールオプションを参照](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)してください。
