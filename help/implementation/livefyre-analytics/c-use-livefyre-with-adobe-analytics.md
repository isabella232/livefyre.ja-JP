---
description: 'null'
seo-description: 'null'
seo-title: Adobe AnalyticsおよびDynamic Tag Manager(DTM)lk xavvn vefyreとAdobe AnalyticsおよびDynamic Tag Manager(DTM)との連携によるLivefyreの使用
uuid: 9a1c25c0-c474-46ff-82ac-e89357007c7f
translation-type: tm+mt
source-git-commit: 55bfc0a545bb4a1093c29bd11e764c9799135324

---


# Adobe AnalyticsおよびDynamic Tag Manager(DTM)と共にLivefyreを使用する{#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Livefyreアプリのデータを収集するようにAdobe AnalyticsとDynamic Tag Manager(DTM)を設定します。

## 手順1:Adobe Analyticsでのイベントの設定 {#section_iks_kgd_4cb}

Adobe Analytics Report Suite Managerで、Livefyreイベントを1つ以上のカスタム成功イベントにマッピングします。

Report Suite Managerについて詳しくは、「Report Suite Manager」を参 [照してください](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)。

1. Adobe Analyticsに管理者ユーザーとしてログインします。
1. Adobe Analytics管理者Report Suite Managerを開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックし、に移動して、レポートスイートを編集しま **[!UICONTROL Edit Settings > Conversion > Success Events]**&#x200B;す。
1. Livefyreイベントを1つ以上のカスタム成功イベントにマップします。

## 手順2:コンバージョン変数の設定

Adobe Analytics管理者Report Suite Managerで、Livefyreコンバージョン変数(eVar)をコンバージョン変数にマップします。 コンバージョン変数は、Livefyreイベントから収集されたデータを識別する方法を決定するための並べ替え関数のように機能します。

1. Report Suite Managerで、をクリックしま **[!UICONTROL Edit Settings > Conversion > Conversion Variables]**&#x200B;す。
1. 使用するカスタムコンバージョン変数(eVar)を選択し、Livefyreコンバージョン変数にマッピングします。 Livefyreコンバージョン変数をカスタムコンバージョン変数にマップするには：
* コンバージョン変数の有効化
* コンバージョン変数に名前を付ける
* コンバージョン変数に型を指定します。
1. カスタムコンバージョン変数を保存します。

## 手順3:DTMを使用したLivefyreイベントでのレポートスイートの追加 {#section_t15_2hd_4cb}

Adobe AnalyticsをDTMに追加して、Analyticsを機能させます。 これを行うには、新しいプロパティとツールを作成し、Livefyreイベントを含む新しいレポートスイートをプロパティに追加します。 DTMについて詳しくは、 [DTMを参照してください](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)。

Livefyreイベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合は、この手順を実行する必要はありません。

1. DTMで、既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、ボタンをクリックし **[!UICONTROL Add a Tool]** ます。
ツールに次のパラメータを設定します。
* Set **[!UICONTROL Tool Type]** to **[!UICONTROL Adobe Analytics]**.
* Enable **[!UICONTROL Automatic Configuration]**.
* Enable **[!UICONTROL Authenticate via Marketing Cloud]**.
1. フィールドに、Livefyreイベントを含むレポートスイートの名前を追加するか、確認 **[!UICONTROL Report Suites]** します。

## 手順4:Analytics処理を設定するためのページ型ルールの設定 {#section_jfj_j3d_4cb}

ページ型ルールを設定して、すべてのデータを取り込みます。 ページ型ルールを使用すると、ページが読み込まれたときのイベントを記録するルールにカスタムjavascriptを設定できます。

>[!NOTE]
>
>イベント型ルールやダイレクト型ルールは使用しないでください。

1. DTMで、「tab」を選択 **[!UICONTROL Rules]** します。
1. Click **[!UICONTROL Page Load Rules]**.
1. ボタンをクリック **[!UICONTROL Create New Rule]** します。
1. ボタンをクリ **[!UICONTROL Conditions]** ックして、セクションを開 **[!UICONTROL Plus]** きます。
1. ルールをトリガーします。 ルールを **[!UICONTROL DOM Ready]** 非同期で **[!UICONTROL Onload]** 遅延または実装する場合は、タイプを選択またはトリガーします。
1. （オプション）パラメーターを追加して、Livefyreアプリを表示するページを制限します。 その他の設定オプションについて詳しくは、 [DTMを参照してください](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)。
1. の下で、 **[!UICONTROL Javascript/ Third Party Tags]**&#x200B;タブをクリック **[!UICONTROL Non-sequential]** し、をクリックしま **[!UICONTROL Add New Script]**&#x200B;す。
1. スクリプ **[!UICONTROL Sequential HTML]** トタイプとして選択します。
1. 次のスクリプトをコードエディターに追加し、をクリックしま **[!UICONTROL Save Code]**す。
次のスクリプトは、Livefyre javaScriptの読み込 `livefyre_analytics` み後にダイレクト型ルールを呼び出します。 次のスクリプトの例では、がページ上にあるかどうかを400 msごとに `livefyre.analytics` チェックします。 ページが読み込まれると、livefyre.analyticsはトラッキング情報を送信します。

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

1. Click **[!UICONTROL Save Code]**.
1. Click **[!UICONTROL Save Rule]**.

