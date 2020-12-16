---
description: 顧客の遍歴の特定の時点で製品固有のUGCを提供し、UGCコマース機能を使用して購入意図とコンバージョンを高めます。
seo-description: 顧客の遍歴の特定の時点で製品固有のUGCを提供し、UGCコマース機能を使用して購入意図とコンバージョンを高めます。
seo-title: UGCコマース
solution: Experience Manager
title: UGCコマース
uuid: 71e64901-a2b6-4957-ba88-058e4eaca537
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 2%

---


# UGCコマース{#ugc-commerce}

顧客の遍歴の特定の時点で製品固有のUGCを提供し、UGCコマース機能を使用して購入意図とコンバージョンを高めます。

UGCコマース機能を使用すると、購入意図やコンバージョンにUGCや製品の詳細ページに影響を及ぼすことができます。 UGCと商品在庫とをシームレスに関連付けることで、タイム・トゥ・マーケットを短縮 UGCを使用してコミュニティを作成し、真の顧客層を強調することでブランド忠誠度を高めます。

AEM Livefyreには、SKU、サムネール画像、価格、製品名など、製品カタログ情報を読み込む方法がいくつか用意されています。 AEM Livefyreの権限リクエスト、自動ストリームルールタグ付け、およびモデレートワークフローを使用して、製品とUGCの関連付けを簡単に管理できます。

購入に影響するだけでなく、AEM LivefyreのUGCコマース製品の機能を活用して、次のような他の方法でコンバージョンを促進できます。

* B2Bリードジェネレーション：誘い文句(UGC)の下に誘い文句（CTA：コールトゥアクション）ボタンを置いて、リードを捕捉します。
* B2Cアプリのダウンロード：ユーザーにアプリのダウンロードを促す
* 記事の照会：ユーザーをUGCに関連した記事にリンクする

コンバージョンを促すために、製品の誘い文句（CTA：コールトゥアクション）をUGCと並べて配置します。 次のことができます。

* 数千も追加の製品詳細ページに及ぶ製品固有のUGC。
* 製品の詳細ページに、メディアウォールやモザイクなどのUGCコマース機能をサポートするAEM Livefyreのビジュアライゼーションアプリを埋め込みます。
* UGCに配置された製品CTAおよび製品詳細ページに配置されたUGCからのコンバージョンを測定するには、設定可能な参照追跡コードをAnalyticsソリューションと共に使用します。

AEMコマースのユーザーは、既存の製品カタログをLivefyreにシームレスに統合できるので、Livefyreのビジュアライゼーションアプリでユーザーのエンゲージメントを促進できます。 AEMコマースを使用しないLivefyreユーザーは、自分の製品カタログをLivefyreに手動で読み込むことができます。 詳しくは、[ファイルのアップロードを使用したLivefyreへの製品のアップロード](/help/using/c-features-livefyre/c-ugc-commerce.md)を参照してください。

この機能を使用するアプリ：

