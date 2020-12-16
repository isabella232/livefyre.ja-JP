---
description: Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。
seo-description: Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。
seo-title: 安全なルール
title: 安全なルール
uuid: 2f91d0d4-dffe-4651-88af-79bbb96c1b5c
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 0%

---


# 安全なルール{#safe-rules}

Livefyre Spam and Avuse Filtering Engine(SAFE)は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyreユーザーに対して有効になります。



SAFEでは、スパム、違反、不敬、およびバルク（繰り返し）投稿を検出するために、パターンルールと統計モデルを使用します。 他のLivefyre製品（コンテンツモデレートツールやModQなど）では、時折参照されます。

>[!NOTE]
>
>SAFEは英語のみです。ただし、一括メールの分類は例外です。 他の言語のサポートが必要な場合は、戦略的アカウントマネージャーにお問い合わせください。

## SAFEを使用するStudioコンポーネント{#section_k34_4tx_vy}

SAFEで適用されるフラグは、次のStudioコンポーネントで使用できます。

* ルール

   **[!UICONTROL Network Settings]**&#x200B;内でコンテンツに自動的にフラグを付け、フラグ付けされたコンテンツの処理方法を定義するSAFEルールを定義できます。

   例えば、サイトで不敬の許容度を非常に低く設定し、プロファンとしてフラグ付けされたすべてのコンテンツをボゾとして設定するセーフルールを定義できます。他のサイトでは、ストリームに入る前にプロファイルのコンテンツを事前にモデレートするように設定するルールを定義できます。

* ModQ

   ModQでは、SAFEルールによってフラグ付けされたコンテンツや、その他のモデレート前のルール（スパム、不敬など）をモデレートできます。

* ライブラリ内のアプリコンテンツ

   SAFEによってフラグ付けされたコンテンツは、**[!UICONTROL Library]**&#x200B;タブのアプリのコンテンツに一覧表示されます。 コンテンツをフラグでフィルターして、コンテンツをモデレートできます。

## 安全なフィルタオプション{#section_pg5_ttx_vy}

SAFEは、フィルターを適用したコンテンツに次のフラグを適用します。このフラグを使用して、Livefyre Studio内からルールの作成やコンテンツのモデレートを行うことができます。

* **[!UICONTROL Profanity List]**:一般的な使用法に基づき、英語のリストで定義されるプロファイルのコンテンツ。

   不敬な言葉遣いのフィルターは、テストした単語のリストに基づいて不敬な言語を探します。 検出された場合、コンテンツにはプロファイルというフラグが付けられます。

   >[!NOTE]
   >
   >また、Livefyreには、2つ目の不敬なリストフィルターも用意されており、これはサイトレベルとネットワークレベルの両方でカスタマイズできます。 不敬のリストを使用して作成されたルールは、「不敬の言葉を使用しない」フィルターに由来する自動ルールよりも優先されます。 詳しくは、設定ドキュメントの「不敬なリスト」の節を参照してください。

* **[!UICONTROL Mild Profanity]**:一般的に礼儀正しい会話では受け入れられない単語やフレーズですが、通常、気軽な会話では受け入れられます。一般に、これらの語句はネットワークテレビで許可されます。
* **[!UICONTROL Strong Profanity]**:ネットワークテレビでは許されない、R評価映画や成熟したケーブルテレビ番組ではあまり使われないような非常に強い言語。一般的には礼儀正しい会話や気軽な会話では使われず、聞き手を傷つけようという不敬な会話の中で言われる。
* **[!UICONTROL SPAM]**:非請求、通常は商用コンテンツ。これは、様々な機能（コメントの内容やURLなど）に依存する統計モデルを使用して、コンテンツの一部をスパムとしてフラグ付けします。 スパムのしきい値を調整して、要求に応じて、ネットワークやサイトのスパムタグ付け率をカスタマイズできます。
* **[!UICONTROL Mild Insult]**:キーワードとフレーズパターンのリストで定義される、コンテンツの侮蔑。
* **[!UICONTROL Strong Insult]**:キーワードとフレーズパターンのリストで定義される、コンテンツの侮蔑。
* **[!UICONTROL Hate Speech]**:民族や宗教に基づく侮辱、特にターゲットグループの認知が少数派または保護されている場合の侮辱。
* **[!UICONTROL ALL CAPS]**:すべての大文字で表示されるテキスト（「キャリング」と読み上げられます）。
* **[!UICONTROL Mild Threat]**:他の人に対する軽い不敬な言葉を含む脅威または侮辱。このオプションは、可能性のある脅威により頻繁にフラグを付けますが、**[!UICONTROL Strong Threat]**&#x200B;よりも偽陽性率が高くなります。

* **[!UICONTROL Strong Threat]**:1人または複数の人々に対して、対抗可能な身体上の害について言及する重大な脅威または侮辱で、しばしば不敬の言葉を浴びせます。このオプションは、脅威に対するフラグの頻度を下げますが、**[!UICONTROL Mild Threat]**&#x200B;よりも偽陽性率が低くなります。

* **[!UICONTROL Probable Nudity]**:ヌードを含む可能性のある画像。このオプションは、ヌードに対するフラグ付けの頻度は低くなりますが、偽陽性率も&#x200B;**[!UICONTROL Possible Nudity]**&#x200B;より低くなります。

* **[!UICONTROL Possible Nudity]**:ヌードを含む可能性のある画像。このオプションは、ヌードに対してより頻繁にフラグを付けますが、**[!UICONTROL Probable Nudity]**&#x200B;よりも偽陽性率が高くなります。

* **[!UICONTROL PII]** （個人を特定できる情報）:ユーザーを識別できる情報。例えば、電子メールアドレス、住所、社会保障番号（米国のお客様の場合）、クレジットカード番号、パスワードなど、詐欺や身元の特定に使用できる情報を入力できます。
* **[!UICONTROL Livefyre Recommends Trash]**&#x200B;をインストールします。自動モデレートレコメンデーションで拒否の対象となるコンテンツが識別される場合に、システムが実行するアクションを設定します。 ![](assets/mod_reco1.png)

   >[!NOTE]
   >
   >モデレートRecommendationsを有効にするには、AdobeのLivefyreサポート担当者にお問い合わせください。

## SAFEで取得されないコンテンツの処理{#section_pjy_5tx_vy}

このフィルターでキャッチされないコンテンツを効果的に処理する方法はいくつかあります。 次のオプションは、推奨される処理順に示されています。

1. モデレーターとして、ストリームからコンテンツを削除します。
1. 5人のユーザーがコンテンツの一部にスパムまたは不快なフラグを付けた場合に、そのフラグを「Bozo」に設定するように指示するフラグルールを作成します。
1. 不要なコンテンツを投稿しているユーザーを禁止し、そのユーザーのコンテンツがすべて「房蔵」状態に直接移行するようにします。
1. 常に不敬な追加リストに合わせてフィルタする必要のある特定の単語。

>[!NOTE]
>
>モデレーターがスパムフィルターで取得したコンテンツを投稿した場合、そのコンテンツは依然としてスパムとしてフラグ付けされますが、自動的に承認され、「房蔵」に設定されません。

コンテンツのトレンドやパターンがSAFEで取得されない場合は、CSMにコメントIDとテキストを電子メールで送信します。



この機能を使用するアプリ：

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [Comments](/help/using/c-about-apps/c-comments/c-comments.md)
* [機能カード](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Sidenots](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify 2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [アップロードボタン](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)

