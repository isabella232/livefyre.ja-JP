---
description: アプリのサイズ、幅、およびインタラクションオプションを変更します。
seo-description: アプリのサイズ、幅、およびインタラクションオプションを変更します。
seo-title: 機能カードのカスタマイズ
solution: Experience Manager
title: 機能カードのカスタマイズ
uuid: dd43c076-027f-42c8- be2e-7d863d4e3976
translation-type: tm+mt
source-git-commit: a014b5cd618672934843f1adf20d6b2cc504e2d8

---


# 機能カードのカスタマイズ{#feature-card-customizations}

アプリのサイズ、幅、およびインタラクションオプションを変更します。

<!-- 
r_feature_card_customization.dita
 -->

機能カードアプリには、標準的なカスタマイズのみが含まれています。** [!UICONTROL Theme]**、ブランドカラー、フォントファミリー、フォントサイズ。

以下を使用して、機能カードをカスタマイズできます。

* **[!UICONTROL Style]** およびすべてのアプリの **[!UICONTROL Config]** オプション **[!UICONTROL App Designer]** を参照してください。すべてのアプリの標準 **[!UICONTROL Style]** および **[!UICONTROL Config]** オプションについて詳しくは、アプリのカスタマイズを参照 **[!UICONTROL App Designer]** してください。

* 統合ツール。統合ツールを使用してアプリケーションをカスタマイズする方法について詳しくは、アプリ統合を参照してください。
* **[!UICONTROL Call-to-action button]** 「誘い文句（CTA:コールトゥアクション）」ボタンを製品カタログと共に使用して、ユーザーを製品またはサイトに誘導し、さらにアクションをとることができます。

   * **[!UICONTROL Call-to-action button]** 切り替えをオンに切り替えて、誘い文句（CTA:コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** 切り替えをオンに切り替えて、コンテンツの所有者がコンテンツに対して「誘い文句（CTA:コールトゥアクション）」ボタンが表示されるまでコンテンツの権利を付与していることを求めます。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でもコンテンツが表示されますが、コンテンツの権利が付与されていない限り、「誘い文句（CTA:コールトゥアクション）」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの「誘い文句（CTA:コールトゥアクション）」ボタンの上にあるヘッダーに表示する単語です。デフォルトの言い回しは、&quot;Shopこれらの製品」です。」.
   * **[!UICONTROL Call-to-action button text]** 誘い文句（CTA:コールトゥアクション）ボタンのテキストをカスタマイズします。デフォルトのテキストは&quot;Buy Now&quot;です。
   * **[!UICONTROL Product display options]** 「誘い文句（CTA:コールトゥアクション） **[!UICONTROL Photo]** 」ボタンを **[!UICONTROL Product name]** 表示するかどうかを選択します。
   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンに切り替えて、このアプリから関連付けられている製品ページに照会を追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** パラメーターを追加して、アプリコンテンツから関連する製品ページへの照会トラッキングをさらに指定します。

* **[!UICONTROL Product page filter]** 

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページ用に1つのアプリを作成するには、このオプションを選択します。製品固有のUGCを各製品ページのアプリにフィルターします。1つまたは複数のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。複数のフォルダーを選択する場合に使用 `CTRL/Command + click` します。Livefyreはフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを判断します。
   * **[!UICONTROL Show related content]**. これを切り替えると、アプリに投稿されたコンテンツが表示されますが、別の製品IDでタグ付けされます。アプリに固有のコンテンツが表示された後、Livefyreはその製品に関連付けられていない他の製品やコンテンツのコンテンツを表示します。Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、その後、他の製品IDと共にアプリに投稿されたコンテンツを、製品IDなしでアプリに公開します。

