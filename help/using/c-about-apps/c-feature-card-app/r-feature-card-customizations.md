---
description: マップアプリのサイズ、幅およびインタラクションオプションを変更します。
title: 機能カードのカスタマイズ
exl-id: b907885a-211d-4628-9955-5f1a5ec577cf
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# 機能カードのカスタマイズ{#feature-card-customizations}

マップアプリのサイズ、幅およびインタラクションオプションを変更します。

<!-- 
r_feature_card_customization.dita
 -->

機能カードアプリには、標準のカスタマイズ(** [!UICONTROL Theme]**)、ブランド色、フォントファミリー、フォントサイズのみが含まれます。

フィーチャカードは、次を使用してカスタマイズできます。

* **[!UICONTROL Style]** 」および「」のすべてのアプリの **[!UICONTROL Config]** オプションを選択し **[!UICONTROL App Designer]**&#x200B;ます。**[!UICONTROL App Designer]**&#x200B;のすべてのアプリの標準&#x200B;**[!UICONTROL Style]**&#x200B;および&#x200B;**[!UICONTROL Config]**&#x200B;オプションについて詳しくは、「アプリのカスタマイズ」を参照してください。

* 統合ツール。 統合ツールを使用してアプリをカスタマイズする方法について詳しくは、「アプリの統合」を参照してください。
* **[!UICONTROL Call-to-action button]** 誘い文句（CTA：コールトゥアクション）ボタンを製品カタログと共に使用して、ユーザーを製品やサイトに誘導し、その後のアクションを促すことができます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、「誘い文句（CTA：コールトゥアクション）」ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** 切り替えをオンにして、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与していることを必須にします。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない場合は、「行動喚起」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルで、アクションの呼び出しボタンの上にヘッダーに表示する単語。デフォルトの言い回しは、「次の製品を購入する：」です。
   * **[!UICONTROL Call-to-action button text]** 「誘い文句（CTA：コールトゥアクション）」ボタンのテキストをカスタマイズします。デフォルトのテキストは、「Buy Now」です。
   * **[!UICONTROL Product display options]** とを表示するかどうかを選択し **[!UICONTROL Photo]** 、「誘い文句（CTA：コールトゥアクション）」ボタン **[!UICONTROL Product name]** を表示します。
   * **[!UICONTROL Product URL referral tracking]** このアプリから関連する製品ページへの照会を追跡するには、トグルをオンに切り替えます。
   * **[!UICONTROL Referral tracking key-value pairs]** アプリのコンテンツから関連する製品ページへのリファラル追跡をさらに指定するための追加パラメーター。

* **[!UICONTROL Product page filter]**

   * **[!UICONTROL Filter UGC by Product ID]**&#x200B;をインストールします。複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 各製品ページで、製品固有のUGCをアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**&#x200B;をインストールします。UGCのフィルタリングに使用する最上位の製品フォルダを選択します。 `CTRL/Command + click`を使用して、複数のフォルダーを選択します。 Livefyreはこのフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**&#x200B;をインストールします。これを切り替えて、アプリに投稿されたが、異なる製品IDでタグ付けされたコンテンツを表示します。 アプリ用の製品固有のコンテンツが表示されると、Livefyreは他の製品のコンテンツと製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、次に他の製品IDを持つアプリに公開したコンテンツ、次に製品IDを持たないアプリに公開したコンテンツを優先順位付けします。
