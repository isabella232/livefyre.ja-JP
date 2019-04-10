---
description: Mosaicアプリケーションのサイズ、幅、操作オプションを変更します。
seo-description: Mosaicアプリケーションのサイズ、幅、操作オプションを変更します。
seo-title: モザイクのカスタマイズ
solution: Experience Manager
title: モザイクのカスタマイズ
uuid: 4e226d68- f517-4922- bc25-655d524d7d52
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# モザイクのカスタマイズ{#mosaic-customizations}

Mosaicアプリケーションのサイズ、幅、操作オプションを変更します。

すべてのアプリの使用および **[!UICONTROL Style]****[!UICONTROL Config]** オプション **[!UICONTROL App Designer]**。詳しく **[!UICONTROL Style]** は **[!UICONTROL Config]** 、 **[!UICONTROL App Designer.]**

App Designerの次の追加オプションを使用して、Mosaicをカスタマイズできます。

* **[!UICONTROL Content interaction]**. ページに新しいコンテンツをロードするスタイルを設定します。

   * **[!UICONTROL Hover Fade]** を指定します。
   * **[!UICONTROL Hover Flip]** を指定します。
   * **[!UICONTROL Click]** をクリックします。

* **[!UICONTROL Number of Tiles to Load]**. Mosaicに読み込むタイルの数。これは出力の表示に影響を与える場合があります。コンテナの幅に対応する適切なタイル数を選択しない限り、モザイクにモザイクが表示されません。グリッドが正しく表示されるように調整する必要があります。
* **[!UICONTROL Hide social branding when rights granted]** このスイッチをオンにすると、コンテンツの一部に対する権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴが削除されます。

* **[!UICONTROL Call-to-action button]** 「誘い文句（CTA:コールトゥアクション）」ボタンを製品カタログと共に使用して、ユーザーを製品またはサイトに誘導し、さらにアクションをとることができます。

   * **[!UICONTROL Call-to-action button]** 切り替えをオンに切り替えて、誘い文句（CTA:コールトゥアクション）ボタンを表示します。

   * **[!UICONTROL Require rights to display products]** 切り替えをオンに切り替えて、コンテンツの所有者がコンテンツに対して「誘い文句（CTA:コールトゥアクション）」ボタンが表示されるまでコンテンツの権利を付与していることを求めます。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でもコンテンツが表示されますが、コンテンツの権利が付与されていない限り、「誘い文句（CTA:コールトゥアクション）」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. サイト訪問者がカードをクリックしてより大きいウィンドウでコンテンツを開く場合にのみ、誘い文句（CTA:コールトゥアクション）ボタンをフィルムストリップタイルに表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーにカードのクリックを促し、誘い文句（CTA:コールトゥアクション）モーダルを開くように促すテキストです。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの「誘い文句（CTA:コールトゥアクション）」ボタンの上にあるヘッダーに表示する単語です。デフォルトの言い回しは、"Shopこれらの製品」です。」.

   * **[!UICONTROL Call-to-action button text]** 誘い文句（CTA:コールトゥアクション）ボタンのテキストをカスタマイズします。デフォルトのテキストは"Buy Now"です。

   * **[!UICONTROL Product display options]** 「誘い文句（CTA:コールトゥアクション） **[!UICONTROL Photo]** 」ボタンを **[!UICONTROL Product name]** 表示するかどうかを選択します。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンに切り替えて、このアプリから関連付けられている製品ページに照会を追跡します。

   * **[!UICONTROL Referral tracking key-value pairs]** パラメーターを追加して、アプリコンテンツから関連する製品ページへの照会トラッキングをさらに指定します。

* **[!UICONTROL Product page filter]**.

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページ用に1つのアプリを作成するには、このオプションを選択します。製品固有のUGCを各製品ページのアプリにフィルターします。1つまたは複数のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。複数のフォルダを選択するには、CtrlまたはCommandキーを押しながらクリックします。Livefyreはフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを判断します。
   * **[!UICONTROL Show related content]**. これを切り替えると、アプリに投稿されたコンテンツが表示されますが、別の製品IDでタグ付けされます。アプリに固有のコンテンツが表示された後、Livefyreはその製品に関連付けられていない他の製品やコンテンツのコンテンツを表示します。Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、その後、他の製品IDと共にアプリに投稿されたコンテンツを、製品IDなしでアプリに公開します。

Livefyre. jsを使用したモザイクのカスタマイズ方法について詳しくは [、"Mosaic Options](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md) 」を参照してください。
