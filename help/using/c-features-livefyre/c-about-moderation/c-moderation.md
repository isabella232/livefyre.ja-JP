---
description: Livefyreスパムおよび不正行為フィルタリングエンジン（安全）は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyre顧客に対して有効になります。
seo-description: Livefyreスパムおよび不正行為フィルタリングエンジン（安全）は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyre顧客に対して有効になります。
seo-title: セーフルール
title: セーフルール
uuid: 2f91d0d4- dffe-4651-88af-79bbb96c1b5c
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# セーフルール{#safe-rules}

Livefyreスパムおよび不正行為フィルタリングエンジン（安全）は、すべての受信コンテンツを分析するバックグラウンドプロセスで、すべてのLivefyre顧客に対して有効になります。



SAINTでは、パターンルールと統計モデルを使用して、スパム、違反、浪費、および一括（繰り返し）投稿を検出します。これは、他のLivefyre製品（特にコンテンツモデレートツールとMOQ）での時間から時間への参照が表示されます。

>[!NOTE]
>
>安全性は、バルクメールの分類を除き、英語のみです。他の言語のサポートが必要な場合は、戦略的アカウントマネージャーにお問い合わせください。

## セーフによるStudioコンポーネント {#section_k34_4tx_vy}

セーフによって適用されるフラグは、以下のStudioコンポーネントと共に使用できます。

* ルール

   セキュリティルールを定義して、コンテンツに自動的にフラグを付けたり、フラグ付きコンテンツの処理方法を定義 **[!UICONTROL Network Settings]**したりできます。

   例えば、サイトが不敬の許容値を非常に低く設定し、"Proane"としてフラグ付けされたすべてのコンテンツをBoszoとしてフラグ付けする安全なルールを定義するとします。他のサイトでは、ストリームに入る前に、Firefoxコンテンツを事前モデレートするように設定されたルールを定義できます。

* Modq

   MOQ内で、セーフルールによってフラグ付けされたコンテンツや、その他の事前モデレートルール（例えば、スパム、冒涜など）をモデレートできます。

* ライブラリのアプリコンテンツ

   セーフによってフラグ付けされたコンテンツは **[!UICONTROL Library]** 、タブのアプリコンテンツに表示されます。フラグごとにコンテンツをフィルターして、コンテンツをモデレートできます。

## セーフフィルターオプション {#section_pg5_ttx_vy}

SAINTは、フィルターされたコンテンツに次のフラグを適用し、Livefyre Studio内からルールを作成してコンテンツをモデレートするために使用できます。

* **[!UICONTROL Profanity List]**:一般的な用法に基づいて、英語のキーワードのリストによって定義されるプロバンコンテンツ。

   毒言葉フィルターは、テストされた単語リストに基づいて不敬言語を探します。検出された場合、コンテンツにはProaneがフラグ付けされます。

   >[!NOTE]
   >
   >また、Livefyreには2番目のアドホックリストフィルターもあり、サイトレベルとネットワークレベルの両方でカスタマイズできます。不敬リストで作成されたルールは、SAFE浪費フィルターからの自動化されたルールよりも優先されます。詳しくは、設定ドキュメントの「毒文リスト」の節を参照してください。

* **[!UICONTROL Mild Profanity]**:単語とフレーズは通常、適切な会話では許容されませんが、通常、通常の会話で使用できます。一般に、これらの語句はネットワークテレビで使用できます。
* **[!UICONTROL Strong Profanity]**:ネットワークテレビでは許可されず、R検定映画では控えめに使用され、古いケーブルテレビで使用されている、非常に強い言語。一般に、これらの単語は、礼儀的な会話や偶然の会話では使用されず、リスナーに損害を与える意図的な会話とみなされます。
* **[!UICONTROL SPAM]**:説得力のない通常のコンテンツ。コンテンツの一部（コメントコンテンツやURLを含む）に依存する統計モデルを使用して、コンテンツをスパムとしてフラグ付けします。スパムのしきい値を調整して、ネットワークまたはサイトのスパムタグ付け率をリクエスト別にカスタマイズできます。
* **[!UICONTROL Mild Insult]**:キーワードとフレーズのパターンのリストによって定義される、コンテンツの不快化。
* **[!UICONTROL Strong Insult]**:キーワードとフレーズのパターンのリストによって定義される、コンテンツの不快化。
* **[!UICONTROL Hate Speech]**:特にターゲットグループのアフィリエイトが少数または保護されている場合の、人種または宗教に基づく侮辱。
* **[!UICONTROL ALL CAPS]**:すべての大文字に表示されるテキスト。
* **[!UICONTROL Mild Threat]**:通常、ある種のやや厳格な行為を別の人にもたらしている脅威または侮辱。このオプションは、より頻繁に発生する脅威にフラグを付けますが、偽陽性率も高くなり **[!UICONTROL Strong Threat]**ます。

