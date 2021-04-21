---
description: Livefyre Appsのデータを収集するためのAdobe AnalyticsおよびDynamic Tag Manager(DTM)の設定
exl-id: a866782d-fca6-48bf-9fb8-5080e396919b
translation-type: tm+mt
source-git-commit: 24d016fbb2771487f8105b2ca0bb0d03dd60cfc1
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 1%

---

# LivefyreをAdobe AnalyticsおよびDynamic Tag Manager(DTM)と共に使用{#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Livefyre Appsのデータを収集するためのAdobe AnalyticsおよびDynamic Tag Manager(DTM)の設定

## 手順1:Adobe Analytics{#section_iks_kgd_4cb}でイベントを設定

Adobe Analyticsレポートスイートマネージャーで、Livefyreイベントを1つ以上のカスタム成功イベントにマッピングします。

Report Suite Managerについて詳しくは、[Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)を参照してください。

1. 管理者ユーザーとしてAdobe Analyticsにログインします。
1. [Adobe Analytics管理] [Report Suite Manager]を開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックし、**[!UICONTROL Edit Settings > Conversion > Success Events]**&#x200B;に移動して、レポートスイートを編集します。
1. Livefyreイベントを1つ以上のカスタム成功イベントーにマップします。

## 手順2:コンバージョン変数の設定

Livefyreコンバージョン変数(eVar)のコンバージョン変数へのマッピング(Adobe Analytics管理者Report Suite Manager)。 コンバージョン変数は、Livefyreイベントから収集されたデータを識別する方法を決定するための並べ替え関数のような働きをします。

1. Report Suite Managerで&#x200B;**[!UICONTROL Edit Settings > Conversion > Conversion Variables]**&#x200B;をクリックします。
1. 使用するカスタムコンバージョン変数(eVar)を選択し、それらをLivefyreコンバージョン変数にマッピングします。 Livefyreコンバージョン変数をカスタムコンバージョン変数にマップするには：
* コンバージョン変数の有効化
* コンバージョン変数の名前の設定
* コンバージョン変数に型を指定します
1. カスタムコンバージョン変数を保存します。

## 手順3:Livefyreイベント追加を使用したレポートスイートでDTMを使用する{#section_t15_2hd_4cb}

追加Adobe AnalyticsからDTMにアクセスして、Analyticsを機能させます。 これを行うには、新しいプロパティとツールを作成し、Livefyreイベントを含む新しいレポートスイートをプロパティに追加します。 DTMについて詳しくは、[DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)を参照してください。

Livefyreイベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合は、この手順を実行する必要はありません。

1. DTMで、既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、**[!UICONTROL Add a Tool]**ボタンをクリックします。
ツールの次のパラメータを設定します。

   * **[!UICONTROL Tool Type]**&#x200B;を&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;に設定します。
   * 有効にする **[!UICONTROL Automatic Configuration]**.
   * 有効にする **[!UICONTROL Authenticate via Marketing Cloud]**.
1. または追加、**[!UICONTROL Report Suites]**&#x200B;フィールドにLivefyreイベントを設定してレポートスイート名を確認します。

## 手順4:解析処理を設定するためのページ型ルールの設定{#section_jfj_j3d_4cb}

ページ型ルールを設定して、すべてのデータを取り込みます。 ページ型ルールを使用すると、ページの読み込み時にイベントを記録するルールにカスタムjavascriptを設定できます。

>[!NOTE]
>
>イベント型ルールやダイレクト型ルールは使用しないでください。

