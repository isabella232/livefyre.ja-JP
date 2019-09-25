---
description: 顧客が製品の評価とレビューを行えるようにします。
seo-description: 顧客が製品の評価とレビューを行えるようにします。
seo-title: レビュー
solution: Experience Manager
title: レビュー
uuid: b740ee28-f6f9-4ae7-9fe7-61a5cde97bb
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934

---


# レビュー {#reviews}

顧客が製品の評価とレビューを行えるようにします。

レビューを使用すると、コミュニティのメンバーは、あらゆる製品やサービスに関して星の評価や定性のレビューを行うことができます。

## 統合 {#section_kk5_15b_c1b}

レビューアプリを統合するには、会話アプリの統合の手順に従います。 詳しくは、ア [プリの埋め込みを参照してください](/help/implementation/c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md)。 次に、埋め込みReviewsアプリの例を示します。

### 例

```
var networkConfig = { 
   network: "client-solutions-uat.fyre.co" 
}; 
  
var convConfig = { 
   siteId: '304059', 
   articleId: 'sh_col_22_1373478370_reviews', 
   el: 'livefyre-comments', 
   app: 'reviews', 
   ratingSummaryEnabled: true, 
   maxRating: 5, 
   collectionMeta: 'eyJhbGciOiAiSFMyNTYiLCAidHlwIjogIkpXVCJ9.eyJ1cmwiOiAiaHR0cDovL3d3dy5kaXJlY3R2LmNvbS9wZXJzb24vQW5uYS1QYXF1aW4tYjJGU0wwZHJLM051YldjOS1yZXZpZXdzIiwgInNpdGVJZCI6ICIzMDQwNTkiLCAiYXJ0aWNsZUlkIjogInNoX2NvbF8yMl8xMzczNDc4MzcwX3Jldmlld3MiLCAidHlwZSI6ICJyZXZpZXdzIiwgInRpdGxlIjogIlRCX1BhcXVpbl9yYXRpbmdzX3Jldmlld3MifQ.hes3KMwygCG-fFDQlkaB-XlxGjW6-iZ68xA4RRGqUl0' 
}; 
  
Livefyre.require(['fyre.conv#3'], function (Review) { 
   new Review(networkConfig, [convConfig], function (reviewWidget) {}); 
   auth.delegate({ 
      login: function (callback) { 
         callback(null,{livefyre:'<userauthtoken>'}); 
      }, 
   }); 
});
```

「Building」の節で説明したように、はエ `CollectionMeta` ンコードさ `CollectionMeta` れたJSONオブジェクトです。 上の例では、JSONオブジェクトはJWTエンコードされる前に次の形式をとります。

```
{ 
"url": "https://www.directv.com/person/Anna-Paquin-b2FSL0drK3NubWc9-reviews",  
"siteId": "304059",  
"articleId": "sh_col_22_1373478370_reviews",  
"type": "reviews",  
"title": "TB_Paquin_ratings_reviews" 
}
```

## convConfigオブジェクト {#section_pzv_ytb_c1b}

「はじめに」の節を既に完了している場合は、convConfigオブジェクトについて理解しておく必要があります。 レビューを有効にするには、次のフィールドでconvConfigを更新します。

* **alwaysShowEditorオプション***のboolean* :デフォルトでは、レビューエディターは、ユーザーが「レビューを書き込み」ボタンを押した後にのみ表示されます。 常にエディターを表示するには、このパラメーターをtrueに設定します。

* **app** required ** string:レビューに使用するアプリ名です。 「レビュー」にする必要があります。

* **defaultSortオプシ** ョン ** 文字列：レビューのデフォルトの並べ替えオプションを選択できます。 使用可能な値は次のとおりです。mostHenveled、highestRated、lowestRated、newestおよびorest。

* **disableTitleオプシ** ョン ** boolean:レビューエディターのタイトルフィールドの有効/無効を切り替えます。デフォルトでは必須で表示されます。 初期設定は true です。

* **enableHalfRatingオプション***のboolean* :デフォルトの星選択モジュールで、レーティングの半分を有効にするために使用します。 初期設定は true です。

* **hideShowReviewButtonオプション***のboolean* :ボタンを表示す [!UICONTROL Show My Review] るかどうかを制御します。 ユーザーが自分のレビューを表示するか表示するかを選択できるようにするには、trueに設定します。

