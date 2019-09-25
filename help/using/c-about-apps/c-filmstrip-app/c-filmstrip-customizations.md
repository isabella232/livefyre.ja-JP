---
description: 'null'
seo-description: 'null'
seo-title: Filmstripのカスタマイズ
solution: Experience Manager
title: Filmstripのカスタマイズ
uuid: 99f8b697-4aa3-4813-bcac-d0e0bdee252d
translation-type: tm+mt
source-git-commit: bd989c97ae5cf06a5ac3deec215f865b0fe95d16

---


# Filmstripのカスタマイズ{#filmstrip-customizations}

すべてのアプリでは、 **[!UICONTROL Style]** とのオ **[!UICONTROL Config]** プションが使用されま **[!UICONTROL App Designer]**&#x200B;す。 標準およびすべてのアプリのオプションにつ **[!UICONTROL Style]** いて詳し **[!UICONTROL Config]** くは、「アプリのカスタマイズ」を参照してください。 **[!UICONTROL App Designer.]**

App Designerで次の追加オプションを使用して、フィルムストリップをカスタマイズできます。

* **[!UICONTROL Content fit]**. カード **[!UICONTROL crop]** 全体に表示されるかどうかに関係なく、カード全体に表示され **[!UICONTROL Aspect Ratio]** るようにコンテンツを切り抜くか、カード全体を表示するかを選択します。
* **[!UICONTROL Tile Size]**. タイルのサイズをピクセル単位で入力します。
* **[!UICONTROL Show Notifications]**. 新しいコンテンツがフィルムストリップアプリにストリーミングされる際に通知を表示するかどうかを選択します。
* **[!UICONTROL Require rights]**. 権限要求のステータスが「許可済み」のコンテンツのみを表示する場合は、このオプションを有効にします。
* **[!UICONTROL Hide social branding when rights granted]** このオプションをオンにすると、コンテンツに対する権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴが削除されます。
* **[!UICONTROL Call-to-action button]** 商品カタログに対して誘い文句（CTA：コールトゥアクション）ボタンを使用すると、ユーザを商品やサイトに誘導して、さらなるアクションを実行できます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、誘い文句（CTA：コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** オンに切り替えると、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与する必要があります。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない限り、誘い文句（CTA：コールトゥアクション）ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. サイトの訪問者がカードをクリックし、コンテンツを大きなウィンドウで開いた場合にのみ、誘い文句（CTA：コールトゥアクション）ボタンを表示する代わりに、フィルムストリップタイルに誘い文句（CTA：コールトゥアクション）ボタンを表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーがカードをクリックして誘い文句（CTA：コールトゥアクション）モーダルを開くように促すテキストです。
   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンの上のヘッダーに表示する単語。 デフォルトのテキストは「Shop these products:」です。
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンに表示する単語。 デフォルトのテキストは「Buy Now:」です。
   * **[!UICONTROL Product display options]** とを表示するかどうかを、誘い文 **[!UICONTROL Photo]** 句(CTA：コ **[!UICONTROL Product name]** ールトゥアクション)ボタンで選択します。

      >[!NOTE]
      >
      >「写真」ボタンと「製品名」ボタンが有効な場合は、両方とも青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンにして、このアプリから関連製品ページへのリファラルを追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** 関連する製品ページに、アプリのコンテンツからの参照追跡をさらに指定するパラメーターを追加します。

* **[!UICONTROL Embed App in multiple pages]**.

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 製品固有のUGCを、各製品ページでアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。 複数のフォルダを選択するには、CtrlキーまたはCommandキーを押しながらクリックします。 Livefyreはこのフォルダーを使用して、そのフォルダー内の製品のうち、様々なページのアプリに表示する製品を決定します。
   * **[!UICONTROL Show related content]**. これを切り替えて、アプリに投稿したコンテンツを、異なる製品IDでタグ付けして表示します。 アプリの製品固有のコンテンツが表示された後、Livefyreは他の製品のコンテンツと、製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先し、次に他の製品IDを持つアプリにコンテンツを公開し、次に製品IDを持たないアプリにコンテンツを公開します。

Livefyre.jsを使用し [](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) てフィルムストリップをカスタマイズする方法について詳しくは、Filmstrip Optionsを参照してください。

