---
description: これらのオプションは、すべてのソーシャルネットワークまたは投稿方法のすべてのストリームルールに適用されます。
title: すべてのストリームルールのストリームルールオプション
exl-id: eff1a3cb-395f-4eb1-be93-f0f09bba95e2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 5%

---

# すべてのストリームルールのストリームルールオプション{#stream-rule-options-for-all-stream-rules}

これらのオプションは、すべてのソーシャルネットワークまたは投稿方法のすべてのストリームルールに適用されます。

テキストフィールドとキーワードフィールドの検索機能：

* キーワードを入力すると、Livefyreは、個々の単語に対してブール演算子&#x200B;**OR**&#x200B;を自動的に使用します。 例えば、*cake*&#x200B;または&#x200B;*recipe*&#x200B;という単語を含む投稿を検索するには、*cake*&#x200B;と入力し、**[!UICONTROL keyword]**&#x200B;フィールドに&#x200B;*recipe*&#x200B;と入力します。

* 完全に一致するフレーズを引用符で囲むと、完全に一致するフレーズを検索できます。 例えば、「*cake recipe*」というフレーズを検索するには、「**[!UICONTROL keyword]**」フィールドに「*&quot;cake recipe&quot;*」と入力します。

* ブール検索と完全一致のフレーズ検索を1つのストリームルールで組み合わせることができます。 例えば、*cake*、*recipe*、*&quot;cake recipe&quot;*&#x200B;を一度に1つずつ入力して検索できます。

 を使用します&#x200B;**[!UICONTROL Additional Filters]**。

* **[!UICONTROL Media]**&#x200B;をインストールします。次のいずれかを選択します。

   * **[!UICONTROL All Content.]** 任意のコンテンツを許可します。
   * **[!UICONTROL Media Required.]** 画像とビデオのあるコンテンツのみを許可します。(InstagramとFacebookのコンテンツの場合は、**[!UICONTROL Photos]**&#x200B;または&#x200B;**[!UICONTROL Videos]**&#x200B;のみ指定できます)。

* **[!UICONTROL Language]**&#x200B;をインストールします。検索する言語を選択します。 デフォルトの言語は英語です。
* **[!UICONTROL Smart Tags]**&#x200B;をインストールします。コンテンツの識別に使用するタグを選択します。 Livefyreは、コンピューターの視覚技術を使用して、特定のスマートタグで写真やビデオを識別し、より正確に検索できるようにします。 **[!UICONTROL ANY]**&#x200B;修飾子を使用して任意のタグを使用してコンテンツをストリームにフィルターしたり、**[!UICONTROL ALL]**&#x200B;修飾子を使用してコンテンツをすべてのタグを使用するストリームにフィルターしたりします。 **[!UICONTROL Image contains none of these smart tags]**&#x200B;フィールドを使用して、ストリームに含めないコンテンツを含む写真のタグを入力します。 このオプションは、テキストコンテンツに対しては機能しません。

* **[!UICONTROL Products]**&#x200B;をインストールします。製品追加タグを使用して、ストリームルールと製品カタログの製品を一致させます。
* **[!UICONTROL Premoderate]**&#x200B;をインストールします。次のいずれかを選択します。

   * **[!UICONTROL On]**&#x200B;をインストールします。受信するすべてのルールコンテンツを事前モデレートします。 ModQのStreamsセクションから、モデレート済みコンテンツを表示できます。 **[!UICONTROL On]** は、「アプリ設定」の設定を上書きします。
   * **[!UICONTROL Off]**&#x200B;をインストールします。受信するルールの内容を事前にモデレートしないでください。 **[!UICONTROL Off]** は、「アプリ設定」の設定を上書きします。
   * **[!UICONTROL Inherited (Off)]**&#x200B;をインストールします。サイト（**[!UICONTROL Site Settings]**&#x200B;の下）のプレモデレート設定を使用します。

* **[!UICONTROL SAFE Rules]**&#x200B;をインストールします。次のいずれかを選択します。
   * **[!UICONTROL Apply SAFE Rules]**&#x200B;をインストールします。このストリームにすべてのセーフルールを適用します。
   * **[!UICONTROL Apply SAFE Rules for:]** 1つ以上のオプションを選択して、このストリームルールにセーフルールを適用します。
   * **[!UICONTROL Disable SAFE Rules]**&#x200B;をインストールします。このストリームにセーフルールを適用しないでください。

ソーシャルネットワークまたはコンテンツタイプに固有のストリームルールオプションについては、それぞれのソーシャルネットワークまたはコンテンツタイプに関する次のドキュメントを参照してください。

* [Facebook ページ](../c-streams/c-facebook-page-rules.md#c_facebook_page_rules)
* [Email](../c-streams/c-email-rules.md#c_email_rules)
* [Instagram](../c-streams/c-instagram-rules.md#c_instagram_rules)
* [Tumblr](../c-streams/c-tumblr-rules.md#c_tumblr_rules)
* [Twitter](../c-streams/c-twitter-rules.md#c_twitter_rules)
* [YouTube](../c-streams/c-youtube-rules/c-youtube-rules.md#c_youtube_rules)
* [RSS](../c-streams/c-rss-rules-streams.md#c_rss_rules_streams)
