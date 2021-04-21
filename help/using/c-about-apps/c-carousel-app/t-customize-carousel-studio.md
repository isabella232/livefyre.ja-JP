---
description: カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。
title: Studioを使用したカルーセルのカスタマイズ
exl-id: f6f681ac-c601-40b9-9e99-bf5495f505f8
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Studioを使用したカルーセルのカスタマイズ{#customize-a-carousel-using-studio}

カルーセルアプリのサイズ、幅およびインタラクションオプションを変更します。

すべてのアプリで、**[!UICONTROL App Designer]**&#x200B;の&#x200B;**[!UICONTROL Style]**&#x200B;と&#x200B;**[!UICONTROL Config]**&#x200B;オプションを使用します。 **[!UICONTROL App Designer]**&#x200B;のすべてのアプリの標準&#x200B;**[!UICONTROL Style]**&#x200B;および&#x200B;**[!UICONTROL Config]**&#x200B;オプションについて詳しくは、「アプリのカスタマイズ」を参照してください。

カルーセルは、App Designerの次の追加オプションを使用してカスタマイズできます。

* **[!UICONTROL Max Number of Items]**

   カルーセルに表示する項目数を設定します。 デフォルトは 50 です。

* **[!UICONTROL Orientation]**

   **[!UICONTROL Responsive]**&#x200B;をインストールします。コンピューター画面のみ

   * コンテンツが600ピクセルを超える場合は、は水平方向に表示されます
   * コンテンツが600ピクセル未満の場合は、は垂直方向に表示します
   * **バーティカル.** コンピューター画面またはモバイルデバイスの場合。モバイルデバイスでは、カードは画面のサイズに合わせて縮小されます。

* **[!UICONTROL Call-to-action button]** 誘い文句（CTA：コールトゥアクション）ボタンを製品カタログと共に使用して、ユーザーを製品やサイトに誘導し、その後のアクションを促すことができます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、誘い文句（CTA：コールトゥアクション）ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** オンに切り替えると、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与している必要があります。

   >[!NOTE]
   >
   >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない場合は、アクションの呼び出しボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Show call-to-action in tile]**&#x200B;をインストールします。サイト訪問者がカードをクリックして大きいウィンドウでコンテンツを開いた場合にのみ、誘い文句（CTA：コールトゥアクション）ボタンを表示する代わりに、誘い文句（CTA：コールトゥアクション）ボタンをタイルに表示するかどうかを選択します。
   * **[!UICONTROL Call-to-action indication text]** ユーザーがカードをクリックして誘い文句（CTA：コールトゥアクション）モーダルを開くように促すテキストです。
   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルで、アクションの呼び出しボタンの上にヘッダーに表示する単語。デフォルトのテキストは、「Shop these products:」です。
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンに表示する単語。デフォルトのテキストは、「Buy Now:」です。
   * **[!UICONTROL Product display options]** とを表示するかどうかを選択し **[!UICONTROL Photo]** 、「誘い文句（CTA：コールトゥアクション）」ボタン **[!UICONTROL Product name]** を表示します。

   >[!NOTE]
   >
   >「写真」ボタンと「製品名」ボタンが有効な場合は、両方とも青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** このアプリから関連する製品ページへの照会を追跡するには、トグルをオンに切り替えます。
   * **[!UICONTROL Referral tracking key-value pairs]** アプリのコンテンツから関連する製品ページへのリファラル追跡をさらに指定するための追加パラメーター。



* **[!UICONTROL Embed App in multiple pages]**

   * **[!UICONTROL Filter UGC by Product ID]**&#x200B;をインストールします。複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 各製品ページで、製品固有のUGCをアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**&#x200B;をインストールします。UGCのフィルタリングに使用する最上位の製品フォルダを選択します。 複数のフォルダーを選択するには、CtrlまたはCommandキーを押しながらクリックします。 Livefyreはこのフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**&#x200B;をインストールします。これを切り替えて、アプリに投稿されたが、異なる製品IDでタグ付けされたコンテンツを表示します。 アプリ用の製品固有のコンテンツが表示されると、Livefyreは他の製品のコンテンツと製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、次に他の製品IDを持つアプリに公開したコンテンツ、次に製品IDを持たないアプリに公開したコンテンツを優先順位付けします。
