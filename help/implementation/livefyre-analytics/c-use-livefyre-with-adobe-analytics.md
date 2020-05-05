---
description: 'null'
seo-description: 'null'
seo-title: LivefyreをAdobe Analyticsと共に使用し、Dynamic Tag Manager(DTM)lk xavvn vefyreをAdobe AnalyticsおよびDynamic Tag Manager(DTM)と共に使用する
uuid: 9a1c25c0-c474-46ff-82ac-e89357007c7f
translation-type: tm+mt
source-git-commit: 573e815799fbae2c2c4f1d98a01ea0ae04108a34

---


# Adobe AnalyticsおよびDynamic Tag Manager(DTM)とLivefyreを使用する{#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Adobe AnalyticsとDynamic Tag Manager(DTM)を設定して、Livefyreアプリのデータを収集します。

## 手順1: Adobe Analyticsでのイベントの設定 {#section_iks_kgd_4cb}

Adobe Analytics Report Suite Managerで、Livefyreイベントを1つ以上のカスタム成功イベントにマッピングします。

Report Suite Managerについて詳しくは、「Report Suite Manager [」を参照してください](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)。

1. 管理者ユーザーとしてAdobe Analyticsにログインします。
1. Adobe Analytics管理者Report Suite Managerを開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックし、に移動して、レポートスイートを編集し **[!UICONTROL Edit Settings > Conversion > Success Events]**&#x200B;ます。
1. Livefyreイベントを1つ以上のカスタム成功イベントーにマップします。

## 手順2: コンバージョン変数の設定

Adobe Analytics管理者Report Suite Managerで、Livefyreコンバージョン変数(eVar)をコンバージョン変数にマップします。 コンバージョン変数は、Livefyreイベントから収集されたデータを識別する方法を決定するための並べ替え関数のような働きをします。

1. 「Report Suite Manager」で、をクリックし **[!UICONTROL Edit Settings > Conversion > Conversion Variables]**&#x200B;ます。
1. 使用するカスタムコンバージョン変数(eVar)を選択し、それらをLivefyreコンバージョン変数にマッピングします。 Livefyreコンバージョン変数をカスタムコンバージョン変数にマップするには：
* コンバージョン変数の有効化
* コンバージョン変数の名前の設定
* コンバージョン変数に型を指定します
1. カスタムコンバージョン変数を保存します。

## 手順3: Livefyreイベントを使用し追加たレポートスイートへのDTMの使用 {#section_t15_2hd_4cb}

追加Adobe AnalyticsからDTMへのアップグレードを参照してください。 これを行うには、新しいプロパティとツールを作成し、Livefyreイベントを含む新しいレポートスイートをプロパティに追加します。 DTMについて詳しくは、「 [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)」を参照してください。

Livefyreイベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合は、この手順を実行する必要はありません。

1. DTMで、既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、 **[!UICONTROL Add a Tool]** ボタンをクリックします。
ツールの次のパラメータを設定します。

   * Set **[!UICONTROL Tool Type]** to **[!UICONTROL Adobe Analytics]**.
   * 有効にする **[!UICONTROL Automatic Configuration]**.
   * 有効にする **[!UICONTROL Authenticate via Marketing Cloud]**.
1. または、フィールドにLivefyreイベントを追加含むレポートスイートの名前を確認し **[!UICONTROL Report Suites]** ます。

## 手順4: Analytics処理を設定するためのページ型ルールの設定 {#section_jfj_j3d_4cb}

ページ型ルールを設定して、すべてのデータを取り込みます。 ページ型ルールを使用すると、ページの読み込み時にイベントを記録するルールにカスタムjavascriptを設定できます。

>[!NOTE]
>
>イベント型ルールやダイレクト型ルールは使用しないでください。

1. DTMで、「 **[!UICONTROL Rules]** tab」を選択します。
1. クリック **[!UICONTROL Page Load Rules]**.
1. ボタンをクリックし **[!UICONTROL Create New Rule]** ます。
1. ボタンをクリックして、 **[!UICONTROL Conditions]** セクションを開き **[!UICONTROL Plus]** ます。
1. ルールをトリガーします。 ルールを非同期に遅延または実装する場合は、タイプ **[!UICONTROL DOM Ready]** を選択または **[!UICONTROL Onload]** トリガーします。
1. （オプション）Livefyre Appsを表示するページを追加制限するための追加のパラメーター。 その他の設定オプションについて詳しくは、「 [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)」を参照してください。
1. の下 **[!UICONTROL Javascript/ Third Party Tags]**&#x200B;で、 **[!UICONTROL Non-sequential]** タブをクリックし、をクリックし **[!UICONTROL Add New Script]**&#x200B;ます。
1. スクリプトの種類 **[!UICONTROL Sequential HTML]** としてを選択します。
1. 次追加のスクリプトをコードエディターに入力し、をクリックし **[!UICONTROL Save Code]**&#x200B;ます。

   次のスクリプトは、Livefyre JavaScriptの読み込み後に `livefyre_analytics` ダイレクト型ルールを呼び出します。 次のスクリプトの例では、がページ上にあるかどうかを400ミリ秒ごとに確認 `livefyre.analytics` します。 ページが読み込まれた後、livefyre.analyticsはトラッキング情報を送信します。

   ```
   /** 
   * Poll for Livefyre.analytics object to exist since it gets loaded via the 
   * Livefyre.js JavaScript file. Depending on the timing, this could already 
   * exist or need a little time. 
   */ 
   function pollForAnalytics() {  
   if (Livefyre.analytics) { 
     _satellite.track('livefyre_analytics'); 
       return true; 
     } 
     setTimeout(pollForAnalytics, 400); 
   } 
   setTimeout(pollForAnalytics, 400);
   ```

