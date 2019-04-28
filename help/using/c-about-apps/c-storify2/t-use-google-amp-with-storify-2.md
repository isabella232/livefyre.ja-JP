---
description: Livefyre APIを使用して、コンテンツをインタラクティブでSEOフレンドリーに維持するために、Storify2ページにGoogle AMP機能を追加します。
seo-description: Livefyre APIを使用して、コンテンツをインタラクティブでSEOフレンドリーに維持するために、Storify2ページにGoogle AMP機能を追加します。
seo-title: Google AMPをStorify2と連携させる
solution: Experience Manager
title: Google AMPをStorify2と連携させる
uuid: 40c9f083-7284-43ba- ae27-53b1ff9e3954
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Google AMPをStorify2と連携させる{#use-google-amp-with-storify}

Livefyre APIを使用して、コンテンツをインタラクティブでSEOフレンドリーに維持するために、Storify2ページにGoogle AMP機能を追加します。

Google AMPをStorify2と共に使用するには、Google AMPマークアップを使用してStorify2アプリ用のページを作成する必要があります。

AMPバージョンのアプリケーションは元のページからアップデートをリクエストします **（****amp- live- list** APIのpollIntervalパラメーターを使用して、更新リクエストの間隔を設定します）。AMPページの訪問者が最新のコンテンツをすばやく取得できるようにするには、Storify2AMPページに低キャッシュTTLを使用してください。

Storeify2アプリで投稿として含まれる画像以外のアセット（例えば、ビデオ）はAMP仕様で指定されているHTTPSを使用する必要があります。Google Cloudコンテンツ配信ネットワーク（CDN）を使用するAMP URLは、HTTPSを使用します。

Storify2とGoogle AMPを使用するには:

1. サイトにAMP検証済みテンプレートを作成します。
1. Google AMPページをカスタマイズするには、以下のGoogle AMP APIを1つ以上使用します。
   1. [amp-iframe](https://www.ampproject.org/docs/reference/components/amp-iframe) to customize the Storify 2 display
   1. [更新の時間間隔をカスタマイズ](https://www.ampproject.org/docs/reference/components/amp-live-list) するamp- live- list
   1. [amp- social- share](https://www.ampproject.org/docs/reference/components/amp-social-share) を使用してソーシャルシェアボタンを追加
1. 次のStorify2AMPページの内容を、 <style amp-custom> タグ: [https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css](https://cdn.livefyre.com/libs/liveblog-v2-component/amp.min.css)
1. 次のStorify2AMP Markup APIの内容をGoogle AMPテンプレートに含めます。 `https://api.livefyre.com/app-service/v4/bootstrap/{{APP_ID}}/amp` ここで{{APP_ ID}}はLivefyre StudioのStorify2アプリケーションのApp IDです。
   1. 唯一のクエリパラメーターはpollIntervalです。 **pollInterval**は、アプリケーションが更新をチェックする間隔（ミリ秒単位）です。
   1. URLには、最新の投稿（ツイート、ビデオなど）のコンテンツが含まれます。
   1. 投稿ページでは、Google AMPページを更新するために、このURLからコンテンツを取得する必要があります。