## 手順5:ダイレクト型ルールの作成によるLivefyre用のAdobe Analyticsマッピング設定の構築 {#section_gvp_b1g_pdb}

カスタムイベント、DTM内のAdobe Analytics UIフィールドおよびデータ要素を使用して、DTMを使用してLivefyreを実装する方法は他にもあります。 このドキュメントでは、同じ効果を実現するためにカスタムJavaScriptを使用します。

1. DTMで「ルール」タブを **選択し** 、「ダイレクト型ルール」 **をクリックします**。
1. Click on the **Create New Rule** button.
1. 新しいルールにLivefyre **Analyticsという名前を付けます**。
1. 「条件」設 **定領域** 。
1. 「文字列」フ **ィールドに** 、と入力しま `livefyre_analytics`す。
1. 「JavaScript /サードパーティタグ」セクションを展開し、「新しいスクリプトを追加」ボ **タンをクリックしま** す。
1. 「タ **グ名** 」入力ボックスにLivefyre Analytics Configと **入力します** 。
1. 「非順 **次JavaScript」を選択します**。
1. 次のLivefyre設定コードをコードエディターに入力し、「コードを保存」ボタンをク **リックします** 。

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

* Livefyreのすべての解析イベントの解析ハンドラーを追加します。 イベントごとに、グローバルオブジェクトにデータを設定し、イベントをディスパッチします。

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
1. Click on **Save Rule**.

## Step 6: Approve changes for Page Load Rule {#section_pxc_11t_ycb}

1. Go to **[!UICONTROL Approvals]** tab.
1. Click **[!UICONTROL Approve]**.
1. Click **[!UICONTROL Yes, approve]** to confirm your approval.
1. Go to **[!UICONTROL Overview > Publish Queue]**.
1. Select the Rule to publish.
1. Click **[!UICONTROL Publish Selected]**.
1. Click **[!UICONTROL Publish]** to confirm that you want to publish.

## Script {#section_xkb_vft_mcb}

The following sample code maps the specific eVars to available Livefyre eVars. The Livefyre conversion variable ( `eVar`) name (for example, `appId`) maps to the name you set up in the Report Suite Manager (for example, `eVar81`). Change the `eVar` names in this script to the custom conversion variables.
```

var s = _satellite.getToolsByType`('sc')[0]`.getS();var evaMap = {appId:'eVar81',appType:'eVar82'};

```
The following sample code maps the specific events you set up in the Report Suite Manager with available Livefyre events. In this example, `event82` is set up as any user interaction event without differentiating which kind of user interaction event (for example, liking or sharing content). This is an efficient way to record all user interaction information in a block. You can also map the events in the DTM Analytics UI with Data Element referencing.
```

var eventMap = {FlagCancel:'event82',\
FlagClick:'event82',\
FlagDisagree:'event82',\
FlagOffense:'event82',\
FlagOffTopic:'event82',\
フラグスパム：'event82',\
いいね！:'event82',Load:'event81',\
RequestMore:'event82',\
ShareButtonClick:'event82',\
ShareFacebook:'event82',\
ShareOnPostClick:'event82',\
ShareTwitter:'event82',\
ShareURL:'event82',\
SortStream:'event82',\
Twitterの「いいね！」クリック：'event82',TwitterReplyClick:'event82',\
Twitterリツイートクリック：'event82',\
TwitterUserFollow:'event82'};

```
The following sample states that if there isn't an event in this list, don't do anything. You do not need to modify this section of code.
```

function trackLivefyreEvent(data) {\
var event =[eventMapdata.type];console.log('Track:', data.type, event);

if (!event) {console.warn(data.type, 'is not mapped to event in AA');\
return;
}

```
The following code differentiates the event types that `event82` records. The conversion variable, `eVar83` records the type of user interaction, and the script sets up `eVar83` to separate the user interaction data by type. So `eVar83` allows you to break out the recorded data into specific types of user interactions.
```

var vars = ['events'];\
switch (event) {case 'event82':s.eVar83 = data.type;\
vars.push('eVar83');\
break;デフォルト：}

['generator', 'evars'].forEach(function (type) {\
var obj =[datatype];for (var d in obj) {if (obj.hasOwnProperty(d) &amp;&amp;[evarMapd]) {\
s[[evarMapd]] =[objd];\
vars.push([evarMapd]);}});

s.linkTrackVars = vars.join(',');\
s.linkTrackEvents = event;\
s.events = event;

console.log('linkTrackVars:', s.linkTrackVars);\
console.log('linkTrackEvents:', s.linkTrackEvents);\
console.log('events:', s.events);

s.tl();
}

```
The following code sample adds a handler to listen to all the events that happen. It uses the page load rule on load, waits for events to exist, then sets up handler for all events from the App and tracks them. You do not need to modify this code.
```

/**
* Livefyreのすべての解析イベントの解析ハンドラーを追加します。 イベントごとに、グローバルオブジェクトにデータを設定し、イベントをディスパッチします。

*/function addAnalyticsHandler() {Livefyre.analytics.addHandler(function (events) {(events)|| []).forEach(function (data) {console.log('Event handled:', data.type);trackLivefyreEvent(data);});});}

```
## More Info

For more information on the topics discussed on this page, see:

* [Report Suite Manager](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)
* [DTM](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)
* [Rules](https://marketing.adobe.com/resources/help/en_US/dtm/rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)

