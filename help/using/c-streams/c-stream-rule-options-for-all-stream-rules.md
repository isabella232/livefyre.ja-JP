---
description: これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのストリームルールに適用されます。
seo-description: これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのストリームルールに適用されます。
seo-title: すべてのストリームルールのストリームルールオプション
solution: Experience Manager
title: すべてのストリームルールのストリームルールオプション
uuid: 4072ee83-31e7-4de6-918c-134b8b8032e1
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# すべてのストリームルールのストリームルールオプション{#stream-rule-options-for-all-stream-rules}

これらのオプションは、すべてのソーシャルネットワークまたは投稿方法からのストリームルールに適用されます。

テキストおよびキーワードフィールドの検索機能:

* キーワードを入力すると、Livefyreは自動的にBoolean演算子 **OR** を使用します。*例えば、ケーキ* または *レシピ*のある投稿を検索するには、ケーキを入力 **して、フィールドに *レシピ* を入力 **[!UICONTROL keyword]** します。

* 正確なフレーズテキストを引用符で囲むことで、正確なフレーズを検索できます。For example, to search for the exact phrase *cake recipe*, enter *"cake recipe"* in the **[!UICONTROL keyword]** field.

* ブール値と完全一致フレーズの検索は、1つのストリームルール内で組み合わせることができます。例えば、各フレーズを一度に入力して *、ケーキ*、 *レシピ*、 *「ケーキレシピ」* を検索できます。

**[!UICONTROL Additional Filters]**:

* **[!UICONTROL Media]**. 次のいずれかを選択します。

   * **[!UICONTROL All Content.]** コンテンツを許可します。
   * **[!UICONTROL Media Required.]** 画像とビデオのあるコンテンツのみを許可します。（InstagramおよびFacebookのコンテンツの場合は、指定 **[!UICONTROL Photos]** できます **[!UICONTROL Videos]** 。

* **[!UICONTROL Language]**. 検索する言語を選択します。デフォルト言語は英語です。
* **[!UICONTROL Smart Tags]**. コンテンツの識別に使用するタグを選択します。Livefyreは、コンピューターの視覚的なテクノロジーを使用して、特定のスマートタグを使用して写真やビデオを識別し、この検索をより正確にします。**[!UICONTROL ANY]** 修飾子を使用して、任意のタグまたは **[!UICONTROL ALL]** 修飾子を使用してコンテンツをストリームにフィルターし、すべてのタグを使用するストリームにコンテンツをフィルターします。フィールドを **[!UICONTROL Image contains none of these smart tags]** 使用して、ストリームに含めないコンテンツを含む写真のタグを入力します。このオプションはテキストコンテンツでは機能しません。

* **[!UICONTROL Products]**. 製品タグを追加して、製品カタログの製品と共に、ストリームルールに一致させます。
* **[!UICONTROL Premoderate]**. 次のいずれかを選択します。

   * **[!UICONTROL On]**. すべての受信ルールコンテンツのモデレートModeredコンテンツは、Modqの"Streams"セクションから表示できます。**[!UICONTROL On]** は、アプリ設定の設定よりも優先されます。
   * **[!UICONTROL Off]**. 受信ルールコンテンツを事前モデレートしないでください。**[!UICONTROL Off]** は、アプリ設定の設定よりも優先されます。
   * **[!UICONTROL Inherited (Off)]**. サイトの事前モデレート設定を使用します（下の） **[!UICONTROL Site Settings]**。

* **[!UICONTROL SAFE Rules]**. 次のいずれかを選択します。
   * **[!UICONTROL Apply SAFE Rules]**. すべてのセーフルールをこのストリームに適用します。
   * **[!UICONTROL Apply SAFE Rules for:]** このストリームルールのセーフルールを適用するには、1つまたは複数のオプションを選択します。
   * **[!UICONTROL Disable SAFE Rules]**. このストリームには、セーフルールを適用しないでください。

ソーシャルネットワークまたはコンテンツタイプに固有のストリームルールオプションについては、それぞれのソーシャルネットワークまたはコンテンツタイプに関する次のドキュメントを参照してください。

* [Facebookページ](../c-streams/c-facebook-page-rules.md#c_facebook_page_rules)
* [電子メール](../c-streams/c-email-rules.md#c_email_rules)
* [Instagram](../c-streams/c-instagram-rules.md#c_instagram_rules)
* [Tumblr](../c-streams/c-tumblr-rules.md#c_tumblr_rules)
* [Twitter](../c-streams/c-twitter-rules.md#c_twitter_rules)
* [YouTube](../c-streams/c-youtube-rules/c-youtube-rules.md#c_youtube_rules)
* [RSS](../c-streams/c-rss-rules-streams.md#c_rss_rules_streams)
