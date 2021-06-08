---
description: Livefyreアプリのデータを収集するためにAdobe AnalyticsとDynamic Tag Manager(DTM)を設定します。
title: LivefyreをAdobe AnalyticsおよびDynamic Tag Manager(DTM)と共に使用する
exl-id: a866782d-fca6-48bf-9fb8-5080e396919b
source-git-commit: cbe23e8c253f1531418f18424e180d1adc16e426
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 1%

---

# LivefyreをAdobe AnalyticsおよびDynamic Tag Manager(DTM){#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}と共に使用する

Livefyreアプリのデータを収集するためにAdobe AnalyticsとDynamic Tag Manager(DTM)を設定します。

## 手順1:Adobe Analyticsでのイベントの設定 {#section_iks_kgd_4cb}

Adobe Analytics Report Suite Managerで、Livefyreイベントを1つ以上のカスタム成功イベントにマッピングします。

Report Suite Managerの詳細については、「[Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)」を参照してください。

1. Adobe Analyticsに管理者ユーザーとしてログインします。
1. Adobe Analytics Admin Report Suite Managerを開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックし、**[!UICONTROL Edit Settings > Conversion > Success Events]**&#x200B;に移動して、レポートスイートを編集します。
1. Livefyreイベントを1つ以上のカスタム成功イベントにマッピングする。

## 手順2:コンバージョン変数の設定

Livefyreコンバージョン変数(eVar)をAdobe Analytics Admin Report Suite Managerのコンバージョン変数にマッピングします。 コンバージョン変数は、並べ替え関数のように機能し、Livefyreイベントから収集されたデータを識別する方法を決定します。

1. Report Suite Managerで&#x200B;**[!UICONTROL Edit Settings > Conversion > Conversion Variables]**&#x200B;をクリックします。
1. 使用するカスタムコンバージョン変数(eVar)を選択し、Livefyreコンバージョン変数にマッピングします。 Livefyreコンバージョン変数をカスタムコンバージョン変数にマッピングするには：
* コンバージョン変数の有効化
* コンバージョン変数の名前を指定します。
* コンバージョン変数に型を指定します。
1. カスタムコンバージョン変数を保存します。

## 手順3:DTMを使用したLivefyreイベントでのレポートスイートの追加 {#section_t15_2hd_4cb}

Adobe AnalyticsをDTMに追加して、Analyticsを機能させます。 これをおこなうには、新しいプロパティとツールを作成し、Livefyreイベントを含む新しいレポートスイートをプロパティに追加します。 DTMについて詳しくは、[DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)を参照してください。

Livefyreイベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合は、この手順を実行する必要はありません。

1. DTMで、既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、「**[!UICONTROL Add a Tool]**」ボタンをクリックします。
ツールに次のパラメータを設定します。

   * **[!UICONTROL Tool Type]**&#x200B;を&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;に設定します。
   * 有効にする **[!UICONTROL Automatic Configuration]**.
   * 有効にする **[!UICONTROL Authenticate via Marketing Cloud]**.
1. **[!UICONTROL Report Suites]**&#x200B;フィールドにLivefyreイベントを含むレポートスイートの名前を追加するか、確認します。

## 手順4:Analyticsの処理を設定するためのページ型ルールの設定 {#section_jfj_j3d_4cb}

すべてのデータを取り込むページ型ルールを設定します。 ページ型ルールを使用すると、ページの読み込み時にイベントを記録するルールにカスタムJavaScriptを配置できます。

>[!NOTE]
>
>イベント型ルールやダイレクト型ルールは使用しないでください。

1. DTMで、「**[!UICONTROL Rules]**」タブを選択します。
1. クリック **[!UICONTROL Page Load Rules]**.
1. 「**[!UICONTROL Create New Rule]**」ボタンをクリックします。
1. 「**[!UICONTROL Plus]**」ボタンをクリックして、「**[!UICONTROL Conditions]**」セクションを開きます。
1. ルールをトリガーします。 ルールを非同期的に遅延または実装する場合は、**[!UICONTROL DOM Ready]**&#x200B;または&#x200B;**[!UICONTROL Onload]**&#x200B;トリガータイプを選択します。
1. （オプション）追加のパラメーターを追加して、Livefyre Appsを表示するページを制限します。 追加の設定オプションについて詳しくは、[DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)を参照してください。
1. **[!UICONTROL Javascript/ Third Party Tags]**&#x200B;の下の「**[!UICONTROL Non-sequential]**」タブをクリックし、「**[!UICONTROL Add New Script]**」をクリックします。
1. スクリプトタイプとして&#x200B;**[!UICONTROL Sequential HTML]**&#x200B;を選択します。
1. 次のスクリプトをコードエディターに追加し、**[!UICONTROL Save Code]**&#x200B;をクリックします。

   次のスクリプトは、Livefyre JavaScriptの読み込み後に`livefyre_analytics`直接呼び出しルールを呼び出します。 次のスクリプトの例では、400ミリ秒ごとに`livefyre.analytics`がページ上にあるかどうかを確認します。 ページが読み込まれると、 livefyre.analyticsはトラッキング情報を送信します。

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

