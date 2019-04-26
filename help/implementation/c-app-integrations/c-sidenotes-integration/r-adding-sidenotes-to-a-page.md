---
description: null
seo-description: null
seo-title: ページに対するSideosingの追加
solution: Experience Manager
title: ページに対するSideosingの追加
uuid: 6499c45a-3773-4adb- a6c7-22a628309afd
translation-type: tm+mt
source-git-commit: bd989c97ae5cf06a5ac3deec215f865b0fe95d16

---


# ページに対するSideosingの追加 {#adding-sidenotes-to-a-page}

Livefyreには、ページにSideindingを配置するためのいくつかの設定オプションが用意されています。

* 「セレクター」オプションでは、Socialが表示する要素を定義します。
* アンカーは、サイトを区別できる要素を表します。
* カスタムスレッドコンテナを使用すると、sidesedコンテンツに関連するSocialスレッドの位置を定義できます。
* 「カウント数」オプションでは、指定した場所に追加されたSideindingの数を表示できます。
* 複数 `ConvConfig` のオブジェクトを使用して、単一ページにある複数のストーリーにSideindingを追加します。

## セレクター {#section_wyj_4sv_sy}

セレクターオプションを使用すると、ページ上のコンテンツを検索できます。このオプションの値によって、使用する要素を動的に判断できます。セレクター文字列（"# content p，# content img'など）、jQueryオブジェクト（ `$(‘#content’)`など）、DOM要素の配列、または2つのプロパティを持つオブジェクト）を指定できます。を含めて除外します。次に、Socializeアプリは、指定した要素またはページ上の一致する要素を使用します。プロパティを含めて除外する場合は、まずページを解析して、includeプロパティのすべてのエレメントを探し、excludeプロパティにある要素をすべて削除します。

## アンカー {#section_ehq_psv_sy}

アンカーは、コンテンツを区分できる要素を表します。アンカー要素には、テキストまたは画像を含めることができます。アプリケーションの構築中に渡されるセレクターオプションによって、アンカー要素が決まります。

## アンカーID {#section_rsb_rsv_sy}

ページ上のアンカーは、aを使用して識別 `data-lf-anchor-id`されます。

アンカーのIDを自分で設定するには、アンカーにマップする要素 `data-lf-custom-anchor-id` に属性を追加します。これはアンカーの自動検出が失敗する場合に便利です。

例えば、デスクトップバージョンとモバイルバージョンの画像で異なるURLを使用する場合は、異なるアンカーに2つの異なるURLをマッピングできます。代わりに、モバイルと `data-lf-custom-anchor-id` デスクトップの両方でHTMLを使用すると、画像要素は単一のアンカーとして扱われます。

アンカーには動的に決定されるタイプがありますが `data-lf-custom-anchor-type` 、属性を使用して明示的に設定することもできます。

>[!NOTE]
>
>列挙番号の値を使用する必要があります。

使用可能なタイプは次のとおりです。

* **テキスト:** 1
* **画像:** 2
* **メディア:** 3
* **リッチ:** 4

ページ [に動的にSocifier](/help/implementation/c-app-integrations/c-sidenotes-integration/update-anchors-method.md) コンテンツを追加する `updateAnchors` 方法については、updateAnchorsメソッドを参照してください。

## カスタムスレッドコンテナ {#section_jdh_btv_sy}

オプションを `threadContainerEl` 使用して、デフォルトの位置以外のSideindingスレッドの場所を指定します。デフォルトでは、アンカーをアクティブにすると、関連コンテンツの横または下にSocialが表示されます。このデフォルトを変更するには、まず `threadContainerEl` 、スレッドを表示する要素を指定します。

このオプションの値は、最初の有効な要素のみを使用することを除いて、セレクターオプションと同じです。

## サイトのカウント {#section_pld_ntv_sy}

オプションとして、ページにオプションのカウントウィジェットを埋め込む `numSidenotesEl` オプションを使用します。このオプションは、セレクターオプションと同じ入力を受け付けますが、入力配列の最初の有効な要素のみを使用します。

ウィジェットは提供されたまたは一致した要素を装飾し、Ssiinding入力アイコン、この位置に入力されたSideindingの数、ヘルプアイコンを含めます。

ウィジェットをクリックすると、表示方法と使用方法の短い説明を持つポップオーバーが表示されます。

説明と例のテキストは、それぞれカスタム文字列（ `questionExplanation` および `questionMockText`それぞれ）を使用して設定できます。カウントウィジェットとポップオーバーの外観は、カスタムスタイル（ `numSidenotes` および `numSidenotesPopover`それぞれ）を使用して設定することもできます。

## 単一ページに複数のコレクションを追加する {#section_pjl_ptv_sy}

Livefyreでは、複数のコレクションを単一のページに追加できます。例えば、ページに3つのニュースストーリーが含まれている場合、Socialアプリの3つの個別の繰り返しを含めることができます。これを行うには、作成するサイトごとに個別 `ConvConfig` のオブジェクトを定義する必要があります。次に例を示します。

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