* **[!UICONTROL Strong Threat]**:しばしば強い不敬を持つ1人以上の人に対して、アクション可能な身体の損害をメンションする重大な脅威または侮辱。このオプションは、発生頻度の低い脅威にフラグを付けますが、偽陽性率は低くなり **[!UICONTROL Mild Threat]**ます。

* **[!UICONTROL Probable Nudity]**:ヌードの可能性がある画像。このオプションでは、微妙な頻度は低くなりますが、偽陽性率 **[!UICONTROL Possible Nudity]**は低くなります。

* **[!UICONTROL Possible Nudity]**:ヌードの可能性がある画像。このオプションにより、微妙に除外されますが、偽陽性率 **[!UICONTROL Probable Nudity]**は高くなります。

* **[!UICONTROL PII]** （個人識別情報）:ユーザーを識別できる情報です。これには、電子メールアドレス、住所、社会保障番号（米国のお客様向け）、クレジットカード番号、パスワード、詐欺で使用できる任意の情報、またはユーザーのIDを取得することができます。
* **[!UICONTROL Livefyre Recommends Trash]**. 自動モデレートレコメンデーションがコンテンツを拒否するコンテンツを識別するときに、システムが実行するアクションを設定します。 ![](assets/mod_reco1.png)

   >[!NOTE]
   >
   >モデレートのRecommendationsを有効にするには、Adobe Livefyreのサポートプロフェッショナルにお問い合わせください。

## 保護されていないコンテンツの処理 {#section_pjy_5tx_vy}

このフィルターではキャッチされないコンテンツを効果的に処理するためのいくつかの手段があります。以下のオプションは、推奨されるプロセスの順番に一覧表示されます。

1. モデレーターとして、ストリームからコンテンツを削除します。
1. フラグルールを作成して、コンテンツの一部がスパムとしてフラグ付けされているか、5人のユーザーによる攻撃としてフラグ付けされているかを示すフラグを作成します。
1. 不要なコンテンツを投稿しているユーザーを禁止すると、そのコンテンツはすべてBoszo状態に直接移行します。
1. 常に不敬なリストにフィルターする特定の単語を追加します。

>[!NOTE]
>
>モデレーターがスパムフィルターによって取得されたコンテンツを投稿した場合、そのコンテンツはスパムとしてフラグ付けされますが、自動的に承認され、Boszoには設定されません。

安全でないコンテンツのトレンドやパターンについては、CSMSにコメントIDとテキストを電子メールで送信してください。



この機能を使用するアプリ:

* [カルーセル](/help/using/c-about-apps/c-carousel-app/c-carousel-app.md#c_carousel_app)
* [チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md#c_chat_app)
* [コメント](/help/using/c-about-apps/c-comments/c-comments.md)
* [Feature Card](/help/using/c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)
* [マップ](/help/using/c-about-apps/c-map-app/c-map-app.md#c_map_app)
* [メディアウォール](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)
* [モザイク](/help/using/c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)
* [レビュー](/help/using/c-about-apps/c-reviews-app/c-reviews-app.md#c_reviews_app)
* [Ssiindes](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md#c_sidenotes_app)
* [Storify2](/help/using/c-about-apps/c-storify2/c-storify2.md#c_storify2)
* [アップロードボタン](/help/using/c-about-apps/c-upload-button-app/c-upload-button-app.md#c_upload_button_app)

