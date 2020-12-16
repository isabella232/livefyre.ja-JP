---
description: Media Wallアプリケーションのサイズ、幅、および操作オプションを変更します。
seo-description: Media Wallアプリケーションのサイズ、幅、および操作オプションを変更します。
seo-title: メディアウォールのカスタマイズ
solution: Experience Manager
title: メディアウォールのカスタマイズ
uuid: 79aecd92-3937-4bb4-a1a6-b090fb39afb0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '733'
ht-degree: 0%

---


# メディアウォールのカスタマイズ{#media-wall-customizations}

Media Wallアプリケーションのサイズ、幅、および操作オプションを変更します。



Media Wallは、ライブ画像やその他のコンテンツをリアルタイムのソーシャルウォールにストリーミングし、イベントを取り囲むすべてのアクティビティを視覚化します。

有効にすると、ユーザーはテキスト、画像またはビデオを直接このアプリに投稿できます。 サポートされるファイル形式を次に示します。

* 画像：JPEG、GIF、PNG
* ビデオ：Quicktime/MOV、MP4、MPEG、WebM
* オーディオ：WAV、WAVE、X-MS-WMA、FLAC、OGG、MPEG

* **[!UICONTROL Items to load]**

   表示するコンテンツ項目の初期数を設定します。

* **[!UICONTROL Load content with animation.]** このオプションをオンにすると、アニメーションを含むページにメディアウォールが読み込まれます。このオプションをオフにすると、アニメーションを使用しないページにメディアウォールが読み込まれます。
* **[!UICONTROL Number of columns.]** メディアウォールの列数を設定列数は、ウィンドウやブラウザのサイズに関係なく同じままです。 「自動」を選択すると、列数が画面サイズに合わせて最適化された列数で表示されるように調整されます。
* **[!UICONTROL Fit content to width]**&#x200B;をインストールします。このオプションをオフにすると、コンテンツは四角形に切り抜かれます。 このオプションをオンにすると、カード全体に画像が入るかどうかに関係なく、カードに画像全体が表示されます。
* **[!UICONTROL Include content modal]**

   ストリーム内の写真をクリックして、オーバーレイされたポップアップウィンドウで開くことができます。

* **[!UICONTROL Require rights]**&#x200B;をインストールします。権限要求のステータスが「許可済み」であるコンテンツのみを表示する場合は、このオプションを有効にします。
* **[!UICONTROL Hide social branding when rights granted]** コンテンツの権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴを削除するには、これをオンにします。

* **[!UICONTROL Upload Button]**

   * **[!UICONTROL Allow user posts]**&#x200B;をインストールします。「アップロード」ボタンを使用してテキスト、写真またはビデオを投稿できるようにするかどうかを選択します。
   * **[!UICONTROL Require Media]**&#x200B;をインストールします。オンに切り替えて、「アップロード」ボタンを使用して写真またはビデオのコンテンツのみをアップロードするようユーザに求めます。
   * 次の「アップロードボタン」フィールドのデフォルトテキストを編集できます。

      * **[!UICONTROL Upload Button Text]**&#x200B;をインストールします。「アップロード」ボタンのテキスト。 デフォルトのテキストは「何を考えていますか？」です。
      * **[!UICONTROL Comment Modal Title]**&#x200B;をインストールします。コンテンツの投稿に使用するモーダルサイト訪問者のタイトル。 デフォルトのテキストは「コメントを投稿」です。
      * **[!UICONTROL Comment Modal Button]**&#x200B;をインストールします。ボタンサイトの訪問者がクリックしてコンテンツを投稿するテキストです。 デフォルトのテキストは「コメントを投稿」です。

* **[!UICONTROL Call-to-action button]** 誘い文句（CTA：コールトゥアクション）ボタンを製品カタログと共に使用して、ユーザーを製品やサイトに誘導し、その後のアクションを促すことができます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、「誘い文句（CTA：コールトゥアクション）」ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** 切り替えをオンにして、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与していることを必須にします。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない場合は、「行動喚起」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルで、アクションの呼び出しボタンの上にヘッダーに表示する単語。デフォルトの言い回しは、「次の製品を購入する：」です。
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンに表示する単語。デフォルトのテキストは、「Buy Now:」です。
   * **[!UICONTROL Product display options]** 写真と製品名を「誘い文句（CTA：コールトゥアクション）」ボタンと共に表示するかどうかを選択します。

      >[!NOTE]
      >
      >「写真」ボタンと「製品名」ボタンが有効な場合は、両方とも青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** このアプリから関連する製品ページへの照会を追跡するには、トグルをオンに切り替えます。
   * **[!UICONTROL Referral tracking key-value pairs]** アプリのコンテンツから関連する製品ページへのリファラル追跡をさらに指定するための追加パラメーター。

* **[!UICONTROL Product page filter]** を参照してください。
   * **[!UICONTROL Filter UGC by Product ID]**&#x200B;をインストールします。複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 各製品ページで、製品固有のUGCをアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**&#x200B;をインストールします。UGCのフィルタリングに使用する最上位の製品フォルダを選択します。 複数のフォルダーを選択するには、CtrlまたはCommandキーを押しながらクリックします。 Livefyreはこのフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**&#x200B;をインストールします。これを切り替えて、アプリに投稿されたが、異なる製品IDでタグ付けされたコンテンツを表示します。 アプリ用の製品固有のコンテンツが表示されると、Livefyreは他の製品のコンテンツと製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先順位付けし、次に他の製品IDを持つアプリに公開したコンテンツ、次に製品IDを持たないアプリに公開したコンテンツを優先順位付けします。

次を使用して、メディアウォールをカスタマイズできます。

* **[!UICONTROL Style]** 」および「」のすべてのアプリの **[!UICONTROL Config]** オプションを選択し **[!UICONTROL App Designer]**&#x200B;ます。**[!UICONTROL App Designer]**&#x200B;のすべてのアプリの標準&#x200B;**[!UICONTROL Style]**&#x200B;および&#x200B;**[!UICONTROL Config]**&#x200B;オプションについて詳しくは、「アプリのカスタマイズ」を参照してください。

* 統合ツール。 統合ツールを使用してメディアウォールをカスタマイズする方法については、[メディアウォールの統合](/help/implementation/c-app-integrations/c-media-wall-integration.md)を参照してください。

