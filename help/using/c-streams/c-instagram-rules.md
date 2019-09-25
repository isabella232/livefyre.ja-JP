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
>Instagramストリームを作成する前に、少なくとも1つのInstagramビジネスアカウントをのセクションに追加する必要 **[!UICONTROL Social Accounts]** がありま **[!UICONTROL Network Settings]**&#x200B;す。 Instagramアカウントの設定方法について詳しくは、Instagramアカウントにつ [いてを参照してください](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)。

@メンションまたはハッシュタグに基づいてInstagramルールを作成します。

>[!NOTE]
>
>すべてのInstagramルールには、少なくとも1つのハッシュタグが必要です。 キーワードとルールのユーザ名を追加すると、両方のエントリを含むコンテンツが返されます。

Instagramのフィードからコンテンツを取り込むためのInstagramルールを作成するには、次のフィルターを使用します。

* **[!UICONTROL Words]**

   * Instagramスト **[!UICONTROL hashtags]** リームに含めるか、除外するかを入力します。 との両方のフィールドに値を指 **[!UICONTROL Contains]** 定すると、 **[!UICONTROL Does not contain]** 最初の値を含み、2番目の値を含まない画像が返されます。

   * 例えば、キーワードGiants、Posey **[!UICONTROL Contains]****[!UICONTROL Does not contain]** およびキーワードDodgerを入力すると、GiantsまたはPoseyという語を含み、Dodgerという語を含まないすべての投稿が返されます。

      >[!NOTE]
      >
      >Instagramルールは、発言者のコメントにリストされたハッシュタグを含む投稿を返しますが、この投稿はストリームに表示されない場合があります。

* **[!UICONTROL Mentions]**

   * ストリー **[!UICONTROL @mentions]** ムに取り込むか、ストリームから除外するかを入力します。

* **[!UICONTROL Authors]**

   >[!NOTE]
   >
   >Instagramストリームルールで作成者検索を使用するには、LivefyreでInstagramビジネスアカウントを設定する必要があります。 LivefyreでのInstagramビジネスアカウントの設定について詳しくは、Instagramアカウントにつ [いてを参照してください](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)。

   * ストリー **[!UICONTROL @usernames]** ムに取り込むためのEnterを入力します。 @usernameに関連付けられているアカウ **ントは** 、Instagramのビジネスアカウントである必要があります。

   * ストリームか **ら除外する** @usernamesを入力します。

* **[!UICONTROL Additional Filters]**

   * ストリームに含めるか、含めるか、含め **[!UICONTROL All Content]**&#x200B;るか、 **[!UICONTROL Videos Only]**&#x200B;またはストリ **[!UICONTROL Photos Only]** ームに含めるかを選択します。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。
