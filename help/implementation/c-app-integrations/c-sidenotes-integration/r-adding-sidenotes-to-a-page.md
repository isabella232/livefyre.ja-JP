---
title: ページへのサイトの追加
description: ページへのサイトの追加
exl-id: 3ec089d0-3d51-4918-b510-d30ef645c9c2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# ページへのサインの追加{#adding-sidenotes-to-a-page}

Livefyreには、サイトをページ上に配置するためのいくつかの設定オプションが用意されています。

* セレクターオプションは、サイドを表示する要素を定義します。
* アンカーは、サイドマーク可能な要素を表します。
* カスタムスレッドコンテナを使用すると、サイド付けされた内容を基準にして、サイド付けスレッドの位置を定義できます。
* 「サイドの数」オプションを使用すると、指定した場所に追加されたサイドの数を表示できます。
* 複数の`ConvConfig`オブジェクトを使用して、1つのページの複数のストーリーにサイトを追加します。

## セレクター{#section_wyj_4sv_sy}

セレクターオプションを使用すると、サイドがページ上のコンテンツを検索できます。 このオプションの値を使用すると、使用する要素を動的に決定できます。 セレクター文字列（「#content p, #content img」など）、jQueryオブジェクト（`$(‘#content’)`など）、DOM要素の配列、または2つのプロパティを持つオブジェクトのいずれかです。含める/除外する。 次に、サイトアプリは、指定された要素またはページ上の一致する要素を使用します。 「以下を含む」および「以下を除外する」プロパティを使用する場合、サイドはまずページを解析し、「以下を含む」プロパティのすべての要素を検索した後、「以下を除外する」プロパティの要素を削除します。

## アンカー{#section_ehq_psv_sy}

アンカーは、コンテンツをサイマン化できる要素を表します。 アンカー要素には、テキストまたは画像を含めることができます。 アプリの構築中に渡されるセレクターオプションによって、アンカー要素が決まります。

## アンカーID {#section_rsb_rsv_sy}

ページ上のアンカーは`data-lf-anchor-id`を使用して識別されます。

アンカーのIDを自分で設定するには、アンカーにマップする要素に属性`data-lf-custom-anchor-id`を追加します。 これは、アンカーの自動検出が失敗する場合に便利です。

例えば、画像のデスクトップバージョンとモバイルバージョンで別のURLを使用する場合、2つの異なるURLが異なるアンカーにマップされる可能性があります。 代わりに、HTMLがモバイルとデスクトップの両方で同じ`data-lf-custom-anchor-id`を提供する場合、画像要素は単一のアンカーとして扱われます。

アンカーには、動的に決定される型がありますが、`data-lf-custom-anchor-type`属性を使用して明示的に設定することもできます。

>[!NOTE]
>
>定義済みリスト番号の値を使用する必要があります。

次のタイプを使用できます。

* **テキスト：** 1
* **画像：** 2
* **メディア：** 3
* **リッチ：** 4

`updateAnchors`メソッドを使用してページにSinefooksコンテンツを動的に追加する方法について詳しくは、[updateAnchorsメソッド](/help/implementation/c-app-integrations/c-sidenotes-integration/update-anchors-method.md)を参照してください。

## カスタムスレッドコンテナ{#section_jdh_btv_sy}

`threadContainerEl`オプションを使用して、サイド付きスレッドの場所を指定します。デフォルトの位置は指定できません。 デフォルトでは、アンカーがアクティブ化されると、サイトは関連するコンテンツの横または下に表示されます。 このデフォルト値を変更するには、`threadContainerEl`を使用して、スレッドを表示する要素を指定します。

このオプションのこの値は、最初の有効な要素のみが使用される以外は、セレクターオプションと同じように機能します。

## サイズの数{#section_pld_ntv_sy}

`numSidenotesEl`オプションを使用して、オプションのサイド数カウントウィジェットをページに埋め込みます。 このオプションは、セレクターオプションと同じ入力を受け付けますが、入力配列の最初の有効な要素のみを使用します。

ウィジェットは提供された要素または一致した要素を装飾し、Sidents入力アイコン、この位置に入力されたSidentの数、ヘルプアイコンを含みます。

ウィジェットをクリックすると、サイド名とその使用方法に関する短い説明の入ったポーバーが表示されます。

説明と例のテキストはどちらも、カスタム文字列（ `questionExplanation`と`questionMockText`）を使用して設定できます。 カウントウィジェットとポーバーの外観は、カスタムスタイル（ `numSidenotes`と`numSidenotesPopover`）を使用して設定することもできます。

## 複数のサイトのコレクションを1つのページに追加する{#section_pjl_ptv_sy}

Livefyreでは、複数のサイトコレクションを1つのページに追加できます。 例えば、ページに3つのニュースストーリーが含まれる場合、Sidents Appの3つの個別の繰り返しを含めることができます。 これを行うには、ビルドするSidentの各インスタンスに対して個別の`ConvConfig`オブジェクトを定義する必要があります。 例：

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
