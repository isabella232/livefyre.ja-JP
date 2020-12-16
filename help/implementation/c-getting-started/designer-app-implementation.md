---
description: Livefyre AppsでBootstrapとストリームAPIを使用します。
seo-description: Livefyre AppsでBootstrapとストリームAPIを使用します。
seo-title: アプリの実装
solution: Experience Manager
title: アプリの実装
uuid: null
translation-type: tm+mt
source-git-commit: b737f2c6afb03d91041a317cc0afb790c3eadcb1
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---

# アプリの実装{#appimplementation}

使用例：お客様は、Livefyre.jsを使用して、LivefyreをサードパーティのCMSに統合したいと考えています。

WordPress、Sitecore、DemandWareのように、カスタムAEMコンポーネントやその他のCMSにLivefyreを実装するには、3つの方法があります。Designerアプリの実装、API、実装およびサードパーティ認証の統合を参照してください。

## Designer App実装{#designerapp}

内容：Livefyre Appを統合する最もシンプルで最も高速な方法です。 カスタマイズしたJavaScript埋め込みコードを設計、設定および生成して、ページ上のLiveCycle Appを数分で統合できます。

方法：[Livefyreアプリの作成、プレビュー、公開、埋め込み](/help/using/c-about-apps/c-create-an-app.md)

例：[https://codepen.io/dharafyre/pen/bvGrLo](https://codepen.io/dharafyre/pen/bvGrLo)

### Livefyre.jsの実装{#livefyrejsimp}

内容：[Livefyre.js](/help/implementation/c-livefyre.js.md)は、サイトでアプリケーションと認証を強化するコアライブラリです。 グローバル`window.Livefyre`オブジェクトと単一のパブリックメソッドLivefyre.requireを定義します。これは、Livefyre Appsの埋め込みやサードパーティのユーザー認証プラットフォームとの統合に役立つ他のLivefyre JavaScriptライブラリの読み込みに使用できます。

方法：

* [CollectionMetaトークンを使用したコレクションの作成](/help/implementation/t-create-a-collectionmeta-token.md)

* アプリケーションの統合を使用して、アプリケーションをサードパーティ製CMSに統合する

例：

* コメントアプリ：[https://codepen.io/dharafyre/pen/oYoJdP](https://codepen.io/dharafyre/pen/oYoJdP)

* レビューアプリ：[https://codepen.io/dharafyre/pen/GXgvvd](https://codepen.io/dharafyre/pen/GXgvvd)

* メディアウォール：[https://codepen.io/dharafyre/pen/dNMPvM](https://codepen.io/dharafyre/pen/dNMPvM)

* SDKを使用した高度なカスタマイズについては、StreamHub SDKsを参照してください。

## API実装{#apiimplementation}

カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成する場合、BootstrapとストリームAPIを使用してLivefyreとソーシャルデータを消費することで、Livefyreアプリをゼロから作成できます。

## サードパーティ認証の統合{#thirdpartyauth}

認証が必要なLivefyreアプリについては、サードパーティの認証プラットフォームの[IDの統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)を参照してください。

## 顧客の例{#customerexamples}

以下のお客様は、Livefyreとサードパーティ製CMSの統合を実装しています。

* [PGAツアーメディアウォール](https://www.pgatour.com/social-hub.html)

* [TimeOut](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)
