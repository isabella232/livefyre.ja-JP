---
title: 他のAnalyticsツールとLivefyreを使用する
description: 他のAnalyticsツールとLivefyreを使用する
exl-id: da29e281-5095-4e99-a248-19390f2059a2
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# Livefyreを他のAnalyticsツールと共に使用する{#use-livefyre-with-other-analytics-tool}

解析ツールを使用して、Livefyre Appsでのユーザーの操作に関するデータを収集できます。 Adobe Analyticsや好みのツールを使用できます。

(Adobe Analyticsではなく)選択したツールでLivefyreを使用するには、このページに説明されている手順に従います。

## 手順1:イベントハンドラーの設定{#section_ngm_gzl_pdb}

Livefyre Appsを使用するページにイベントハンドラーを設定します。 これにより、そのページ上のアプリから分析に使用できるデータを収集できます。

Livefyre追加.jsをページに追加して、イベントハンドラーを設定します。 Livefyre.jsは非同期で読み込まれます。 ファイルサイズを小さくして読み込みパフォーマンスを向上させるために、分析をすぐに使用することはできません。 データが利用可能になるまで、analyticsオブジェクトをポーリングする必要があります。 このスクリプトは、ページ上の任意の場所に配置するか、独自のコンパイル済みスクリプト内にバンドルします。

```
/** 
 * Handler for Livefyre analytics batch events. 
 * @param {Array.<string>} events Array of events that have been fired since 
 * the last batch send. 
 */ 
function analyticsHandler(events) { 
  // Send to analytics 
  console.log(events); 
} 
 
var attempts = 0; 
 
function pollForAnalytics() { 
  if (Livefyre && Livefyre.analytics) { 
    Livefyre.analytics.addHandler(analyticsHandler); 
    return; 
  } 
  if (attempts === 10) { 
    return; 
  } 
  attempts++; 
  setTimeout(pollForAnalytics, 500); 
} 
 
pollForAnalytics(); 
```

## 手順2:handler関数の実装

ページでLivefyre.analyticsの機能が使用可能になったら、analyticsHandler関数を実装し、受け取ったイベントを任意のanalyticsプロバイダーに送信します。

1. 解析ハンドラーは、個別に、またはプロバイダーがサポートしている場合はバッチとして、繰り返し処理および送信する必要があるイベントの配列を受け取ります。
1. ハンドラーが受信したイベントデータを、Analyticsプロバイダーが必要とする形式にマップします。
1. データをAnalyticsプロバイダーに送信します。
