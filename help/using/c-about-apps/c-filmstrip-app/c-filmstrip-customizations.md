---
description: null
seo-description: null
seo-title: フィルムストリップのカスタマイズ
solution: Experience Manager
title: フィルムストリップのカスタマイズ
uuid: 99f8b697-4aa3-4813- bcac- d0e0bdee252d
translation-type: tm+mt
source-git-commit: bd989c97ae5cf06a5ac3deec215f865b0fe95d16

---


# フィルムストリップのカスタマイズ{#filmstrip-customizations}

すべてのアプリの使用および **[!UICONTROL Style]****[!UICONTROL Config]** オプション **[!UICONTROL App Designer]**。詳しく **[!UICONTROL Style]** は **[!UICONTROL Config]** 、 **[!UICONTROL App Designer.]**

App Designerでは、次の追加オプションを使用してフィルムストリップをカスタマイズできます。

* **[!UICONTROL Content fit]**. カード **[!UICONTROL crop]** を埋めるコンテンツを切り抜き、カード全体 **[!UICONTROL Aspect Ratio]** を占めているかどうか、カード全体を占めていないかどうかをカードに表示します。
* **[!UICONTROL Tile Size]**. タイルのサイズをピクセル単位で入力します。
* **[!UICONTROL Show Notifications]**. 新規コンテンツの通知をフィルムストリップアプリに表示するかどうかを選択します。
* **[!UICONTROL Require rights]**. このオプションを有効にすると、権限リクエストステータスのコンテンツのみが表示されます。
* **[!UICONTROL Hide social branding when rights granted]** このスイッチをオンにすると、コンテンツの一部に対する権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴが削除されます。
* **[!UICONTROL Call-to-action button]** 誘い文句（CTA:コールトゥアクション）ボタンを製品カタログと共に使用して、ユーザを製品やサイトに誘導し、さらなるアクションをとることができます。

   * **[!UICONTROL Call-to-action button]** 切り替えをオンに切り替えて、誘い文句（CTA:コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** 切り替えをオンに切り替えて、コンテンツの所有者がコンテンツに対して誘い文句（CTA:コールトゥアクション）ボタンを表示する前にコンテンツの権利を付与していることを求めます。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でもコンテンツが表示されますが、コンテンツの権利が付与されない限り、誘い文句（CTA:コールトゥアクション）ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. サイト訪問者がカードをクリックしてより大きいウィンドウでコンテンツを開く場合にのみ、誘い文句（CTA:コールトゥアクション）ボタンをフィルムストリップタイルに表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーにカードのクリックを促し、誘い文句（CTA:コールトゥアクション）モーダルを開くように促すテキストです。
   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA:コールトゥアクション）ボタンの上にあるヘッダーに表示する単語です。デフォルトのテキストは"Shop These products"です。」.
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA:コールトゥアクション）ボタンに表示する単語です。デフォルトのテキストは"Buy Now"です。」.
   * **[!UICONTROL Product display options]** 誘い文句（CTA:コールトゥアクション）ボタン **[!UICONTROL Photo]** を表示 **[!UICONTROL Product name]** するかどうかを選択します。

      >[!NOTE]
      >
      >「写真」ボタンと「製品名」ボタンは、有効になっているときに青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンに切り替えて、このアプリから関連付けられている製品ページに照会を追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** パラメーターを追加して、アプリコンテンツから関連する製品ページへの照会トラッキングをさらに指定します。

* **[!UICONTROL Embed App in multiple pages]**.

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページ用に1つのアプリを作成するには、このオプションを選択します。製品固有のUGCを各製品ページのアプリにフィルターします。1つまたは複数のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。複数のフォルダを選択するには、CtrlまたはCommandキーを押しながらクリックします。Livefyreはフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを判断します。
   * **[!UICONTROL Show related content]**. これを切り替えると、アプリに投稿されたコンテンツが表示されますが、別の製品IDでタグ付けされます。アプリに固有のコンテンツが表示された後、Livefyreはその製品に関連付けられていない他の製品やコンテンツのコンテンツを表示します。Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、その後、他の製品IDと共にアプリに投稿されたコンテンツを、製品IDなしでアプリに公開します。

Livefyre. jsを使用したフィルムストリップのカスタマイズ方法について詳しくは [、フィルムストリップオプション](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) を参照してください。

