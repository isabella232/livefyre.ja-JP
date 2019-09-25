---
description: これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのすべてのストリームルールに適用されます。
seo-description: これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのすべてのストリームルールに適用されます。
seo-title: すべてのストリームルールのストリームルールオプション
solution: Experience Manager
title: すべてのストリームルールのストリームルールオプション
uuid: 4072ee83-31e7-4de6-918c-134b8b8032e1
translation-type: tm+mt
source-git-commit: 8bdb537b38d78dba033d6671b710c2a61934d6b2

---


# すべてのストリームルールのストリームルールオプション{#stream-rule-options-for-all-stream-rules}

これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのすべてのストリームルールに適用されます。

テキストフィールドとキーワードフィールドの検索機能：

* キーワードを入力すると、Livefyreは個々の単語に対してブール演算子 **OR** (OR)を自動的に使用します。 例えば、「 *cakes* 」または「recipe」という単語を含む投稿を検索するには、「 *cake*」と入力し、「recipe *」と「recipe」と入力し*****[!UICONTROL keyword]** ます。

* 完全一致のフレーズテキストを引用符で囲むと、完全一致のフレーズを検索できます。 例えば、正確なフレーズ「cake recipe *」を検索するに*&#x200B;は、フィールドに「cake recipe *」と入力し***[!UICONTROL keyword]** ます。

* 1つのストリームルールで、ブール検索と完全一致フレーズ検索を組み合わせることができます。 例えば、各フレーズを一度に1 *つずつ入力して、* cake *、recipe*、 *およびcake recipe* を検索できます。

**[!UICONTROL Additional Filters]**:

* **[!UICONTROL Media]**. 次のいずれかを選択します。

   * **[!UICONTROL All Content.]** 任意のコンテンツを許可します。
   * **[!UICONTROL Media Required.]** 画像とビデオを含むコンテンツのみを許可する。 (InstagramおよびFacebookコンテンツの場合は、またはのみを **[!UICONTROL Photos]** 指定で **[!UICONTROL Videos]** きます)。

* **[!UICONTROL Language]**. 検索する言語を選択します。 デフォルトの言語は英語です。
* **[!UICONTROL Smart Tags]**. コンテンツの識別に使用するタグを選択します。 Livefyreは、コンピューターの視覚技術を使用して、特定のスマートタグを使用して写真やビデオを識別し、より正確に検索できるようにします。 修飾子を使用し **[!UICONTROL ANY]** て任意のタグを使用してコンテンツをストリームにフィルターしたり、修飾子を使用し **[!UICONTROL ALL]** てすべてのタグを使用するストリームにコンテンツをフィルターしたりします。 このフィール **[!UICONTROL Image contains none of these smart tags]** ドを使用して、ストリームに含めないコンテンツを含む写真のタグを入力します。 このオプションは、テキストコンテンツに対しては機能しません。

* **[!UICONTROL Products]**. ストリームルールと製品カタログの製品を一致させる製品タグを追加します。
* **[!UICONTROL Premoderate]**. 次のいずれかを選択します。

   * **[!UICONTROL On]**. 受信するすべてのルールコンテンツを事前モデレートします。 モデレート済みコンテンツは、ModQのStreamsセクションから表示できます。 **[!UICONTROL On]** は、アプリ設定の設定を上書きします。
   * **[!UICONTROL Off]**. 受信したルールのコンテンツを事前にモデレートしないでください。 **[!UICONTROL Off]** は、アプリ設定の設定を上書きします。
   * **[!UICONTROL Inherited (Off)]**. サイトのプレモデレート設定を使用しま **[!UICONTROL Site Settings]**&#x200B;す()。

* **[!UICONTROL SAFE Rules]**. 次のいずれかを選択します。
   * **[!UICONTROL Apply SAFE Rules]**. すべてのSAFEルールをこのストリームに適用します。
   * **[!UICONTROL Apply SAFE Rules for:]** このストリームルールにセーフルールを適用するオプションを1つ以上選択します。
   * **[!UICONTROL Disable SAFE Rules]**. このストリームにSAFEルールを適用しないでください。

ソーシャルネットワークまたはコンテンツタイプに固有のストリームルールオプションについては、各ソーシャルネットワークまたはコンテンツタイプに関する次のドキュメントを参照してください。

* [Facebook ページ](../c-streams/c-facebook-page-rules.md#c_facebook_page_rules)
* [Email](../c-streams/c-email-rules.md#c_email_rules)
* [Instagram](../c-streams/c-instagram-rules.md#c_instagram_rules)
* [Tumblr](../c-streams/c-tumblr-rules.md#c_tumblr_rules)
* [Twitter](../c-streams/c-twitter-rules.md#c_twitter_rules)
* [YouTube](../c-streams/c-youtube-rules/c-youtube-rules.md#c_youtube_rules)
* [RSS](../c-streams/c-rss-rules-streams.md#c_rss_rules_streams)
