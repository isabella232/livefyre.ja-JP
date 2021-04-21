---
description: お客様が製品の評価やレビューを行えるようにします。
title: レビュー
exl-id: 2f10646e-59c4-459c-ae1b-749f951a06d2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 1%

---

# レビュー{#reviews}

お客様が製品の評価やレビューを行えるようにします。

レビューを使用すると、コミュニティのメンバーは、あらゆる製品やサービスに関する評価や定性評価に貢献できます。

## 統合 {#section_kk5_15b_c1b}

レビューアプリを統合するには、会話アプリの統合の手順に従います。 [アプリを埋め込む](/help/implementation/c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md)を参照してください。 次に、埋め込みレビューアプリの例を示します。

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

「`CollectionMeta`の構築」の節で説明したように、`CollectionMeta`はエンコードされたJSONオブジェクトです。 上記の例では、JSONオブジェクトはJWTエンコードされる前に次の形式を取ります。

```
{ 
"url": "https://www.directv.com/person/Anna-Paquin-b2FSL0drK3NubWc9-reviews",  
"siteId": "304059",  
"articleId": "sh_col_22_1373478370_reviews",  
"type": "reviews",  
"title": "TB_Paquin_ratings_reviews" 
}
```

## convConfigオブジェクト{#section_pzv_ytb_c1b}

「はじめに」の節の内容がすでに完了している場合は、convConfigオブジェクトについて理解しておく必要があります。 レビューを有効にするには、convConfigを次のフィールドに更新します。

* **** ** alwaysShowEditoroptionalboolean:デフォルトでは、レビューエディタはユーザーが「書き込みレビュー」ボタンを押した後にのみ表示されます。このパラメーターをtrueに設定すると、常にエディターが表示されます。

* **** ** apprequiredstring:レビューに使用するアプリ名です。「reviews」にする必要があります。

* **** ** defaultSortoptionalstring:「レビュー」のデフォルトの並べ替えオプションを選択できます。使用できる値は次のとおりです。mostHelved、highestRated、lowestRated、newest、olestの順に並べ替えます。

* **disableTitleoptionalboolean:** ** レビューエディターのタイトルフィールドの有効/無効を切り替えます。デフォルトでは必須で表示可能です。初期設定は true です。

* **enableHalfRatingoptionalboolean** ** :デフォルトの星選択モジュールで半分の評価を有効にするために使用します。初期設定は true です。

* **hideShowReviewButtonoptionalboolean** ** :ボ [!UICONTROL Show My Review] タンを表示するかどうかを制御します。自分のレビューを表示するか表示するかをユーザーが選択できるようにするには、trueに設定します。

* **maxRatingoptionalintegerデフォルトの星選択モジュールに表示される星の数を設定するために使用します。** ** デフォルトは 5 です。これは、最大100個まで設定できます。

* **** ** ratingSummaryEnabledoptionalboolean:レビューアプリの上に評価概要表示を表示するために使用します。ratingSummaryDelegateを使用するには、これを有効にする必要があります。 初期設定は true です。

## コレクションメタデータのレビュー{#section_k1s_sqb_c1b}

* **type:** ** requiredstring:コレクションの種類を定義します。`reviews`にする必要があります。

* **** ** ratingDimensionsoptionalarray:このコレクションで使用するディメンションのタイプごとの文字列の配列です。これを指定しない場合、1つのディメンションのみが許可されます。

   例えば、ユーザーが「design」、「features」、「performance」に対して製品の評価を行えるようにするには、アレイを次のように設定します。`ratingDimensions: [‘design’, ‘features’, ‘performance’]`

* **** ** ratingSubpartionalinteger:レビューのテキストボックスに表示するパーティションの数。サブパーツのラベルは、次の図に示すように、パラメータと共に渡されます。

   >[!NOTE]
   >各サブパーツのラベルを定義する必要があります。

* **** ** ratingSubpartsIdsoptionalarray:評価コレクションの各サブパーツに対してIDを定義できます。IDは、CSSやJavaScriptでこれらのサブパーツ要素をターゲットするのに使用できます。ユーザーがレビューを投稿すると、各`ratingSubpart`には「`data-lf-subpart-id`」属性が割り当てられ、このIDが設定されます。

>[!NOTE]
>
>`ratingSubpartsIds`を使用するには、`ratingSubparts`パラメータも定義する必要があり、2つの配列の長さは一致する必要があります。

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
>`ratingDimensions`を使用する場合は、`ratingSelectionDelegate`、`ratingDisplayDelegate`、`ratingSummaryDelegate`を使用する必要があります（評価概要を表示したい場合）。

## レビューのカスタマイズ{#section_khz_xmb_c1b}

### スター画像の設定

星全体のイメージを変更する場合、クラスは`goog-ratings-star`です。 背景画像を任意の画像に変更します。 デフォルトでは、星は28 x 28ピクセルです。

### 星形の半分の星を使用した星形画像の設定

星の数が半分の場合、星の両側に1つずつ、2つのクラスがあります。 ハーフスターの左辺は`fyre-rating-half-odd`、右辺は`fyre-rating-half-even`です。 初期設定では、半星は28 x 14ピクセルです。

### 星のツールチップ値を設定

星のツールチップ値を設定するには、「文字列のカスタマイズ」で説明されているカスタムテキストに従います。 設定が完了したら、キー`ratingValues`と値、およびツールチップ文字列を含む配列を使用します。 ハーフスターを無効にした場合、配列内の要素数は`maxRating` （上記）と同じにする必要があります。 ハーフスターを有効にしている場合、要素数は2x `maxRating`にする必要があります。 配列の最初の要素は、一番左の星（または半星）要素に対応し、左から右に続きます。

### 「レビューを表示」オプションを切り替える

[!UICONTROL Show My Review]オプションのオン/オフを切り替えるには、アプリ設定で`hideShowReviewButton`パラメーターをターゲットします。

### デフォルトでテキストエディタを表示

レビューエディターは、ユーザーが[!UICONTROL write review]ボタンを押した後にのみ表示されます。 デフォルトでこのフォームを表示するには、アプリ設定で`alwaysShowEditor`パラメーターをターゲットします。