1. クリック **[!UICONTROL Save Code]**.
1. クリック **[!UICONTROL Save Rule]**.

## 手順5: LivefyreのAdobe Analyticsマッピング設定を構築するためのダイレクト型ルールの作成 {#section_gvp_b1g_pdb}

カスタムイベント、DTM内のAdobe Analytics UIフィールド、データ要素を使用してLivefyreをDTMと共に実装する方法は他にもあります。 このドキュメントでは、カスタムJavaScriptを使用して同じ効果を実現します。

1. DTMで「 **ルール** 」タブを選択し、「 **直接呼び出しルール**」をクリックします。
1. Click on the **Create New Rule** button.
1. 新しいルールにLivefyre **Analytics**&#x200B;という名前を付けます。
1. 「 **条件** 」設定領域を展開します。
1. 「 **文字列** 」フィールドに、と入力し `livefyre_analytics`ます。
1. 「JavaScript /サードパーティタグ」セクションを展開し、「 **追加新規スクリプト** 」ボタンをクリックします。
1. 「 **タグ名** 」入力ボックスにLivefyre Analytics Config **** と入力します。
1. 「 **非順次JavaScript**」を選択します。
1. 次のLivefyre設定コードをコードエディターに入力し、「コードを **保存** 」ボタンをクリックします。

   ```
   var s = _satellite.getToolsByType('sc')[0].getS(); 
   
   var evarMap = {  
     appId: 'eVar81',  
     appType: 'eVar82' 
   }; 
   
   var eventMap = { 
     FlagCancel: 'event82',  
     FlagClick: 'event82',  
     FlagDisagree: 'event82',  
     FlagOffensive: 'event82',  
     FlagOffTopic: 'event82',  
     FlagSpam: 'event82',  
     Like: 'event82', 
     Load: 'event81',  
     RequestMore: 'event82',  
     ShareButtonClick: 'event82',  
     ShareFacebook: 'event82',  
     ShareOnPostClick: 'event82',  
     ShareTwitter: 'event82',  
     ShareURL: 'event82',  
     SortStream: 'event82',  
     TwitterLikeClick: 'event82', 
     TwitterReplyClick: 'event82',  
     TwitterRetweetClick: 'event82',  
     TwitterUserFollow: 'event82' 
   }; 
   
    function trackLivefyreEvent(data) {  
     var event = eventMap[data.type]; 
     console.log('Track:', data.type, event); 
   
     if (!event) { 
       console.warn(data.type, 'is not mapped   to an event in AA');  
       return; 
     } 
     var vars = ['events'];  
     switch (event) { 
       case 'event82': s.eVar83 = data.type;  
         vars.push('eVar83');  
         break; 
       default: 
     } 
       ['generator', 'evars'].forEach(function (type) {  
       var obj = data[type]; 
       for (var d in obj) { 
         if (obj.hasOwnProperty(d) && evarMap[d]) {  
           s[evarMap[d]] = obj[d];  
           vars.push(evarMap[d]); 
         } 
       } 
     }); 
     s.linkTrackVars = vars.join(',');  
     s.linkTrackEvents = event;  
     s.events = event; 
   
     console.log('linkTrackVars:',  s.linkTrackVars);  
     console.log('linkTrackEvents:',  s.linkTrackEvents);  
     console.log('events:', s.events); 
     s.tl(); 
     } 
     ]
   
     /** 
   ```

   * Livefyreのすべての解析イベント用に解析ハンドラーを追加します。 各イベントに対して、グローバルオブジェクトにデータを設定し、イベントをディスパッチします。

   ```
   */ 
   function addAnalyticsHandler() {  
     Livefyre.analytics.addHandler(function (events) { 
       (events || []).forEach(function (data) {  
         console.log('Event handled:', data.type);  
         trackLivefyreEvent(data); 
       }); 
     }); 
   } 
   addAnalyticsHandler();  
   ```

