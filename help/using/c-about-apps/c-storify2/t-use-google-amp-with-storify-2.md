---
description: Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEOフレンドリーに保ちます。
seo-description: Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEOフレンドリーに保ちます。
seo-title: Storify 2でGoogle AMPを使用
solution: Experience Manager
title: Storify 2でGoogle AMPを使用
uuid: 40c9f083-7284-43ba-ae27-53b1ff9e3954
translation-type: tm+mt
source-git-commit: 65d931e5bd04964db44f8e3a0e000ecec2652893
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---


# Storify 2{#use-google-amp-with-storify}でGoogle AMPを使用

Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEOフレンドリーに保ちます。

Storify 2でGoogle AMPを使用するには、Google AMPマークアップを含むStorify 2 App用のページを作成する必要があります。

アプリのAMPバージョンは、元のページから更新を要求します(更新要求の間隔を設定するには、**amp-live-リスト** APIの&#x200B;**pollInterval**&#x200B;パラメーターを使用します)。 AMPページ上の訪問者が最新のコンテンツをすばやく取得できるように、Storify 2 AMPページのキャッシュ低下TTLを維持します。

Storify 2アプリの投稿として含まれる画像以外のアセット（例えば、ビデオ）は、AMP仕様で指定されたHTTPSを使用する必要があります。 Google Cloud Content Network(CDN)を使用するAMP URLはHTTPSを使用します。

Storify 2でGoogle AMPを使用するには：

1. サイトでAMP検証済みのテンプレートを作成します。
1. 次のGoogle AMP APIの1つ以上を使用して、Google AMPページをカスタマイズします。
   1. [amp-](https://www.ampproject.org/docs/reference/components/amp-iframe) iframeを使用してStorify 2表示をカスタマイズ
   1. [amp-live-](https://www.ampproject.org/docs/reference/components/amp-live-list) list更新の時間間隔をカスタマイズ
   1. [amp-social-](https://www.ampproject.org/docs/reference/components/amp-social-share) shareを使用して、ソーシャルシェアボタンを追加する
1. `<style amp-custom>`タグ内のStorify 2ページのCSSに、以下のStorify 2 AMPページのコンテンツを含めます。[https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css](https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css)
1. 次のStorify 2 AMPマークアップAPIのコンテンツをGoogle AMPテンプレートに含めます。`https://api.livefyre.com/app-service/v4/bootstrap/{{APP_ID}}/amp` {{APP_ID}}は、Livefyre StudioのStorify 2アプリのアプリIDです。
   1. 唯一のクエリパラメーターは&#x200B;**pollInterval**&#x200B;です。これは、アプリが更新をチェックする間隔（ミリ秒単位）です。
   1. URLには、最新の投稿（ツイート、ビデオなど）のコンテンツが含まれます。
   1. 発行者ページは、Google AMPページを更新するのと同じ頻度で、このURLからコンテンツを取得する必要があります。