## 手順5:Livefyre用のAdobe Analyticsマッピング設定を構築するための直接呼び出しルールの作成 {#section_gvp_b1g_pdb}

カスタムイベント、DTM内のAdobe Analytics UIフィールド、およびデータ要素を使用してDTMでLivefyreを実装する方法は他にもあります。 このドキュメントでは、同じ効果を実現するためにカスタムJavaScriptを使用します。

1. DTMで、「**ルール**」タブを選択し、「**直接呼び出しルール**」をクリックします。
1. 「**新規ルールを作成**」ボタンをクリックします。
1. 新しいルールに&#x200B;**Livefyre Analytics**&#x200B;という名前を付けます。
1. **条件**&#x200B;設定領域を展開します。
1. 「**文字列**」フィールドに、`livefyre_analytics`と入力します。
1. 「 Javascript /サードパーティタグ」セクションを展開し、「**新しいスクリプトを追加** 」ボタンをクリックします。
1. **Livefyre Analytics設定**&#x200B;を「**タグ名**」入力ボックスに入力します。
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

   * Livefyreのすべての分析イベントに対して分析ハンドラーを追加します。 イベントごとに、グローバルオブジェクトにデータを設定し、イベントをディスパッチします。

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

## 手順6:ページ型ルールの変更の承認 {#section_pxc_11t_ycb}

1. **[!UICONTROL Approvals]**&#x200B;タブに移動します。
1. クリック **[!UICONTROL Approve]**.
1. 「**[!UICONTROL Yes, approve]**」をクリックして承認を確定します。
1. 移動 **[!UICONTROL Overview > Publish Queue]**.
1. 発行するルールを選択します。
1. クリック **[!UICONTROL Publish Selected]**.
1. **[!UICONTROL Publish]**&#x200B;をクリックして、公開することを確認します。

## script {#section_xkb_vft_mcb}

以下のサンプルコードは、特定のeVarを使用可能なLivefyre eVarにマッピングします。 Livefyreコンバージョン変数(`eVar`)の名前（例えば、`appId`）は、Report Suite Managerで設定した名前（例えば、`eVar81`）にマッピングされます。 このスクリプト内の`eVar`名をカスタムコンバージョン変数に変更します。


```
var s = _satellite.getToolsByType`('sc')[0]`.getS(); 
var evarMap = { 
  appId: 'eVar81', 
  appType: 'eVar82' 
};
```

以下のサンプルコードは、Report Suite Managerで設定した特定のイベントと、使用可能なLivefyreイベントとをマッピングします。 この例では、`event82`は、どの種類のユーザーインタラクションイベント（例えば、コンテンツの「いいね！」や共有）を区別することなく、任意のユーザーインタラクションイベントとして設定されます。 これは、すべてのユーザーインタラクション情報を1つのブロックに記録する効率的な方法です。 また、DTM Analytics UIのイベントを、データ要素の参照とマッピングすることもできます。

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

次のサンプルでは、このリストにイベントがない場合は何も実行しないことを示しています。 コードのこのセクションを変更する必要はありません。

```
function trackLivefyreEvent(data) {  
  var event = eventMap[data.type]; 
  console.log('Track:', data.type, event); 
   
  if (!event) { 
    console.warn(data.type, 'is not mapped to an event in AA');  
    return; 
  }
```

次のコードは、`event82`が記録するイベントタイプを区別します。 コンバージョン変数`eVar83`は、ユーザーインタラクションのタイプを記録し、スクリプトは、ユーザーインタラクションデータをタイプ別に分けるように`eVar83`を設定します。 したがって、`eVar83`では、記録されたデータを特定のタイプのユーザーインタラクションに分割できます。

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

以下のコードサンプルは、発生するすべてのイベントをリッスンするハンドラーを追加します。 読み込み時にページ型ルールを使用し、はイベントが存在するのを待ってから、アプリのすべてのイベントに対してハンドラーを設定し、それらを追跡します。 このコードを変更する必要はありません。

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

このページで説明するトピックの詳細は、次を参照してください。

* [Report Suite Manager](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)
* [DTM](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html)
* [ルール](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/create-rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
