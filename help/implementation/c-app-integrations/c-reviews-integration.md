---
description: 顧客が製品サービスの評価と確認を許可します。
seo-description: 顧客が製品サービスの評価と確認を許可します。
seo-title: レビュー
solution: Experience Manager
title: レビュー
uuid: b740ee28- f6f9-4ae7-9fe7-61a5cde97bbb
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934

---


# レビュー {#reviews}

顧客が製品サービスの評価と確認を許可します。

レビューによって、コミュニティのメンバーは、製品やサービスの評価や定性的なレビューを行うことができます。

## 統合{#section_kk5_15b_c1b}

レビューアプリを統合するには、「会話アプリの統合」の手順に従います。詳しくは、アプリ [の埋め込み](/help/implementation/c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md)を参照してください。以下に、埋め込まれたレビューアプリケーションの例を示します。

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

"Building `CollectionMeta` 」セクションに記述されているとおり、 `CollectionMeta` エンコードされたJSONオブジェクトです。上記の例では、JSONオブジェクトはJWTエンコード前に次の形式を使用します。

```
{ 
"url": "https://www.directv.com/person/Anna-Paquin-b2FSL0drK3NubWc9-reviews",  
"siteId": "304059",  
"articleId": "sh_col_22_1373478370_reviews",  
"type": "reviews",  
"title": "TB_Paquin_ratings_reviews" 
}
```

## contentConfigオブジェクト {#section_pzv_ytb_c1b}

「はじめに」セクションを既に完了している場合は、envConfigオブジェクトについて理解しておく必要があります。レビューを有効にするには、次のフィールドでGCMを更新します。

* **AlwaysShowEditor***オプション* のブール値:デフォルトでは、レビューエディターはユーザーが「レビューレビュー」ボタンを押すと表示されます。このパラメーターをtrueに設定すると、エディターが常に表示されます。

* **app** *required* string:レビューに使用するアプリ名。「レビュー」である必要があります。

* **defaultSort***オプション* の文字列:レビューのデフォルトの並べ替えオプションを選択できます。使用できる値は次のとおりです。Omcsful、HighestRate、loaded、最新、古い。

* **disableTitle***オプション* のブール値:レビューエディターのタイトルフィールドを無効にして非表示にします。デフォルトでは必須と表示されています。初期設定はtrueです。

* **enableHalfUsingオプション**** のブール値:デフォルトの星形選択モジュールで半分のレーティングを有効にするために使用します。初期設定はtrueです。

* **hideShowReviewButton***オプション* のブール値: [!UICONTROL Show My Review] ボタンを表示するかどうかを制御します。ユーザーが自分のレビューを表示するか表示するかを選択できるようにするには、trueに設定します。

* **maxRate***オプション* の整数:デフォルトのスター選択モジュールに表示される星の数を設定します。初期設定は5です。これは100まで設定できます。

* **ratingSummaryEnabled***オプション* のブール値:レビューアプリの上に評価概要ビューを表示するために使用します。これを有効にするには、LatingSummaryDelegateを使用する必要があります。初期設定はtrueです。

## Review Collection Metadata {#section_k1s_sqb_c1b}

* **type:***必要* な文字列:コレクションタイプを定義します。`reviews`必要です。

* **ratingDimensions***オプション* の配列:このCollectionが使用するディメンションのタイプごとの文字列配列です。指定しない場合、1次元のみ許可されます。

   例えば、ユーザーが「デザイン」、「機能」および「パフォーマンス」で製品を評価できるようにするには、配列を次のように設定します。 `ratingDimensions: [‘design’, ‘features’, ‘performance’]`

* **ratingSubParts***オプション* の整数:レビューのテキストボックスに表示する分割の数。サブパーツラベルは、以下に示すようにパラメーターと共に渡されます。

   >[!NOTE]
   >各サブパーツのラベルを定義する必要があります。

* **ratingSubpartKeys***オプション* の配列:レーティングコレクション内の各サブパーツのIDを定義できます。これは、CSSおよびJavaScriptでこれらのサブパーツ要素をターゲット設定するために使用できます。ユーザーがレビューを投稿すると、それぞれ `ratingSubpart` に「 `data-lf-subpart-id`」属性が含まれ、このIDが入力されます。

>[!NOTE]
>
>これを使用 `ratingSubpartsIds`するには `ratingSubparts` 、パラメーターも定義する必要があり、2つの配列の長さが一致する必要があります。

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
>使用し `ratingDimensions`ている場合は、および `ratingSelectionDelegate`（評価 `ratingDisplayDelegate`概要を `ratingSummaryDelegate` 表示する場合）を使用する必要があります。

## レビューのカスタマイズ {#section_khz_xmb_c1b}

### スター画像の設定

完全な星形の画像を変更するには、クラスです `goog-ratings-star`。背景画像を好きな画像に変更します。デフォルトでは、星は28x28ピクセルです。

### ハーフスターを使用した星の画像の設定

星の半分には、星形の各辺に1つのクラスがあります。半分の星形の左側は `fyre-rating-half-odd` 、右側 `fyre-rating-half-even`です。デフォルトでは、2つの星は28x14ピクセルです。

### 星のツールチップの値の設定

星のツールチップ値を設定するには、「文字列のカスタマイズ」で説明されているカスタムテキストに従ってください。設定が完了したら、ツールチップ文字列を含む配列のキー `ratingValues` と値を使用します。2つの星が無効になっている場合、配列内の要素数は（上の）と `maxRating` 同じにする必要があります。星の数が半分の場合、要素数は2x `maxRating`になります。配列の最初の要素は、一番左の星形（または半分の星形）要素に対応し、左から右に続きます。

### 「レビューを表示」オプションの切り替え

オプションの [!UICONTROL Show My Review] オン/オフを切り替えるには、アプリケーション設定の `hideShowReviewButton` パラメーターをターゲットにします。

### テキストエディターをデフォルトで表示

レビューエディターは、ユーザーが [!UICONTROL write review] ボタンを押すと表示されます。デフォルトでこのフォームを表示するには、アプリケーション設定で `alwaysShowEditor` パラメーターをターゲット設定します。
