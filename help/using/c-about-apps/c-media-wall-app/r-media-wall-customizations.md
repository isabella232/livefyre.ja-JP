---
description: Media wallアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-description: Media wallアプリのサイズ、幅およびインタラクションオプションを変更します。
seo-title: メディアウォールのカスタマイズ
solution: Experience Manager
title: メディアウォールのカスタマイズ
uuid: 79aecd92-3937-4bb4-a1a6-b090fb39afb0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# メディアウォールのカスタマイズ{#media-wall-customizations}

Media wallアプリのサイズ、幅およびインタラクションオプションを変更します。



Media wallは、ライブ画像やその他のコンテンツをリアルタイムのソーシャルウォールにストリーミングし、イベントを取り巻くすべてのアクティビティを視覚化します。

有効にすると、ユーザーはテキスト、画像またはビデオを直接このアプリに投稿できます。 サポートされるファイル形式を次に示します。

* 画像：JPEG、GIF、PNG
* ビデオ：Quicktime/MOV、MP4、MPEG、WebM
* オーディオ：WAV、WAVE、X-MS-WMA、FLAC、OGG、MPEG

* **[!UICONTROL Items to load]**

   表示するコンテンツアイテムの初期数を設定します。

* **[!UICONTROL Load content with animation.]** このオプションをオンにすると、アニメーションを含むページにメディアウォールが読み込まれます。 このオプションをオフにすると、アニメーションを使用せずにページにメディアウォールが読み込まれます。
* **[!UICONTROL Number of columns.]** メディアウォールの列数を設定 列数は、ウィンドウやブラウザのサイズに関係なく同じままです。 「自動」を選択すると、列数が画面サイズに合わせて最適化された列数に合わせて調整されます。
* **[!UICONTROL Fit content to width]**. このオプションをオフにすると、コンテンツは四角形にトリミングされます。 このオプションをオンに切り替えると、カード全体を占めるかどうかに関係なく、カードに画像全体が表示されます。
* **[!UICONTROL Include content modal]**

   ストリーム内の写真をクリックして、オーバーレイされたポップアップウィンドウで開くことができます。

* **[!UICONTROL Require rights]**. 権限要求のステータスが「許可済み」のコンテンツのみを表示する場合は、このオプションを有効にします。
* **[!UICONTROL Hide social branding when rights granted]** このオプションをオンにすると、コンテンツに対する権限が付与されたときに、元のソーシャルメディアネットワーク（TwitterまたはInstagram）のロゴが削除されます。

* **[!UICONTROL Upload Button]**

   * **[!UICONTROL Allow user posts]**. アップロードボタンを使用したテキスト、写真またはビデオの投稿をユーザーに許可するかどうかを選択します。
   * **[!UICONTROL Require Media]**. オンに切り替えて、「アップロード」ボタンを使用して写真またはビデオのコンテンツのみをアップロードするようにユーザーに求めます。
   * 次の「アップロードボタン」フィールドのデフォルトテキストを編集できます。

      * **[!UICONTROL Upload Button Text]**. 「アップロード」ボタンのテキスト。 デフォルトのテキストは「何を考えていますか？」です。
      * **[!UICONTROL Comment Modal Title]**. コンテンツの投稿に使用するモーダルサイト訪問者のタイトル。 デフォルトのテキストは「コメントを投稿」です。
      * **[!UICONTROL Comment Modal Button]**. ボタンサイトの訪問者がクリックしてコンテンツを投稿するテキスト。 デフォルトのテキストは「コメントを投稿」です。

* **[!UICONTROL Call-to-action button]** 商品カタログに対して「誘い文句（CTA：コールトゥアクション）」ボタンを使用すると、ユーザーを商品やサイトに誘導して、さらなるアクションを実行できます。

   * **[!UICONTROL Call-to-action button]** トグルをオンに切り替えて、「誘い文句（CTA：コールトゥアクション）」ボタンを表示します。
   * **[!UICONTROL Require rights to display products]** オンに切り替えると、コンテンツに対して誘い文句（CTA：コールトゥアクション）ボタンが表示される前に、コンテンツ所有者がコンテンツに対する権限を付与する必要があります。

      >[!NOTE]
      >
      >コンテンツに対する権限が付与されていない場合でも、コンテンツは表示されますが、コンテンツに対する権限が付与されていない限り、「誘い文句（CTA：コールトゥアクション）」ボタンはコンテンツと共に表示されません。

   * **[!UICONTROL Call-to-action header text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンの上のヘッダーに表示する単語。 デフォルトの言い回しは「次の製品を購入する：」です。
   * **[!UICONTROL Call-to-action button text]** コンテンツモーダルの誘い文句（CTA：コールトゥアクション）ボタンに表示する単語。 デフォルトのテキストは「Buy Now:」です。
   * **[!UICONTROL Product display options]** 写真と製品名を「誘い文句（CTA：コールトゥアクション）」ボタンと共に表示するかどうかを選択します。

      >[!NOTE]
      >
      >「写真」ボタンと「製品名」ボタンが有効な場合は、両方とも青色でハイライト表示されます。

   * **[!UICONTROL Product URL referral tracking]** 切り替えをオンにして、このアプリから関連製品ページへのリファラルを追跡します。
   * **[!UICONTROL Referral tracking key-value pairs]** 関連する製品ページに、アプリのコンテンツからの参照追跡をさらに指定するパラメーターを追加します。

* **[!UICONTROL Product page filter]**.
   * **[!UICONTROL Filter UGC by Product ID]**. 複数の製品ページに対して1つのアプリを作成する場合は、このオプションを選択します。 製品固有のUGCを、各製品ページでアプリにフィルターします。 1つ以上のフォルダーを選択して、特定のコレクションをアプリに関連付けることができます。
   * **[!UICONTROL Select Product folders]**. UGCのフィルターに使用する最上位の製品フォルダーを選択します。 複数のフォルダを選択するには、CtrlキーまたはCommandキーを押しながらクリックします。 Livefyreは、このフォルダーを使用して、そのフォルダー内のどの製品を様々なページのアプリに表示するかを決定します。
   * **[!UICONTROL Show related content]**. これを切り替えて、アプリに投稿したコンテンツを、異なる製品IDでタグ付けして表示します。 アプリの製品固有のコンテンツが表示された後、Livefyreは他の製品のコンテンツと、製品に関連付けられていないコンテンツを表示します。 Livefyreは、最初に同じ製品IDを持つコンテンツを優先し、次に他の製品IDを持つアプリにコンテンツを公開し、次に製品IDを持たないアプリにコンテンツを公開します。

メディアウォールは、次を使用してカスタマイズできます。

* **[!UICONTROL Style]** 」と「」 **[!UICONTROL Config]** のすべてのアプリに対するオプションを追加しま **[!UICONTROL App Designer]**&#x200B;す。 の標準およびすべてのアプリのオプションについて詳しくは、ア **[!UICONTROL Style]** プリのカ **[!UICONTROL Config]** スタマイズを参照してくださ **[!UICONTROL App Designer]**&#x200B;い。

* 統合ツール。 統合ツー [ルを使用してメディアウォールをカスタマイズする方法について詳しくは、「メディアウォールの統合](/help/implementation/c-app-integrations/c-media-wall-integration.md) 」を参照してください。

