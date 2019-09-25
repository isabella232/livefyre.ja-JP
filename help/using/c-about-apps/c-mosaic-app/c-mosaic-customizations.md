---
description: Mosaicアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-description: Mosaicアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-title: Mosaicのカスタマイズ
solution: Experience Manager
title: Mosaicのカスタマイズ
uuid: 4e226d68-f517-4922-bc25-655d524d7d52
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Mosaicのカスタマイズ{#mosaic-customizations}

Mosaicアプリのサイズ、幅およびインタラクションオプションを変更します。

すべてのアプリでは、 **[!UICONTROL Style]** とのオ **[!UICONTROL Config]** プションが使用されま **[!UICONTROL App Designer]**&#x200B;す。 標準およびすべてのアプリのオプションにつ **[!UICONTROL Style]** いて詳し **[!UICONTROL Config]** くは、「アプリのカスタマイズ」を参照してください。 **[!UICONTROL App Designer.]**

Mosaicは、App Designerの次の追加オプションを使用してカスタマイズできます。

* **[!UICONTROL Content interaction]**. ページに読み込む新しいコンテンツのスタイルを設定します。

   * **[!UICONTROL Hover Fade]** を指定します。
   * **[!UICONTROL Hover Flip]** を指定します。
   * **[!UICONTROL Click]** を指定します。

* **[!UICONTROL Number of Tiles to Load]**. Mosaicに読み込むタイルの数です。 これは出力表示に影響を与える可能性があります。 コンテナの幅に対応するタイルの数を正しく選択しない限り、モザイクはグリッドに表示されません。 グリッドが正しく表示されるように、これらを調整する必要がある場合があります。
* **[!UICONTROL Hide social branding when rights granted]** このオプションをオンにすると、コンテンツに対する権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴが削除されます。

* **[!UICONTROL Call-to-action button]** 商品カタログに対して「誘い文句（CTA：コールトゥアクション）」ボタンを使用すると、ユーザーを商品やサイトに誘導して、さらなるアクションを実行できます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、「誘い文句（CTA：コールトゥアクション）」ボタンを表示します。

   * **[!UICONTROL Require rights to display products]** オンに切り替えると、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与する必要があります。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない限り、「誘い文句（CTA：コールトゥアクション）」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. サイトの訪問者がカードをクリックし、コンテンツを大きなウィンドウで開いた場合にのみ、誘い文句（CTA：コールトゥアクション）ボタンを表示する代わりに、フィルムストリップタイルに誘い文句（CTA：コールトゥアクション）ボタンを表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーがカードをクリックして誘い文句（CTA：コールトゥアクション）モーダルを開くように促すテキスト。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンの上のヘッダーに表示する単語。 デフォルトの言い回しは「次の製品を購入する：」です。

   * **[!UICONTROL Call-to-action button text]** 誘い文句（CTA：コールトゥアクション）ボタンのテキストをカスタマイズします。 デフォルトのテキストは「Buy Now」です。

   * **[!UICONTROL Product display options]** とを表示するかどうかを選択し **[!UICONTROL Photo]** 、「誘い文 **[!UICONTROL Product name]** 句（CTA：コールトゥアクション）」ボタンを使用します。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンにして、このアプリから関連製品ページへのリファラルを追跡します。

   * **[!UICONTROL Referral tracking key-value pairs]** 関連する製品ページに、アプリのコンテンツからの参照追跡をさらに指定するパラメーターを追加します。

* **[!UICONTROL Product page filter]**.

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 製品固有のUGCを、各製品ページでアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。 複数のフォルダを選択するには、CtrlキーまたはCommandキーを押しながらクリックします。 Livefyreは、このフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**. これを切り替えて、アプリに投稿したコンテンツを、異なる製品IDでタグ付けして表示します。 アプリの製品固有のコンテンツが表示された後、Livefyreは他の製品のコンテンツと、製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先し、次に他の製品IDを持つアプリにコンテンツを公開し、次に製品IDを持たないアプリにコンテンツを公開します。

Livefyre.jsを使用し [てMosaicをカスタマイズする方法について詳しくは、Mosaic Options](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) （モザイクオプション）を参照してください。