* **maxRating** optional ** integerデフォルトの星選択モジュールに表示する星の数を設定するために使用します。 デフォルトは 5 です。これは最大100個まで設定できます。

* **ratingSummaryEnabledオプション***のboolean* :レビューアプリの上に評価の概要ビューを表示するために使用します。 ratingSummaryDelegateを使用するには、これを有効にする必要があります。 初期設定は true です。

## コレクションのメタデータの確認 {#section_k1s_sqb_c1b}

* **** type:必 *須文字列* :コレクションの種類を定義します。 必ず `reviews`。

* **ratingDimensionsオプショ** ンの配列 ** :このコレクションで使用するディメンションのタイプごとの文字列の配列です。 これを指定しない場合は、1つのディメンションのみが許可されます。

   例えば、ユーザーが製品を「デザイン」、「機能」、「パフォーマンス」に評価できるようにするには、アレイを次のように設定します。 `ratingDimensions: [‘design’, ‘features’, ‘performance’]`

* **ratingSubparts** optional ** integer:レビューのテキストボックスに表示するパーティションの数。 下図に示すように、サブパーツのラベルはパラメータと共に渡されます。

   >[!NOTE]
   >各サブパーツのラベルを定義する必要があります。

* **ratingSubpartsIdsオプショ** ンの配 ** 列：評価コレクション内の各サブパーツのIDを定義できます。このIDは、CSSおよびJavaScriptでこれらのサブパーツ要素をターゲットにするために使用できます。 ユーザーがレビューを投稿す `ratingSubpart` ると、それぞれに「 `data-lf-subpart-id`」属性が付き、このIDが設定されます。

>[!NOTE]
>
>を使用する `ratingSubpartsIds`には、パ `ratingSubparts` ラメータも定義し、2つの配列の長さが一致する必要があります。

```
networkConfig["strings"] = { 
   ratingSubpartPlaceholders: ['Pros...', 'Cons...'], 
   ratingSubpartTitles: ['Pros:', 'Cons:'], 
   ratingSubpartIds: ['pros', 'cons'], 
   reviewStreamTitle: 'Description:' 
} 
fyre.conv.load(networkConfig, [{ 
   app: 'reviews', 
   ratingSubparts: 2, 
    ... // More conv config settings 
}]);
```

>[!NOTE]
>
>を使用している場合は、、 `ratingDimensions`およびを使用する必要があります( `ratingSelectionDelegate`レ `ratingDisplayDelegate`ーテ `ratingSummaryDelegate` ィングの概要を表示する場合は、を使用する必要があります)。

## レビューのカスタマイズ {#section_khz_xmb_c1b}

### スター画像の設定

星全体の画像を変更する場合、クラスはです `goog-ratings-star`。 背景画像を任意の画像に変更します。 デフォルトでは、星は28 x 28ピクセルです。

### 星形（半分）の画像の設定

星は半分で、星の両側に1つずつ、2つのクラスがあります。 ハーフスターの左 `fyre-rating-half-odd` 辺は右辺は `fyre-rating-half-even`。 初期設定では、半星は28 x 14ピクセルです。

### 星のツールチップ値の設定

星のツールチップ値を設定するには、「文字列のカスタマイズ」で説明されているカスタムテキストに従います。 設定が完了したら、キーと値、およびツールチッ `ratingValues` プ文字列を含む配列を使用します。 ハーフスターを無効にした場合、配列内の要素数は上記と同じにする必要 `maxRating` があります。 「半星」を有効にしている場合、要素の数は2倍にする必要がありま `maxRating`す。 配列の最初の要素は、一番左の星（または半星）要素に対応し、左から右に続きます。

### 「レビューを表示」オプションを切り替える

このオプションのオ [!UICONTROL Show My Review] ン/オフを切り替えるには、アプリ設定でパラメ `hideShowReviewButton` ーターをターゲットにします。

### デフォルトでテキストエディターを表示

レビューエディターは、ユーザーがボタンを押した後にのみ表示さ [!UICONTROL write review] れます。 デフォルトでこのフォームを表示するには、アプリ設定でパラメ `alwaysShowEditor` ーターをターゲットにします。
