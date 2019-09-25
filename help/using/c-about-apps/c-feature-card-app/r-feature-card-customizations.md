---
description: マップアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-description: マップアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-title: Feature Card Customizations
solution: Experience Manager
title: Feature Card Customizations
uuid: dd43c076-027f-42c8-be2e-7d863d4e3976
translation-type: tm+mt
source-git-commit: a014b5cd618672934843f1adf20d6b2cc504e2d8

---


# Feature Card Customizations{#feature-card-customizations}

マップアプリのサイズ、幅およびインタラクションオプションを変更します。

<!-- 
r_feature_card_customization.dita
 -->

Feature Card Apps include only standard customizations:** **, Brand color, Font family, and Font size.[!UICONTROL Theme]

You can customize Feature Cards using:

* **[!UICONTROL Style]** and  options for all Apps in the . **[!UICONTROL Config]****[!UICONTROL App Designer]** See Customizing Apps for details on the standard  and  options for all Apps in the .**[!UICONTROL Style]****[!UICONTROL Config]****[!UICONTROL App Designer]**

* Integration tools. See App Integrations for more on how to customize Apps using Integration Tools.
* **[!UICONTROL Call-to-action button]** 商品カタログに対して「誘い文句（CTA：コールトゥアクション）」ボタンを使用すると、ユーザーを商品やサイトに誘導して、さらなるアクションを実行できます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、「誘い文句（CTA：コールトゥアクション）」ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** Switch the toggle to on to require that the content owner has granted rights for the content before a Call-to-action button appears for the content.

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない限り、「誘い文句（CTA：コールトゥアクション）」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンの上のヘッダーに表示する単語。 デフォルトの言い回しは「次の製品を購入する：」です。
   * **[!UICONTROL Call-to-action button text]** 誘い文句（CTA：コールトゥアクション）ボタンのテキストをカスタマイズします。 デフォルトのテキストは「Buy Now」です。
   * **[!UICONTROL Product display options]** とを表示するかどうかを選択し **[!UICONTROL Photo]** 、「誘い文 **[!UICONTROL Product name]** 句（CTA：コールトゥアクション）」ボタンを使用します。
   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンにして、このアプリから関連製品ページへのリファラルを追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** 関連する製品ページに、アプリのコンテンツからの参照追跡をさらに指定するパラメーターを追加します。

* **[!UICONTROL Product page filter]**

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 製品固有のUGCを、各製品ページでアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。 複数のフ `CTRL/Command + click` ォルダーを選択する場合に使用します。 Livefyreはこのフォルダーを使用して、そのフォルダー内の製品のうち、様々なページのアプリに表示する製品を決定します。
   * **[!UICONTROL Show related content]**. これを切り替えて、アプリに投稿したコンテンツを、異なる製品IDでタグ付けして表示します。 アプリの製品固有のコンテンツが表示された後、Livefyreは他の製品のコンテンツと、製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先し、次に他の製品IDを持つアプリにコンテンツを公開し、次に製品IDを持たないアプリにコンテンツを公開します。