* [機能カード](../c-about-apps/c-feature-card-app/c-feature-card-app.md#c_feature_card_app)。フィーチャカードでのUGCコマースの使用方法について詳しくは、[機能カードのカスタマイズ](../c-about-apps/c-feature-card-app/c-feature-card-app.md#section_uds_gzm_5y)を参照してください。

* [](../c-about-apps/c-filmstrip-app/c-filmstrip-app.md#concept_jpc_n2j_jbb)をインストールします。フィルムストリップでのUGCコマースの使用方法について詳しくは、[フィルムストリップのカスタマイズ](../c-about-apps/c-filmstrip-app/c-filmstrip-customizations.md#c_filmstrip_customizations)を参照してください。

* [メディアウォール](../c-about-apps/c-media-wall-app/c-media-wall-app.md#c_media_wall_app)。メディアウォールでのUGCコマースの使用方法について詳しくは、[メディアウォールのカスタマイズ](../c-about-apps/c-media-wall-app/r-media-wall-customizations.md#r_media_wall_customizations)を参照してください。

* [モザイク](../c-about-apps/c-mosaic-app/c-mosaic-app.md#c_mosaic_app)。MosaicでのUGCコマースの使用方法について詳しくは、[Mosaic Customizations](../c-about-apps/c-mosaic-app/c-mosaic-customizations.md#c_mosaic_customizations)を参照してください。

## 概要：UGCコマースの誘い文句（CTA：コールトゥアクション）ボタンの使い方{#section_s2d_tln_n1b}

1. 誘い文句（CTA：コールトゥアクション）ボタンを使用したアプリの作成を参照してください。 [アプリ](/help/using/c-features-livefyre/c-call-to-action-button.md#task_36190DD1C8204C7793CB7EEA379C2155)追加への誘い文句（CTA：コールトゥアクション）ボタンを参照してください。
1. Livefyre追加に製品カタログをアップロードします。 コンテンツを読み込む方法は2つあります。

   * [AEMコマースを使用する場合は、AEM ](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html) Commerceを使用して製品をLivefyreに読み込みます。
   * [AEMコマースを使用しない場合は、](/help/using/c-features-livefyre/c-ugc-commerce.md) Livefyrefyに製品をアップロードします。

1. 製品とコンテンツの関連付け これは、次の4つの方法のいずれかで行うことができます。

   * ライブラリから。 [ライブラリを使用した製品とコンテンツの関連付け](../c-library/t-associate-products-with-content-using-the-library.md#t_associate_products_with_content_using_the_library)を参照
   * ModQから [ModQを使用したコンテンツのモデレート](/help/using/c-features-livefyre/c-about-moderation/c-modq.md)を参照
   * アプリのコンテンツから 「[アプリへ追加の誘い文句（CTA：コールトゥアクション）ボタン](/help/using/c-features-livefyre/c-call-to-action-button.md)」を参照
   * ストリームから。 「[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)」を参照してください。

## ファイルのアップロード{#section_n1s_4hz_m1b}を使用したLivefyreへの製品のアップロード

誘い文句（CTA：コールトゥアクション）ボタンで使用する製品をアップロードして、コンテンツに関連付ける製品を追加したり、既存のファイルを編集および削除したりします。

>[!NOTE]
>
>既存のファイルを含むフォルダーにファイルをアップロードすると、そのフォルダー内のすべてのファイルが削除され、新しいファイルで上書きされます。

1. **[!UICONTROL Network Settings > Products.]**&#x200B;に移動
1. **[!UICONTROL Product Folder]**&#x200B;を作成するか、既存の&#x200B;**[!UICONTROL Product Folder]**&#x200B;を使用します。

1. **[!UICONTROL Product Folder]**&#x200B;をクリックして選択します。
1. **[!UICONTROL Upload Products]**&#x200B;ボタンをクリックします。
1. 次のいずれかの形式で製品ファイルをアップロードします。

   * Google Productsファイル形式
   * Livefyre形式（以下を参照）

   標準形式でJSONファイルをアップロードします。 標準形式の例を参照するには、テンプレートをダウンロードします。 テンプレート内の1つの製品ラインの例を次に示します。 `{"key": "value", "key": "value"}, {"key": "value", "key": "value"}`のシーケンスに従います。

   ```
   {"id": "1", "title": "Flex RN 2017", "isFolder": false, "description": "Flex RN 2017", "price": "$85", "sku": "sku11111", "summary": "This brand is a member of the Sustainable Apparel Coalition", "features": "Cushioning: Lightweight, flexible response", "url": "www.shopping.com/shoes-flex-rn-2017/product/9", "attributes": [{"type": "color", "value": "blue"}
   ```

   次の表に、製品をアップロードするために必要なキーと値のペアを示します。

## 商品カタログアップロード標準形式のキー/値のペア

| キー | タイプ | 説明 |
|--- |--- |--- |
| ID | 文字列 | 製品の一意のID。 |
| oembed | オブジェクト | 画像の添付ファイル`0embed $ref: '../partials/schemas.yaml#/oEmbed'` |
| title | 文字列 | 製品のタイトル。 |
| isFolder | ブール値 | trueの場合、製品はフォルダーと同様に扱われます（例えば、男性、女性など）。 |
| parentId | 文字列 | 商品が属するフォルダを定義します。 |
| description | 文字列 | 製品の説明。 |
| price | 文字列 | 商品の価値（ドル）。 例：「23.36」 |
| sku | 文字列 | 製品の在庫保管単位(SKU)。 |
| url | 文字列 | 製品ページへのリンク。 |
| 有効 | ブール値 | 値Trueは、製品がアクティブであることを意味します。 |
| 属性 | 配列 | 製品を定義するタイプと値（色、サイズなど）。 これはオブジェクトの配列です。</br>**プロパティ：** </br>type  </br>Type:</br>StringDescription:色、サイズ </br>値 </br>の種類：文字列 </br>の説明：緑、XS |
| タグ | 配列 | コンテンツのカテゴリ（車、靴など）を定義するタグ。 これは文字列の配列です。 |

## ModQ {#section_os1_v4t_n1b}

既存のモデレートワークフローに従って、ModQで商品カタログのコンテンツを商品に関連付けることができます。 ModQでのUGCコマースの使い方については、[ModQを使用したコンテンツのモデレート](/help/using/c-features-livefyre/c-about-moderation/c-moderate-content-using-app-content.md)を参照してください。

## ストリーム{#section_qtj_v4t_n1b}

ストリームルールを使用して製品をコンテンツに自動的に関連付け、コンテンツを自動的にアプリに発行し、ライブラリに保存するか、ModQを使用してモデレートできます。 UGCコマースとストリームルールの使用方法の詳細については、[Stream Rule Options for All Stream Rules](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。
