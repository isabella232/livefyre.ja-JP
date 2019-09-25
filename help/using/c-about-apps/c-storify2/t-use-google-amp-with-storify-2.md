---
description: Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEO対応に保ちます。
seo-description: Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEO対応に保ちます。
seo-title: Storify 2でのGoogle AMPの使用
solution: Experience Manager
title: Storify 2でのGoogle AMPの使用
uuid: 40c9f083-7284-43ba-ae27-53b1ff9e3954
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Storify 2でのGoogle AMPの使用{#use-google-amp-with-storify}

Livefyre APIを使用してGoogle AMP機能をStorify 2ページに追加し、コンテンツをインタラクティブでSEO対応に保ちます。

Storify 2でGoogle AMPを使用するには、Google AMPマークアップを使用するStorify 2アプリ用のページを作成する必要があります。

AppのAMPバージョンは、元のページから更新を要求します( **amp-live-list****** APIのpollIntervalパラメーターを使用して、更新要求の間隔を設定します)。 AMPページの訪問者が最新のコンテンツをすばやく取得できるように、Storify 2 AMPページのキャッシュTTLを低く抑えます。

Storify 2アプリの投稿として含まれる画像以外のアセット（例えば、ビデオ）は、AMP仕様で指定されたHTTPSを使用する必要があります。 Google cloudコンテンツ配信ネットワーク(CDN)を使用するAMP URLはHTTPSを使用します。

Storify 2でGoogle AMPを使用するには：

1. AMP検証済みのテンプレートをサイトに作成します。
1. 次の1つ以上のGoogle AMP APIを使用してGoogle AMPページをカスタマイズします。
   1. [amp-iframe](https://www.ampproject.org/docs/reference/components/amp-iframe) :Storify 2表示をカスタマイズ
   1. [amp-live-list](https://www.ampproject.org/docs/reference/components/amp-live-list) ：更新の時間間隔をカスタマイズ
   1. [amp-social-share](https://www.ampproject.org/docs/reference/components/amp-social-share) （ソーシャルシェアボタンの追加）
1. 次のStorify 2 AMPページのコンテンツを、 <style amp-custom> タグ：https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css [](https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css)
1. 次のStorify 2 AMPマークアップAPIの内容をGoogle AMPテンプレートに含めます。{{ `https://api.livefyre.com/app-service/v4/bootstrap/{{APP_ID}}/amp` APP_ID}}は、Livefyre studioのStorify 2アプリのアプリIDです。
   1. 唯一のクエリパラメー **ターはpollInterval**（アプリが更新を確認する間隔）です（ミリ秒単位で設定）。
   1. URLには、最新の投稿（ツイート、ビデオなど）のコンテンツが含まれます。
   1. 発行者ページは、Google AMPページを更新するのに必要な回数だけ、このURLからコンテンツを取得する必要があります。
