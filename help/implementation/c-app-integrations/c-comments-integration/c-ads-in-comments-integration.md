---
description: コメントストリームに広告を挿入します。
seo-description: コメントストリームに広告を挿入します。
seo-title: コメントの広告
solution: Experience Manager
title: コメントの広告
uuid: f8d6372f-4468-4884- a384-116180b4c748
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# コメントの広告{#ads-in-comments}

コメントストリームに広告を挿入します。

## コメントの広告 {#topic_CDD2ACF16AED4DE782725EE90089C04E}

コメントストリームに広告を挿入します。

コメントのLivefyre広告を使用すると、コメントストリームに広告を挿入したり、広告がストリームに表示される頻度を定義したり、同期広告と非同期広告の両方のデリゲートを作成したりできます。

Livefyreは、広告管理ソリューションプロバイダーを使用して広告を挿入できるコンテナを提供します。

広告を挿入するには、Livefyreの2つの値を渡します。

* コメントストリームに広告を挿入する頻度
* 適切な広告を提供する関数。

>[!NOTE]
>
>広告は、広告の配置がビューポートにある場合にのみレンダリングされます。広告は、（スレッド内ではなく）親コメントの後にのみ表示され、ユーザーはこれらの広告にコメントできません。このAPIでは、広告を配置する要素のサイズを指定することはできません。

## 統合{#concept_C99029E618EC49779E3117D2C303E4F1}

この機能を使用するには、広告を配置するページにdiv要素を作成し、広告プロバイダーからHTMLを渡します。

Livefyreには2つの広告配置タイプがあります。同期および非同期。どちらのタイプでも、広告の位置が表示されているようなページをスクロールする場合にのみ、広告が読み込まれます。また、両方ともDOM要素（iFrameまたはdiv）を返す必要があります。

広告を取得するには、外部サービスへの非同期呼び出しの間に、同期メソッド呼び出しをローカルリポジトリに呼び出します。

### 同期

同期プレースメントを作成するには、デリゲートに広告を含め、広告要素自体を返します。ローカルリポジトリへの同期メソッド呼び出し。独自の広告生成を処理できます。

### 非同期

非同期メソッドでは、広告プロバイダーを呼び出す前に、要素をDOMに挿入する必要があります。次に、プロバイダーは送信する広告を決定してから返します。

非同期広告を実装するには、広告が配置される要素を返すデリゲートと、広告の配置を実行するコールバックを作成します。委任に返される要素には、広告の一意のIDを指定する必要があります。このコールバックは、一意のIDによって提供された要素に広告を挿入します。

>[!NOTE]
>
>広告プロバイダーによっては、コールバックが異なる動作になります。

ページがロードされると、コメント内の広告は委任に到達し、要素を挿入し、そのコールバックを呼び出して（以前に定義された）広告を広告と共に更新します。

## パラメーター {#concept_D7E27B0C21EF405C8EB826083DBB53EC}

この呼び出しで使用できるパラメーターは次のとおりです。

広告オブジェクトの場合:

* **delay:****（オプション） integer** -最初の広告が表示されるコメントの数を設定します。初期設定は10です。
* **頻度:（オプション） integer** -後続の各広告が表示されるコメントの数を設定します。次に例を示します。2つ目のコメントごとに広告を表示するには、2を入力します。初期設定は10です。
* **delegate:*****required*関数** -広告をコメントストリームに挿入するために呼び出される関数。

delegateオブジェクトは、同期広告呼び出しと非同期広告呼び出しの両方をサポートしています。delegate関数に渡されるパラメーターには、次のものが含まれます。

* **title:****string** -コレクションのタイトル。
* **タグ:****array** -コレクションに関連付けられているタグのリスト。
* **id:****string** -コレクションの記事識別子。
* **url:****string** -コレクションのURL。
* **NetworkID:****string** -コレクションのネットワークID。
* **siteID:****int** -コレクションのサイトID。

これらの項目は、例のTitConfigオブジェクトを介して渡されます。詳しくは、 [「はじめに」](/help/implementation/c-app-integrations/c-comments-integration/c-comments-integration.md#section_656AAC97903F485084650269A6C7EBCE) の節を参照してください。

### 同期

delegateは、次を含むオブジェクトを返します。

* **エレメント:*****required*DOM element** -アプリケーションに挿入する広告を含む要素。

**非同期**:delegateは、次を含むオブジェクトを返します。delegateは、次の2つのプロパティを含むオブジェクトを返します。エレメントとコールバック:

* **エレメント:*****required*DOM element** -アプリケーションに挿入する広告を含む要素。
* **callback:*****required*関数** -上記のDOM要素への広告の挿入を処理するコールバック。

`Conv` オブジェクトの場合、広告セクションのタイトルを示す文字列を渡すことができます。

* **文字列:****（オプション）** -広告のヘッダーテキストをカスタマイズするために使用します。デフォルトでは「スポンサード」です。

## 同期の例 {#concept_E733E4431D9948638B8102ADE398735F}

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
<div id="livefyre-app-17"></div> 
<script> 
  
(function() { 
  var nextSlotId = 1; 
  function generateNextSlotName() { 
    var id = nextSlotId++; 
    return 'adslot' + id; 
  } 
  Livefyre.require(['fyre.conv#qa'], function(Conv) { 
    new Conv({ 
      network: 'qa-0.fyre.co', 
        env: 'qa', 
        strings: { 
          'sponsored': 'Sponsored by: Livefyre' 
        } 
      }, [{ 
        app: 'main', 
        siteId: '291206', 
        articleId: '17', 
        el: 'livefyre-app-17', 
        ad: { 
          delay: 5, 
          frequency: 10, 
          delegate: function(data) { 
            var elem = document.createElement('div'); 
            elem.id = generateNextSlotName(); 
            return { 
              element: elem 
            }; 
          } 
        } 
      }], function (widget) { 
        // Initialize or Auth 
      }); 
    }); 
}()); 
</script>
```

## 非同期の例 {#concept_16B798C7EB20423DAA53ACCC71540051}

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
<div id="livefyre-app-17"></div> 
<script> 
  
(function() { 
  var nextSlotId = 1; 
  function generateNextSlotName() { 
    var id = nextSlotId++; 
    return 'adslot' + id; 
  } 
  function insertSlot(slotName) { 
    var adElem = document.createElement("img"); 
    var ad = "https://your-ad-here.com/great-ad-image.image"; 
    adElem.setAttribute("src", ad); 
    document.getElementById(slotName).appendChild(adElem); 
  } 
  Livefyre.require(['fyre.conv#qa'], function(Conv) { 
    new Conv({ 
      network: 'qa-0.fyre.co', 
        env: 'qa', 
        strings: { 
          'sponsored': 'Sponsored by: Livefyre' 
        } 
      }, [{ 
        app: 'main', 
        siteId: '291206', 
        articleId: '17', 
        el: 'livefyre-app-17', 
        ad: { 
          delay: 5, 
          frequency: 10, 
          delegate: function(data) { 
            var elem = document.createElement('div'); 
            elem.id = generateNextSlotName(); 
            return { 
              element: elem, 
              callback: function() { 
                insertSlot(elem.id); 
              } 
            }; 
          } 
        } 
      }], function (widget) { 
        // Initialize or Auth 
      }); 
    }); 
}()); 
</script>
```
