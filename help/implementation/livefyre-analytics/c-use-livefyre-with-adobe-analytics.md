---
description: null
seo-description: null
seo-title: Adobe AnalyticsおよびDynamic Tag Manager（DTM）を使用したLivefyreのAdobe AnalyticsおよびDynamic
  Tag Manager（DTM） lk xavvnフィードの使用
uuid: 9a1c25c0- c474-46ff-82ac- e89357007c7f
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Adobe AnalyticsおよびDynamic Tag Manager（DTM）でLivefyreを使用する{#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Livefyreアプリのデータを収集するために、Adobe AnalyticsおよびDynamic Tag Manager（DTM）を設定します。

## 手順1:Adobe Analyticsでのイベントの設定 {#section_iks_kgd_4cb}

Adobe Analytics Report Suite Managerの1つ以上のカスタム成功イベントにLivefyreイベントをマッピングします。

Report Suite Managerについて詳しくは [、Report Suite Manager](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)を参照してください。

1. 管理者ユーザーとしてAdobe Analyticsにログインします。
1. Adobe Analytics管理者Report Suite Managerを開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックしてレポートスイートを編集し、に移動 **[!UICONTROL Edit Settings > Conversion > Success Events]**します。
1. Livefyreイベントを1つ以上のカスタム成功イベントにマップします。

## 手順2:コンバージョン変数の設定

Adobe Analytics管理者Report Suite Managerのコンバージョン変数にLivefyreコンバージョン変数（eVar）をマッピングします。コンバージョン変数は、Livefyreイベントから収集されたデータを識別するための並べ替え関数のように機能します。

1. Report Suite Managerをクリック **[!UICONTROL Edit Settings > Conversion > Conversion Variables]**します。
1. 使用するカスタムコンバージョン変数（eVar）を選択し、それらをLivefyreコンバージョン変数にマッピングします。Livefyreコンバージョン変数をカスタムコンバージョン変数にマップするには:
* コンバージョン変数の有効化
* コンバージョン変数に名前を付ける
* コンバージョン変数にタイプを入力する
1. カスタムコンバージョン変数を保存します。

## 手順3:DTMを使用したLivefyreイベントのレポートスイートの追加 {#section_t15_2hd_4cb}

DTMにAdobe Analyticsを追加して、Analyticsを利用できるようにします。これを行うには、新しいプロパティとツールを作成し、プロパティにLivefyreイベントを含む新しいレポートスイートを追加します。DTMについて詳しくは [、DTM](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)を参照してください。

Livefyreイベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合、この手順を実行する必要はありません。

1. DTMで既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、ボタンを **[!UICONTROL Add a Tool]** クリックします。
ツールに次のパラメーターを設定します。
* に設定 **[!UICONTROL Tool Type]****[!UICONTROL Adobe Analytics]**します。
* 有効 **[!UICONTROL Automatic Configuration]**化
* 有効 **[!UICONTROL Authenticate via Marketing Cloud]**化
1. Livefyreイベントを **[!UICONTROL Report Suites]** 含むレポートスイートの名前を追加または確認します。

## 手順4:ページ型ルールの設定によるAnalyticsの処理の設定 {#section_jfj_j3d_4cb}

すべてのデータを取り込むページ型ルールを設定します。ページ型ルールを使用すると、ページの読み込み時にイベントを記録するカスタムjavascriptをルールに挿入できます。

>[!NOTE]
>
>イベント型ルールまたはダイレクト型ルールを使用しないでください。

1. DTMで、「タブ」を選択 **[!UICONTROL Rules]** します。
1. **[!UICONTROL Page Load Rules]**をクリックします。
1. ボタンを **[!UICONTROL Create New Rule]** クリックします。
1. ボタンをクリックして **[!UICONTROL Conditions]** セクションを開き **[!UICONTROL Plus]** ます。
1. ルールをトリガーします。ルールを非同期で遅延または実装する場合は、タイプを選択 **[!UICONTROL DOM Ready]** または **[!UICONTROL Onload]** トリガーします。
1. （オプション） Livefyreアプリを表示するページを制限するためのパラメーターを追加します。追加の設定オプションについて詳しくは [、DTM](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)を参照してください。
1. で **[!UICONTROL Javascript/ Third Party Tags]**、タブを **[!UICONTROL Non-sequential]** クリックし、をクリック **[!UICONTROL Add New Script]**します。
1. スクリプトの種類 **[!UICONTROL Sequential HTML]** として選択します。
1. コードエディターに次のスクリプトを追加し、をクリック **[!UICONTROL Save Code]**します。
次のスクリプトでは、Livefyre JavaScriptの読み込み後に `livefyre_analytics` ダイレクト型ルールを呼び出します。次のスクリプトの例では、ページ上のあるか `livefyre.analytics` どうかを確認するために400ミリ秒ごとにチェックします。ページが読み込まれると、livehyre. analyticsはトラッキング情報を送信します。

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

1. **[!UICONTROL Save Code]**をクリックします。
1. **[!UICONTROL Save Rule]**をクリックします。

## 手順5:LivefyreのAdobe Analyticsマッピング設定を作成するためのダイレクト型ルールの作成 {#section_gvp_b1g_pdb}

カスタムイベント、DTM内のAdobe Analytics UIフィールド、データ要素を使用してLivefyreを実装する方法もあります。このドキュメントでは、カスタムJavaScriptを使用して同じ効果を実現しています。

1. In DTM select the **Rules** tab and then click on **Direct Call Rules**.
1. 「新しいルール **を作成」** ボタンをクリックします。
1. 新しいルール **Livefyre Analyticsに名前を付け**ます。
1. **条件** の設定領域を展開します。
1. **"String** 」フィールドに入力 `livefyre_analytics`します。
1. "Javascript/サードパーティタグ」セクションを展開し、「新しいスクリプト **を追加** 」ボタンをクリックします。
1. 「タグ名」入力ボックスに ******Livefyre** Analytics設定と入力します。
1. 「非順次 **Javascript**」を選択します。
1. コードエディターに次のLivefyre設定コードを入力し、「コード **を保存** 」ボタンをクリックします。

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

* Livefyreからすべての解析イベントの分析ハンドラーを追加します。イベントごとに、グローバルオブジェクトにデータを設定してからイベントをディスパッチします。

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

var s=_ satellite. getToolsByType`('sc')[0]`. gets（）;
var eVarMap={AppID:eVar81'、appType:'eVar82'};

```
The following sample code maps the specific events you set up in the Report Suite Manager with available Livefyre events. In this example, `event82` is set up as any user interaction event without differentiating which kind of user interaction event (for example, liking or sharing content). This is an efficient way to record all user interaction information in a block. You can also map the events in the DTM Analytics UI with Data Element referencing.
```

var eventMap={flagCancel:'event82'，\
flagClick:'event82'，\
フラグの非表示:'event82'，\
フラグ攻撃:'event82'，\
flagOffTopic:'event82'，\
Flagスパム:'event82'，\
いいね!:'event82'、Load:'event81'，\
requestMore:'event82'，\
ShareButtonClick:'event82'，\
ShareFacebook:'event82'，\
ShareOnPostClick:'event82'，\
ShareTwitter:'event82'，\
ShareURL:'event82'，\
sortStream:'event82'，\
TwitterLikeclick:'event82'、TwitterReplyClick:'event82'，\
TwitterResetTweetClick:'event82'，\
TwitterUserフォロー:'event82'};

```
The following sample states that if there isn't an event in this list, don't do anything. You do not need to modify this section of code.
```

function trackLiveFyReEvent（data）{\
var event= EventMapData[. type];
console. log（'Track:'， data. type， event）;

if（!event）{console.
warning（data. type，'is not mapping to an event in AA'）;\
return;}

```
The following code differentiates the event types that `event82` records. The conversion variable, `eVar83` records the type of user interaction, and the script sets up `eVar83` to separate the user interaction data by type. So `eVar83` allows you to break out the recorded data into specific types of user interactions.
```

var vars= ['events'];\
switch（event）{case'event82':s. eVar83= data. type;\
vars. push（'eVar83'）;\
break;
default:}

['generator'，'evar']. foreach（function（type）{\
var obj= datatype[];
for（var d in obj）{if（obj.
hasOwnProperty（d）&& eVarMapD[]）{\
s[eVarMapD[]]= objd[];\
vars. push（eVarMapD[]）;}}}）;

s. linkTrackVars= vars. join（'，'）;\
s. linkTrackEvents= event;\
s. events= event;

console. log（'linkTrackVars:'， s. linkTrackVars）;\
console. log（'linkTrackEvents:'， s. linkTrackEvents）;\
console. log（'events:'， s. events）;

s. tl（）;}

```
The following code sample adds a handler to listen to all the events that happen. It uses the page load rule on load, waits for events to exist, then sets up handler for all events from the App and tracks them. You do not need to modify this code.
```

/**
* Livefyreからすべての解析イベントの分析ハンドラーを追加します。イベントごとに、グローバルオブジェクトにデータを設定してからイベントをディスパッチします。

*/function addAnalyticHandler（）{Livefyre.
analytics. addHandler（function（events）{（events）{|| []）. Foreach（function（data）{console.
log（'event handled:'， data. type）;
trackLiveFyReEvent（data）;}）;}）;}

```
## More Info

For more information on the topics discussed on this page, see:

* [Report Suite Manager](https://marketing.adobe.com/resources/help/en_US/reference/report_suites_admin.html)
* [DTM](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html)
* [Rules](https://marketing.adobe.com/resources/help/en_US/dtm/rules.html)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)

