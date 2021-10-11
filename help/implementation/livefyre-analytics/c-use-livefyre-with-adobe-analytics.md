---
description: Livefyre アプリのデータを収集するためのAdobe Analyticsと Dynamic Tag Manager(DTM) の設定。
title: Livefyre とAdobe Analyticsおよび Dynamic Tag Manager(DTM) の使用
exl-id: a866782d-fca6-48bf-9fb8-5080e396919b
source-git-commit: 53aead87db517e6f68266a66115889509287a287
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 1%

---

# Livefyre とAdobe Analyticsおよび Dynamic Tag Manager(DTM) の使用{#use-livefyre-with-adobe-analytics-and-dynamic-tag-manager-dtm}

Livefyre アプリのデータを収集するためのAdobe Analyticsと Dynamic Tag Manager(DTM) の設定。

## 手順 1:Adobe Analyticsでのイベントの設定 {#section_iks_kgd_4cb}

Adobe Analytics Report Suite Manager で、Livefyre イベントを 1 つ以上のカスタム成功イベントにマッピングします。

Report Suite Manager の詳細については、「[Report Suite Manager](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=en)」を参照してください。

1. 管理者ユーザーとしてAdobe Analyticsにログインします。
1. Adobe Analytics Admin Report Suite Manager を開きます。
1. 新しいレポートスイートを作成するか、既存のレポートスイートを選択します。
1. 変更するレポートスイートをクリックし、**[!UICONTROL Edit Settings > Conversion > Success Events]** に移動して、レポートスイートを編集します。
1. Livefyre イベントを 1 つ以上のカスタム成功イベントにマッピングします。

## 手順 2:コンバージョン変数の設定

Livefyre コンバージョン変数 (eVar) をAdobe Analytics Admin Report Suite Manager でコンバージョン変数にマッピングします。 コンバージョン変数は、並べ替え関数のように機能し、Livefyre イベントから収集されたデータを識別する方法を決定します。

1. Report Suite Manager で **[!UICONTROL Edit Settings > Conversion > Conversion Variables]** をクリックします。
1. 使用するカスタムコンバージョン変数 (eVar) を選択し、Livefyre コンバージョン変数にマッピングします。 Livefyre コンバージョン変数をカスタムコンバージョン変数にマッピングするには：
* コンバージョン変数の有効化
* コンバージョン変数の名前を設定します。
* コンバージョン変数に型を指定します。
1. カスタムコンバージョン変数を保存します。

## 手順 3:DTM を使用した Livefyre イベントでのレポートスイートの追加 {#section_t15_2hd_4cb}

