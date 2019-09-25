---
description: 'null'
seo-description: 'null'
seo-title: ページへのサイトの追加
solution: Experience Manager
title: ページへのサイトの追加
uuid: 6499c45a-3773-4adb-a6c7-22a628309afd
translation-type: tm+mt
source-git-commit: bd989c97ae5cf06a5ac3deec215f865b0fe95d16

---


# ページへのサイトの追加 {#adding-sidenotes-to-a-page}

Livefyreには、ページ上にSidenetを配置するためのいくつかの設定オプションが用意されています。

* 「セレクター」オプションは、サイドを表示する要素を定義します。
* アンカーは、サイドを示すことのできる要素を表します。
* カスタムスレッドコンテナを使用すると、サイド付きの内容を基準にして、サイド付きスレッドが配置される場所を定義できます。
* 「サイド数」(Sidents count)オプションを使用すると、指定した場所に追加されたサイド数を表示できます。
* 複数のオブジェ `ConvConfig` クトを使用して、単一ページの複数のストーリーにサイドを追加します。

## セレクター {#section_wyj_4sv_sy}

セレクターオプションを使用すると、サイドがページ上のコンテンツを検索できます。 このオプションの値を使用すると、使用する要素を動的に決定できます。 セレクター文字列（「#content p, #content img」など）、jQueryオブジェクト(例： `$(‘#content’)`)、DOM要素の配列、または2つのプロパティを持つオブジェクトを指定できます。「含む」と「除外する」。 その後、サイドアプリは、指定された要素またはページ上の一致する要素を使用します。 「含む」および「除外する」プロパティを使用する場合、Sidentはまずページを解析して「含む」プロパティのすべての要素を検索し、次に「除外する」プロパティの要素を削除します。

## アンカー {#section_ehq_psv_sy}

アンカーは、コンテンツを表示できる要素を表します。 アンカー要素には、テキストまたは画像を含めることができます。 アプリの構築中に渡されるセレクターオプションによって、アンカー要素が決まります。

## アンカーID {#section_rsb_rsv_sy}

ページ上のアンカーは、を使用して識別されま `data-lf-anchor-id`す。

アンカーのIDを自分で設定するには、アンカーにマ `data-lf-custom-anchor-id` ップする要素に属性を追加します。 これは、アンカーの自動検出が失敗する場合に役立ちます。

例えば、画像のデスクトップバージョンとモバイルバージョンで異なるURLを使用する場合、2つの異なるURLが異なるアンカーにマッピングされる可能性があります。 代わりに、HTMLがモバイルとデスクトッ `data-lf-custom-anchor-id` プの両方で同じものを提供する場合、画像要素は単一のアンカーとして扱われます。

アンカーには、動的に決定されるタイプがありますが、属性を使用して明示的に設定することもで `data-lf-custom-anchor-type` きます。

>[!NOTE]
>
>列挙番号の値を使用する必要があります。

次のタイプを使用できます。

* **** テキスト：1
* **** 画像：2
* **** メディア：3
* **** リッチ：4

このメソ [ッドを使用してSineworksコンテンツをページに動的に追](/help/implementation/c-app-integrations/c-sidenotes-integration/update-anchors-method.md)`updateAnchors` 加する方法について詳しくは、updateAnchorsメソッドを参照してください。

## カスタムスレッドコンテナ {#section_jdh_btv_sy}

このオプシ `threadContainerEl` ョンを使用して、既定の位置以外のサイドスレッドの位置を指定します。 デフォルトでは、アンカーがアクティブ化されると、サイドは関連するコンテンツの横または下に表示されます。 このデフォルトを変更するには、を使用 `threadContainerEl` して、ねじを表示する要素を指定します。

このオプションの値は、最初の有効な要素のみが使用される以外は、セレクターオプションと同じように機能します。

## サイド数 {#section_pld_ntv_sy}

このオプションを `numSidenotesEl` 使用して、ページにオプションのサイド数ウィジェットを埋め込みます。 このオプションは、セレクターオプションと同じ入力を受け付けますが、入力配列の最初の有効な要素のみを使用します。

ウィジェットは提供された要素または一致した要素を装飾し、Sidents入力アイコン、この位置に入力されたSidentの数、ヘルプアイコンを含みます。

ウィジェットをクリックすると、サイドネートの簡単な説明と使用方法を含むポーバーが表示されます。

説明と例のテキストは、それぞれカスタム文字列（および）を使用して `questionExplanation` 設定で `questionMockText`きます。 カウントウィジェットとポーバーの外観は、それぞれカスタムスタイル（および）を使用して `numSidenotes` 設定するこ `numSidenotesPopover`ともできます。

## 単一ページへの複数サイトのコレクションの追加 {#section_pjl_ptv_sy}

Livefyreでは、複数のサイドコレクションを単一のページに追加できます。 例えば、ページに3つのニュースストーリーが含まれる場合、「アプリを表示」の3つの異なる繰り返しを含めることができます。 これを行うには、作成するSidentの各インスタ `ConvConfig` ンスに対して別々のオブジェクトを定義する必要があります。 次に例を示します。

```
<html> 
   <head> 
      <script src="//cdn.livefyre.com/Livefyre.js"></script> 
   </head> 
<body> 
   <h2>Story #1</h2> 
   <div id="story1"> 
      <p class="sidenotes">stuff #1</p> 
      <p class="sidenotes">more stuff #1</p> 
   </div> 
   <hr /> 
   <h2>Story #2</h2> 
   <div id="story2"> 
      <p class="sidenotes">stuff #2</p> 
      <p class="sidenotes">more stuff #2</p> 
      <p class="sidenotes">more and more stuff</p> 
   </div> 
   <hr /> 
   <script type="text/javascript"> 
      var convConfig_story1 = { 
         network: '<Your Network>', 
         siteId: '<Site ID>', 
         articleId: '<Your Article ID>', 
         selectors: '#story1 > p.sidenotes', 
         collectionMeta: '<First collectionMeta>' 
      }; 
  
      var convConfig_story2 = { 
         network: '<Your Network>', 
         siteId: '<Site ID>', 
         articleId: '<Your Second Article ID>', 
         selectors: '#story2 > p.sidenotes', 
         collectionMeta: '<Second collectionMeta>' 
      }; 
  
      Livefyre.require(['sidenotes#1', 'auth'], function(Sidenotes, auth) { 
         new Sidenotes(convConfig_story1); 
         new Sidenotes(convConfig_story2); 
         auth.delegate({ 
            login: function (callback) { 
               callback(null,{livefyre: '<Login Token>'}); 
            } 
         }); 
      }); 
   </script> 
</body> 
</html>
```
