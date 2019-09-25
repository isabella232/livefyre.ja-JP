---
description: カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-description: カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-title: Studioを使用したカルーセルのカスタマイズ
solution: Experience Manager
title: Studioを使用したカルーセルのカスタマイズ
uuid: 24f080fc-37bf-40d4-8c1a-a502ee8ac978
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Studioを使用したカルーセルのカスタマイズ{#customize-a-carousel-using-studio}

カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。

すべてのアプリでは、 **[!UICONTROL Style]** とのオ **[!UICONTROL Config]** プションが使用されま **[!UICONTROL App Designer]**&#x200B;す。 の標準およびすべてのアプリのオプションについて詳しくは、ア **[!UICONTROL Style]** プリのカ **[!UICONTROL Config]** スタマイズを参照してくださ **[!UICONTROL App Designer]**&#x200B;い。

カルーセルは、App Designerの次の追加オプションを使用してカスタマイズできます。

* **[!UICONTROL Max Number of Items]**

   カルーセルに表示する項目数を設定します。 デフォルトは 50 です。

* **[!UICONTROL Orientation]**

   **[!UICONTROL Responsive]**. コンピューター画面のみ

   * コンテンツが600ピクセルを超える場合は、横方向に表示されます。
   * コンテンツが600ピクセル未満の場合は、垂直方向に表示されます。
   * **バーティカル.** コンピューター画面またはモバイルデバイスの場合。 モバイルデバイスでは、カードは画面のサイズに合わせて縮小されます。

* **[!UICONTROL Call-to-action button]** 商品カタログに対して「誘い文句（CTA：コールトゥアクション）」ボタンを使用すると、ユーザーを商品やサイトに誘導して、さらなるアクションを実行できます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、誘い文句（CTA：コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** オンに切り替えると、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与する必要があります。
   >[!NOTE]
   >
   >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない限り、誘い文句（CTA：コールトゥアクション）ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. サイトの訪問者がカードをクリックして大きなウィンドウでコンテンツを開いた場合にのみ、誘い文句（CTA：コールトゥアクション）ボタンを表示する代わりに、誘い文句（CTA：コールトゥアクション）ボタンをタイルに表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーがカードをクリックして誘い文句（CTA：コールトゥアクション）モーダルを開くように促すテキストです。
   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンの上のヘッダーに表示する単語。 デフォルトのテキストは「Shop these products:」です。
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンに表示する単語。 デフォルトのテキストは「Buy Now:」です。
   * **[!UICONTROL Product display options]** とを表示するかどうかを選択し **[!UICONTROL Photo]** 、「誘い文 **[!UICONTROL Product name]** 句（CTA：コールトゥアクション）」ボタンを使用します。
   >[!NOTE]
   >
   >「写真」ボタンと「製品名」ボタンが有効な場合は、両方とも青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンにして、このアプリから関連製品ページへのリファラルを追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** 関連する製品ページに、アプリのコンテンツからの参照追跡をさらに指定するパラメーターを追加します。



* **[!UICONTROL Embed App in multiple pages]**

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 製品固有のUGCを、各製品ページでアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。 複数のフォルダを選択するには、CtrlキーまたはCommandキーを押しながらクリックします。 Livefyreは、このフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**. これを切り替えて、アプリに投稿したコンテンツを、異なる製品IDでタグ付けして表示します。 アプリの製品固有のコンテンツが表示された後、Livefyreは他の製品のコンテンツと、製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先し、次に他の製品IDを持つアプリにコンテンツを公開し、次に製品IDを持たないアプリにコンテンツを公開します。
