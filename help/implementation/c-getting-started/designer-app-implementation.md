---
description: LivefyreアプリでBootstrapとStream APIを使用します。
seo-description: LivefyreアプリでBootstrapとStream APIを使用します。
seo-title: アプリの実装
solution: Experience Manager
title: アプリの実装
uuid: null
translation-type: tm+mt
source-git-commit: b737f2c6afb03d91041a317cc0afb790c3eadcb1

---

# アプリの実装 {#appimplementation}

使用例：お客様は、Livefyre.jsを使用してLivefyreをサードパーティCMSに統合したいと考えています。

WordPress、Sitecore、DemandWareのように、LivefyreをカスタムAEMコンポーネントまたは他のCMSに実装するには、3つの方法があります。Designerアプリの実装、API、実装およびサードパーティ認証の統合を参照してください。

## Designerアプリの実装 {#designerapp}

What:Livefyre appの最もシンプルで最も高速な統合方法です。 カスタマイズしたJavaScript埋め込みコードをデザイン、設定、生成して、LiveCycleアプリをページに統合できます。

方法：Livefyreア [プリの作成、プレビュー、公開および埋め込み](/help/using/c-about-apps/c-create-an-app.md)

例：https://codepen.io/dharafyre/pen/bvGrLo [](https://codepen.io/dharafyre/pen/bvGrLo)

### Livefyre.jsの実装 {#livefyrejsimp}

What:Livefyre.jsは [](/help/implementation/c-livefyre.js.md) 、サイト上のアプリと認証を強化するコアライブラリです。 これは、グローバルオ `window.Livefyre` ブジェクトと単一のパブリックメソッドLivefyre.requireを定義し、Livefyreアプリの埋め込みとサードパーティユーザー認証プラットフォームとの統合に役立つ他のLivefyre javaScriptライブラリの読み込みに使用できます。

方法：

* [CollectionMetaトークンを使用したコレクションの作成](/help/implementation/t-create-a-collectionmeta-token.md)

* アプリケーションの統合を使用したサードパーティCMSへのアプリケーションの統合

例：

* コメントアプリ：https://codepen.io/dharafyre/pen/oYoJdP [](https://codepen.io/dharafyre/pen/oYoJdP)

* レビューアプリ：https://codepen.io/dharafyre/pen/GXgvvd [](https://codepen.io/dharafyre/pen/GXgvvd)

* メディアウォール：https://codepen.io/dharafyre/pen/dNMPvM [](https://codepen.io/dharafyre/pen/dNMPvM)

* SDKを使用した高度なカスタマイズについては、StreamHub SDKを参照してください。

## APIの実装 {#apiimplementation}

カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成する場合、Bootstrap/Stream APIを使用してLivefyreとソーシャルデータを利用することで、Livefyreアプリを一から作成できます。

## サードパーティ認証の統合 {#thirdpartyauth}

認証が必要なLivefyreアプリについては、サードパーティ認証プ [ラットフォームの](/help/implementation/t-about-identity-integration/t-about-identity-integration.md) 「ID統合」を参照してください。

## 顧客事例 {#customerexamples}

以下のお客様は、Livefyreとサードパーティ製CMSの統合を実装しています。

* [PGAツアーメディアウォール](https://www.pgatour.com/social-hub.html)

* [TimeOut](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)
