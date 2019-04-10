---
description: null
seo-description: null
seo-title: Livefyreを他のAnalyticsツールと共に使用
solution: Experience Manager
title: Livefyreを他のAnalyticsツールと共に使用
uuid: 26c835f6- aced-41f7- aober-418afce8a829
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyreを他のAnalyticsツールと共に使用{#use-livefyre-with-other-analytics-tool}

解析ツールを使用して、Livefyreアプリとのユーザーインタラクションにデータを収集できます。Adobe Analyticsまたは選択したツールを使用できます。

（Adobe Analyticsではなく）任意のツールでLivefyreを使用するには、このページに説明されている手順に従います。

## 手順1:イベントハンドラーの設定 {#section_ngm_gzl_pdb}

Livefyreアプリを使用するページにイベントハンドラーを設定します。これにより、Analyticsで使用できるページ上のアプリからデータを収集できます。

ページにLivefyre. jsを追加して、イベントハンドラーを設定します。Livefyre. jsは非同期で読み込まれます。ファイルサイズを小さくし、読み込みパフォーマンスを向上させるために、解析はすぐには使用できません。データが利用可能になるまで、Analyticsオブジェクトをポーリングする必要があります。このスクリプトをページの任意の場所に配置するか、独自のコンパイルスクリプト内にバンドルします。

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

Livefyre. analytics機能をページで利用できるようになると、Analyticsの受信者関数を実装して、受信したイベントを任意の分析プロバイダーに送信できます。

1. Analyticsハンドラーは、個別に実行して送信する必要があるイベントの配列、またはプロバイダーがサポートしている場合はバッチとして送信する必要があります。
1. ハンドラーによって受け取ったイベントデータを、Analyticsプロバイダーが必要とする形式にマップします。
1. データをAnalyticsプロバイダーに送信します。