1. DTMで、「**[!UICONTROL Rules]**」タブを選択します。
1. クリック **[!UICONTROL Page Load Rules]**.
1. 「**[!UICONTROL Create New Rule]**」ボタンをクリックします。
1. **[!UICONTROL Conditions]**&#x200B;セクションを開くには、**[!UICONTROL Plus]**&#x200B;ボタンをクリックします。
1. ルールのトリガー。 ルールを非同期で遅延または実装する場合は、**[!UICONTROL DOM Ready]**&#x200B;または&#x200B;**[!UICONTROL Onload]**&#x200B;トリガータイプを選択します。
1. （オプション）Livefyre Appsを表示するページを追加制限するための追加のパラメーター。 その他の設定オプションについて詳しくは、[DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)を参照してください。
1. **[!UICONTROL Javascript/ Third Party Tags]**&#x200B;の下の「**[!UICONTROL Non-sequential]**」タブをクリックし、「**[!UICONTROL Add New Script]**」をクリックします。
1. スクリプトの種類として&#x200B;**[!UICONTROL Sequential HTML]**&#x200B;を選択します。
1. 次追加のスクリプトをコードエディターに入力し、**[!UICONTROL Save Code]**&#x200B;をクリックします。

   次のスクリプトは、Livefyre JavaScriptの読み込み後に`livefyre_analytics`ダイレクト型ルールを呼び出します。 次のスクリプトの例では、400ミリ秒ごとにチェックを実行し、`livefyre.analytics`がページ上にあるかどうかを確認します。 ページが読み込まれた後、livefyre.analyticsはトラッキング情報を送信します。

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

## 手順5:Livefyre {#section_gvp_b1g_pdb}のAdobe Analyticsマッピング設定を構築するためのダイレクト型ルールの作成

カスタムイベント、DTM内のAdobe AnalyticsUIフィールド、データ要素を使用してLivefyreをDTMと共に実装する方法は他にもあります。 このドキュメントでは、カスタムJavaScriptを使用して同じ効果を実現します。

1. DTMで「**ルール**」タブを選択し、「**直接呼び出しルール**」をクリックします。
1. 「**新しいルールを作成**」ボタンをクリックします。
1. 新しいルールに&#x200B;**Livefyre Analytics**&#x200B;という名前を付けます。
1. **conditions**&#x200B;構成領域を展開します。
1. 「**文字列**」フィールドに`livefyre_analytics`と入力します。
1. 「JavaScript /サードパーティタグ」セクションを展開し、「**追加新しいスクリプト**」ボタンをクリックします。
1. **Livefyre Analytics Config**&#x200B;を&#x200B;**タグ名**&#x200B;入力ボックスに入力します。
1. 「**非順次JavaScript**」を選択します。
1. 次のLivefyre設定コードをコードエディターに入力し、「**コードを保存**」ボタンをクリックします。

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

1. 「**ルールを保存**」をクリックします。

## 手順6:ページ型ルールの変更を承認{#section_pxc_11t_ycb}

1. **[!UICONTROL Approvals]**&#x200B;タブに移動します。
1. クリック **[!UICONTROL Approve]**.
1. **[!UICONTROL Yes, approve]**&#x200B;をクリックして承認を確定します。
1. 移動 **[!UICONTROL Overview > Publish Queue]**.
1. 発行するルールを選択します。
1. クリック **[!UICONTROL Publish Selected]**.
1. **[!UICONTROL Publish]**&#x200B;をクリックして、公開することを確認します。

## script {#section_xkb_vft_mcb}

以下のサンプルコードは、特定のeVarを利用可能なLivefyre eVarにマップしています。 Livefyreコンバージョン変数(`eVar`)名（例えば`appId`）は、Report Suite Managerで設定した名前（例えば`eVar81`）にマップされます。 このスクリプトの`eVar`名前をカスタムコンバージョン変数に変更します。


```
var s = _satellite.getToolsByType`('sc')[0]`.getS(); 
var evarMap = { 
  appId: 'eVar81', 
  appType: 'eVar82' 
};
```

以下のサンプルコードは、Report Suite Managerで使用可能なLivefyreイベントと共に設定した特定のイベントをマップしています。 この例では、`event82`はユーザーインタラクションイベントとして設定され、どの種類のユーザーインタラクションイベント（例えば、コンテンツの「いいね！」や共有）を区別する必要はありません。 これは、すべてのユーザインタラクション情報をブロックに記録する効率的な方法です。 また、DTM Analytics UIのイベントを、データ要素の参照を使用してマッピングすることもできます。

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

次のコードは、`event82`が記録するイベントタイプを区別します。 コンバージョン変数`eVar83`は、ユーザーインタラクションのタイプを記録し、スクリプトは、ユーザーインタラクションデータを型で区切るように`eVar83`を設定します。 `eVar83`を使うと、記録されたデータを特定の種類のユーザー操作に分割できます。

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
