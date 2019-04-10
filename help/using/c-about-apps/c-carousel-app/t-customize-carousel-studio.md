---
description: カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-description: カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-title: Studioを使用したカルーセルのカスタマイズ
solution: Experience Manager
title: Studioを使用したカルーセルのカスタマイズ
uuid: 24f080fc-37bf-40d4-8c1a- a502ee8ac978
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Studioを使用したカルーセルのカスタマイズ{#customize-a-carousel-using-studio}

カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。

すべてのアプリの使用および **[!UICONTROL Style]****[!UICONTROL Config]** オプション **[!UICONTROL App Designer]**。すべてのアプリの標準 **[!UICONTROL Style]** および **[!UICONTROL Config]** オプションについて詳しくは、アプリのカスタマイズを参照 **[!UICONTROL App Designer]**してください。

アプリデザイナーの次の追加オプションを使用して、カルーセルをカスタマイズできます。

* **[!UICONTROL Max Number of Items]**

   カルーセルに表示する項目の数を設定します。初期設定は50です。

* **[!UICONTROL Orientation]**

   **[!UICONTROL Responsive]**. コンピューターの画面のみ

   * コンテンツが600ピクセルを超える場合、水平方向に表示
   * コンテンツが600ピクセル未満の場合、垂直方向に表示
   * **垂直方向。** コンピューター画面または携帯端末の場合。携帯端末では、カードは画面サイズに合わせて縮小されます。

* **[!UICONTROL Call-to-action button]** 「誘い文句（CTA:コールトゥアクション）」ボタンを製品カタログと共に使用して、ユーザーを製品またはサイトに誘導し、さらにアクションをとることができます。

   * **[!UICONTROL Call-to-action button]** 切り替えをオンに切り替えて、誘い文句（CTA:コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** 切り替えをオンに切り替えて、コンテンツの所有者がコンテンツに対して誘い文句（CTA:コールトゥアクション）ボタンを表示する前にコンテンツの権利を付与していることを求めます。
   >[!NOTE]
   >
   >コンテンツに対する権限が付与されていない場合でもコンテンツが表示されますが、コンテンツの権利が付与されない限り、誘い文句（CTA:コールトゥアクション）ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**. 誘い文句（CTA:コールトゥアクション）ボタンを表示するのではなく、誘い文句（CTA:コールトゥアクション）ボタンを並べて表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーにカードのクリックを促し、誘い文句（CTA:コールトゥアクション）モーダルを開くように促すテキストです。
   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの「誘い文句（CTA:コールトゥアクション）」ボタンの上にあるヘッダーに表示する単語です。デフォルトのテキストは"Shop These products"です。」.
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの「誘い文句（CTA:コールトゥアクション）」ボタンに表示する単語です。デフォルトのテキストは"Buy Now"です。」.
   * **[!UICONTROL Product display options]** 「誘い文句（CTA:コールトゥアクション） **[!UICONTROL Photo]** 」ボタンを **[!UICONTROL Product name]** 表示するかどうかを選択します。
   >[!NOTE]
   >
   >「写真」ボタンと「製品名」ボタンは、有効になっているときに青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンに切り替えて、このアプリから関連付けられている製品ページに照会を追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** パラメーターを追加して、アプリコンテンツから関連する製品ページへの照会トラッキングをさらに指定します。



* **[!UICONTROL Embed App in multiple pages]**

   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページ用に1つのアプリを作成するには、このオプションを選択します。製品固有のUGCを各製品ページのアプリにフィルターします。1つまたは複数のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。複数のフォルダを選択するには、CtrlまたはCommandキーを押しながらクリックします。Livefyreはフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを判断します。
   * **[!UICONTROL Show related content]**. これを切り替えると、アプリに投稿されたコンテンツが表示されますが、別の製品IDでタグ付けされます。アプリに固有のコンテンツが表示された後、Livefyreはその製品に関連付けられていない他の製品やコンテンツのコンテンツを表示します。Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、その後、他の製品IDと共にアプリに投稿されたコンテンツを、製品IDなしでアプリに公開します。
