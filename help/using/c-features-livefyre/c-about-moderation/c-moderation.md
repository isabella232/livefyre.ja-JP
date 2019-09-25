---
description: Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。
seo-description: Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。
seo-title: セーフルール
title: セーフルール
uuid: 2f91d0d4-dffe-4651-88af-79bb96c1b5c
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# セーフルール{#safe-rules}

Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。



SAFEは、スパム、違法行為、不敬な言葉遣い、およびバルク（繰り返し）投稿を検出するために、パターンルールと統計モデルを使用します。 他のLivefyre製品（特にコンテンツモデレートツールやModQ）では、これらのコンテンツが時折参照されます。

>[!NOTE]
>
>SAFEは英語のみです。ただし、一括メールの分類は例外です。 その他の言語のサポートが必要な場合は、戦略的アカウントマネージャーにお問い合わせください。

## SAFEを使用するStudioコンポーネント {#section_k34_4tx_vy}

SAFEによって適用されるフラグは、以下のStudioコンポーネントで使用できます。

* ルール

   SAFEルールを定義して、コンテンツに自動的にフラグを付けたり、でのフラグ付けされたコンテンツの処理方法を定義したりできま **[!UICONTROL Network Settings]**&#x200B;す。

   例えば、サイトで不敬の言葉に対する許容度を非常に低く設定し、不敬のフラグを付けたすべてのコンテンツをボゾのデザインとして設定するSAFEルールを定義するとします。他のサイトでは、ストリームに入る前にプロファイルのコンテンツを事前にモデレートするように設定するルールを定義する場合があります。

* ModQ

   SAFEルールによってフラグ付けされたコンテンツや、その他のモデレート前のルール（例えば、スパム、不敬な言葉遣いなど）をModQでモデレートできます。

* ライブラリ内のアプリコンテンツ

   SAFEでフラグ付けされたコンテンツは、タブの「アプリのコンテンツ」に表示さ **[!UICONTROL Library]** れます。 コンテンツをフラグでフィルターして、コンテンツをモデレートできます。

## SAFEフィルタオプション {#section_pg5_ttx_vy}

SAFEは、フィルターされたコンテンツに次のフラグを適用します。このフラグを使用して、Livefyre studio内からルールを作成し、コンテンツをモデレートできます。

* **[!UICONTROL Profanity List]**:一般的な使用に基づく、英語のキーワードのリストで定義されるプロファイルコンテンツ。

   不敬な言語フィルターは、テストされた単語リストに基づいて不敬な言語を探します。 検出された場合、コンテンツにはProfanceというフラグが付けられます。

   >[!NOTE]
   >
   >また、Livefyreには、サイトレベルとネットワークレベルの両方でカスタマイズできる、不敬なリストフィルターも用意されています。 「不敬な言葉」リストで作成されたルールは、「不敬な言葉」フィルターに由来する自動化されたルールよりも優先されます。 詳しくは、設定ドキュメントの「不敬な言葉のリスト」の節を参照してください。

* **[!UICONTROL Mild Profanity]**:丁寧な会話では一般的に受け入れられないが、普段の会話では受け入れられる言葉やフレーズ。 一般に、これらの語句はネットワークテレビで許可されます。
* **[!UICONTROL Strong Profanity]**:ネットワークテレビでは許されない、R評価映画や成熟したケーブルテレビ番組では控えめに使われるなど、非常に強い言語。 一般に、これらの言葉は礼儀正しい会話や気まぐれな会話には使われず、聞き手を傷つける目的で失礼な会話の中で言われます。
* **[!UICONTROL SPAM]**:非要請、通常は商用コンテンツ。 このモデルは、様々な機能（コメントの内容やURLなど）に依存して、一部のコンテンツにスパムのフラグを付ける統計モデルを使用します。 スパムのしきい値を調整して、要求に応じて、ネットワークまたはサイトのスパムタグ付け率をカスタマイズできます。
* **[!UICONTROL Mild Insult]**:キーワードとフレーズのパターンのリストで定義されるコンテンツの侮辱。
* **[!UICONTROL Strong Insult]**:キーワードとフレーズのパターンのリストで定義されるコンテンツの侮辱。
* **[!UICONTROL Hate Speech]**:民族や宗教に基づく侮辱、特にターゲットグループの認知が少数派または保護されている場合。
* **[!UICONTROL ALL CAPS]**:すべての大文字で表示されるテキスト（「エル」として読み上げられます）。
* **[!UICONTROL Mild Threat]**:他の人に向けられた軽い言葉を含む脅しまたは侮辱。 このオプションは、可能性のある脅威により頻繁にフラグを付けますが、偽陽性率も高くなりま **[!UICONTROL Strong Threat]**&#x200B;す。

* **[!UICONTROL Strong Threat]**:1人以上の人々に対して、違法な身体的被害を言及する重大な脅威または侮辱。しばしば、不敬な言葉を使います。 このオプションは、潜在的な脅威に対するフラグの頻度を下げますが、偽陽性率もより低くなりま **[!UICONTROL Mild Threat]**&#x200B;す。

* **[!UICONTROL Probable Nudity]**:ヌードを含む画像。 このオプションは、ヌードに対するフラグ付けの頻度を下げますが、偽陽性率も低くなりま **[!UICONTROL Possible Nudity]**&#x200B;す。

* **[!UICONTROL Possible Nudity]**:ヌードを含む画像。 このオプションはヌードにより頻繁にフラグを付けますが、偽陽性率も高くなりま **[!UICONTROL Probable Nudity]**&#x200B;す。

* **[!UICONTROL PII]** （個人を特定できる情報）:ユーザーを識別できる情報。 電子メールアドレス、住所、社会保障番号（米国のお客様の場合）、クレジットカード番号、パスワード、詐欺や身元の確認に使用できるものなどが含まれます。
* **[!UICONTROL Livefyre Recommends Trash]**. 自動モデレートレコメンデーションで拒否の対象となるコンテンツが識別された場合にシステムが実行するアクションを設定します。  ![](assets/mod_reco1.png)

   >[!NOTE]
   >
   >モデレートのレコメンデーションを有効にするには、Adobe Livefyreサポート担当者にお問い合わせください。

## SAFEで取得されないコンテンツの処理 {#section_pjy_5tx_vy}

このフィルターで取得されないコンテンツを効果的に処理する方法はいくつかあります。 以下のオプションは、推奨される処理の順序で一覧表示されます。

1. モデレーターとして、ストリームからコンテンツを削除します。
1. 5人のユーザーがコンテンツの一部にスパムまたは不快のフラグを付けた場合に、そのフラグを「Bozo」に設定するフラグルールを作成します。
1. 不要なコンテンツを投稿しているユーザーを禁止して、すべてのコンテンツが直接Bozo状態になります。
1. 常に不敬な言葉のリストにフィルターする特定の単語を追加します。

>[!NOTE]
>
>モデレーターがスパムフィルターで取得したコンテンツを投稿した場合、そのコンテンツはスパムとしてフラグ付けされますが、自動的に承認され、ボゾに設定されません。

コンテンツのトレンドやパターンがSAFEで捕捉されない場合は、CSMにコメントIDとテキストを電子メールで送信します。



この機能を使用するアプリ：

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [サイデン](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [アップロードボタン](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)

