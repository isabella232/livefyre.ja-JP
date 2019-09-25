---
description: 'null'
seo-description: 'null'
seo-title: 他のAnalyticsツールでのLivefyreの使用
solution: Experience Manager
title: 他のAnalyticsツールでのLivefyreの使用
uuid: 26c835f6-aced-41f7-aabe-418afce8a829
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 他のAnalyticsツールでのLivefyreの使用{#use-livefyre-with-other-analytics-tool}

解析ツールを使用して、Livefyre Appsでのユーザーの操作に関するデータを収集できます。 Adobe Analyticsまたは任意のツールを使用できます。

（Adobe Analyticsではなく）選択したツールでLivefyreを使用するには、このページで説明する手順に従います。

## 手順1:イベントハンドラーの設定 {#section_ngm_gzl_pdb}

Livefyre Appsを使用するページにイベントハンドラーを設定します。 これにより、分析に使用できる、そのページ上のアプリからデータを収集できます。

ページにLivefyre.jsを追加して、イベントハンドラーを設定します。 Livefyre.jsは非同期で読み込みます。 ファイルサイズを小さくして読み込みパフォーマンスを向上させるため、解析を今すぐ利用することはできません。 データが利用可能になるまで、Analyticsオブジェクトをポーリングする必要があります。 このスクリプトは、ページ上の任意の場所に配置するか、独自のコンパイル済みスクリプト内にバンドルします。

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

## 手順2:ハンドラー関数の実装

ページでLivefyre.analytics機能が使用可能になったら、analyticsHandler関数を実装して、受信したイベントを任意のAnalyticsプロバイダーに送信します。

1. 解析ハンドラーは、個別に、またはプロバイダーがサポートしている場合はバッチとして、繰り返し送信する必要があるイベントの配列を受け取ります。
1. ハンドラーが受け取ったイベントデータを、Analyticsプロバイダーが必要とする形式にマップします。
1. Analyticsプロバイダーにデータを送信します。