1. 「ルールを **保存**」をクリックします。

## 手順6: ページ型ルールの変更の承認 {#section_pxc_11t_ycb}

1. 移動先 **[!UICONTROL Approvals]** タブ
1. クリック **[!UICONTROL Approve]**.
1. をクリック **[!UICONTROL Yes, approve]** して、承認を確認します。
1. 移動 **[!UICONTROL Overview > Publish Queue]**.
1. 発行するルールを選択します。
1. クリック **[!UICONTROL Publish Selected]**.
1. をクリック **[!UICONTROL Publish]** して、公開することを確認します。

## script {#section_xkb_vft_mcb}

以下のサンプルコードは、特定のeVarを利用可能なLivefyre eVarにマップしています。 Livefyreコンバージョン変数( `eVar`)名(例えば、 `appId`)は、Report Suite Managerで設定した名前(例えば、 `eVar81`)に対応付けられます。 このスクリプトの `eVar` 名前をカスタムコンバージョン変数に変更します。


```
var s = _satellite.getToolsByType`('sc')[0]`.getS(); 
var evarMap = { 
  appId: 'eVar81', 
  appType: 'eVar82' 
};
```

以下のサンプルコードは、Report Suite Managerで使用可能なLivefyreイベントと共に設定した特定のイベントをマップしています。 この例では、 `event82` はどの種類のユーザーインタラクションイベント（コンテンツの「いいね！」や共有など）を区別しないで、任意のユーザーインタラクションイベントとして設定します。 これは、すべてのユーザインタラクション情報をブロックに記録する効率的な方法です。 また、DTM Analytics UIのイベントを、データ要素の参照を使用してマッピングすることもできます。

```
var eventMap = { 
  FlagCancel: 'event82',  
  FlagClick: 'event82',  
  FlagDisagree: 'event82',  
  FlagOffensive: 'event82',  
  FlagOffTopic: 'event82',  
  FlagSpam: 'event82',  
  Like: 'event82', 
  Load: 'event81',  
  RequestMore: 'event82',  
  ShareButtonClick: 'event82',  
  ShareFacebook: 'event82',  
  ShareOnPostClick: 'event82',  
  ShareTwitter: 'event82',  
  ShareURL: 'event82',  
  SortStream: 'event82',  
  TwitterLikeClick: 'event82', 
  TwitterReplyClick: 'event82',  
  TwitterRetweetClick: 'event82',  
  TwitterUserFollow: 'event82' 
};
```

次のサンプルでは、このリストにイベントがない場合は何もしないでください。 コードのこのセクションを変更する必要はありません。

```
function trackLivefyreEvent(data) {  
  var event = eventMap[data.type]; 
  console.log('Track:', data.type, event); 
   
  if (!event) { 
    console.warn(data.type, 'is not mapped to an event in AA');  
    return; 
  }
```

次のコードは、 `event82` 記録するイベントタイプを区別します。 コンバージョン変数は、ユーザーインタラクションのタイプを `eVar83` 記録し、スクリプトは、ユーザーインタラクションデータをタイプ `eVar83` 別に分けるように設定します。 記録されたデータを特定のタイプのユーザーインタラクションに分割で `eVar83` きます。

```
  var vars = ['events'];  
  switch (event) { 
    case 'event82': s.eVar83 = data.type;  
      vars.push('eVar83');  
      break; 
    default: 
  } 
   
  ['generator', 'evars'].forEach(function (type) {  
    var obj = data[type]; 
    for (var d in obj) { 
      if (obj.hasOwnProperty(d) && evarMap[d]) {  
        s[evarMap[d]] = obj[d];  
        vars.push(evarMap[d]); 
      } 
    } 
  }); 
   
  s.linkTrackVars = vars.join(',');  
  s.linkTrackEvents = event;  
  s.events = event; 
   
  console.log('linkTrackVars:', s.linkTrackVars);  
  console.log('linkTrackEvents:', s.linkTrackEvents);  
  console.log('events:', s.events); 
   
  s.tl(); 
}
```

以下のコードの例では、発生するすべてのイベントをリッスンするハンドラーを追加します。 読み込み時にページ型ルールを使用し、イベントが存在するのを待ち、アプリからのすべてのイベントのハンドラーを設定して追跡します。 このコードを変更する必要はありません。

```
/** 
* Adds an analytics handler for all analytics events from Livefyre. For each event, it sets the data on a global object and then dispatches the event. 
*/ 
function addAnalyticsHandler() { 
  Livefyre.analytics.addHandler(function (events) { 
    (events || []).forEach(function (data) { 
      console.log('Event handled:', data.type); 
      trackLivefyreEvent(data); 
    }); 
  }); 
}
```

## 詳細情報

このページで説明されているトピックの詳細については、次を参照してください。

* [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)
* [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)
* [ルール](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/create-rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