Adobe Analyticsを DTM に追加して、Analytics を機能させます。 これをおこなうには、新しいプロパティとツールを作成し、Livefyre イベントを含む新しいレポートスイートをプロパティに追加します。 DTM について詳しくは、[DTM](https://experienceleague.adobe.com/docs/dtm/using/c-overview.html?lang=en) を参照してください。

Livefyre イベントで設定したレポートスイート用に既にプロパティまたはツールが設定されている場合は、この手順を実行する必要はありません。

1. DTM で、既存のプロパティを作成または編集します。
1. 既存のAdobe Analyticsツールを作成または編集します。
1. 既存のAdobe Analyticsツールが存在しない場合は、「**[!UICONTROL Add a Tool]**」ボタンをクリックします。
ツールに次のパラメータを設定します。

   * **[!UICONTROL Tool Type]** を **[!UICONTROL Adobe Analytics]** に設定します。
   * 有効にする **[!UICONTROL Automatic Configuration]**.
   * 有効にする **[!UICONTROL Authenticate via Marketing Cloud]**.
1. Livefyre イベントを含むレポートスイートの名前を **[!UICONTROL Report Suites]** フィールドに追加するか、または確認します。

## 手順 4:Analytics の処理を設定するページ型ルールの設定 {#section_jfj_j3d_4cb}

すべてのデータを取り込むページ型ルールを設定します。 ページ型ルールを使用すると、ページの読み込み時にイベントを記録するルールにカスタム JavaScript を配置できます。

>[!NOTE]
>
>イベント型ルールやダイレクト型ルールは使用しないでください。

1. DTM で、「**[!UICONTROL Rules]**」タブを選択します。
1. クリック **[!UICONTROL Page Load Rules]**.
1. **[!UICONTROL Create New Rule]** ボタンをクリックします。
1. **[!UICONTROL Plus]** ボタンをクリックして、**[!UICONTROL Conditions]** セクションを開きます。
1. ルールをトリガーします。 ルールを遅延または非同期で実装する場合は、 **[!UICONTROL DOM Ready]** または **[!UICONTROL Onload]**&#x200B;トリガータイプを選択します。
1. （オプション）追加のパラメーターを追加して、Livefyre Apps を表示するページを制限します。 追加の設定オプションについて詳しくは、[DTM](https://experienceleague.adobe.com/docs/dtm/using/c-overview.html?lang=en) を参照してください。
1. **[!UICONTROL Javascript/ Third Party Tags]** の下の「**[!UICONTROL Non-sequential]**」タブをクリックし、「**[!UICONTROL Add New Script]**」をクリックします。
1. スクリプトタイプとして **[!UICONTROL Sequential HTML]** を選択します。
1. 次のスクリプトをコードエディターに追加して、**[!UICONTROL Save Code]** をクリックします。

   次のスクリプトは、Livefyre JavaScript の読み込み後に `livefyre_analytics` 直接呼び出しルールを呼び出します。 次のスクリプトの例では、400 ミリ秒ごとに `livefyre.analytics` がページ上にあるかどうかを確認します。 ページが読み込まれると、 livefyre.analytics はトラッキング情報を送信します。

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

## 手順 5:Livefyre 用のAdobe Analyticsマッピング設定を構築するための直接呼び出しルールの作成 {#section_gvp_b1g_pdb}

カスタムイベント、DTM 内のAdobe Analytics UI フィールド、データ要素を使用して DTM で Livefyre を実装する方法は他にもあります。 このドキュメントでは、カスタム JavaScript を使用して同じ効果を実現します。

1. DTM で、「**ルール**」タブを選択し、「**直接呼び出しルール**」をクリックします。
1. 「**新規ルールを作成**」ボタンをクリックします。
1. 新しいルールに **Livefyre Analytics** と名前を付けます。
1. **条件** 設定領域を展開します。
1. 「**文字列**」フィールドに、`livefyre_analytics` と入力します。
1. 「 Javascript /サードパーティタグ」セクションを展開し、「**新しいスクリプトを追加** 」ボタンをクリックします。
1. **Livefyre Analytics Config** を **タグ名** 入力ボックスに入力します。
1. 「**非順次 JavaScript**」を選択します。
1. 次の Livefyre 設定コードをコードエディターに入力し、「**コードを保存**」ボタンをクリックします。

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

   * Livefyre のすべての Analytics イベントに対して Analytics ハンドラーを追加します。 イベントごとに、データをグローバルオブジェクトに設定し、イベントをディスパッチします。

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

## 手順 6:ページ型ルールの変更の承認 {#section_pxc_11t_ycb}

1. **[!UICONTROL Approvals]** タブに移動します。
1. クリック **[!UICONTROL Approve]**.
1. **[!UICONTROL Yes, approve]** をクリックして、承認を確定します。
1. 移動 **[!UICONTROL Overview > Publish Queue]**.
1. 発行するルールを選択します。
1. クリック **[!UICONTROL Publish Selected]**.
1. **[!UICONTROL Publish]** をクリックして、公開することを確認します。

## script {#section_xkb_vft_mcb}

以下のサンプルコードは、特定の eVar を使用可能な Livefyre eVar にマッピングします。 Livefyre コンバージョン変数 (`eVar`) の名前（例えば `appId`）は、Report Suite Manager で設定した名前（例えば、`eVar81`）にマッピングされます。 このスクリプト内の `eVar` 名をカスタムコンバージョン変数に変更します。


```
var s = _satellite.getToolsByType`('sc')[0]`.getS();
var evarMap = {
  appId: 'eVar81',
  appType: 'eVar82'
};
```

次のサンプルコードは、Report Suite Manager で設定した特定のイベントと、使用可能な Livefyre イベントを対応付けます。 この例では、 `event82` は、どの種類のユーザーインタラクションイベント（コンテンツの「いいね！」や共有など）を区別することなく、任意のユーザーインタラクションイベントとして設定されます。 これは、すべてのユーザーインタラクション情報を 1 つのブロックに記録する効率的な方法です。 また、DTM Analytics UI のイベントを、データ要素の参照先にマッピングすることもできます。

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

次のサンプルでは、このリストにイベントがない場合は何も実行しないことを示しています。 このコードセクションを変更する必要はありません。

```
function trackLivefyreEvent(data) {
  var event = eventMap[data.type];
  console.log('Track:', data.type, event);

  if (!event) {
    console.warn(data.type, 'is not mapped to an event in AA');
    return;
  }
```

次のコードは、`event82` が記録するイベントタイプを区別します。 コンバージョン変数 `eVar83` は、ユーザーインタラクションのタイプを記録し、スクリプトは、ユーザーインタラクションデータをタイプ別に分けるように `eVar83` を設定します。 したがって、`eVar83` では、記録されたデータを特定のタイプのユーザーインタラクションに分割できます。

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

次のコードサンプルでは、発生するすべてのイベントをリッスンするハンドラーを追加しています。 読み込み時にページ型ルールを使用し、はイベントが存在するのを待ってから、アプリ内のすべてのイベントに対してハンドラーを設定して追跡します。 このコードを変更する必要はありません。

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

このページで取り上げるトピックの詳細は、次を参照してください。

* [Report Suite Manager](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=en)
* [DTM](https://experienceleague.adobe.com/docs/dtm/using/c-overview.html?lang=en)
* [ルール](https://experienceleague.adobe.com/docs/dtm/using/resources/rules/create-rules.html?lang=en)
* [Livefyre.js](/help/implementation/c-livefyre.js.md)
