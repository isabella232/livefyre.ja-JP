---
description: LivefyreアプリでBootstrapおよびStream APIを使用します。
seo-description: LivefyreアプリでBootstrapおよびStream APIを使用します。
seo-title: アプリの実装
solution: Experience Manager
title: アプリの実装
uuid: null
translation-type: tm+mt
source-git-commit: b737f2c6afb03d91041a317cc0afb790c3eadcb1

---

# アプリの実装 {#appimplementation}

使用例:Livefyre. jsメソッドを使用してLivefyreを自社のサードパーティCMSに統合したいと思います。

カスタムAEMコンポーネントまたはその他のCMS（SiteCatalyst、SiteCatalyst、Demandware）にLivefyreを実装するには、3つの方法があります。Designerアプリケーションの実装、API、実装およびサードパーティ認証の統合。

## Designerアプリケーションの実装 {#designerapp}

内容:Livefyreアプリケーションを最もシンプルかつ高速に統合できます。カスタマイズしたJavascript埋め込みコードを設計、設定および生成して、Liveyfreアプリを数分でページに統合できます。

方法: [Livefyreアプリの作成、プレビュー、公開および埋め込み](/help/using/c-about-apps/c-create-an-app.md)

例: [https://codepen.io/dharafyre/pen/bvGrLo](https://codepen.io/dharafyre/pen/bvGrLo)

### Livefyre. jsの実装 {#livefyrejsimp}

内容: [Livefyre. js](/help/implementation/c-livefyre.js.md) は、サイト上でアプリと認証を推進するコアライブラリです。グローバル `window.Livefyre` オブジェクトと単一のパブリックメソッドLivefyre. requireを定義し、Livefyreアプリケーションの埋め込みに役立つ他のLivefyre JavaScriptライブラリの読み込みや、サードパーティのUser Authプラットフォームとの統合に役立つ、他のLivefyre JavaScriptライブラリを読み込みます。

How:

* [CollectionMetaトークンを使用したコレクションの作成](/help/implementation/t-create-a-collectionmeta-token.md)

* アプリケーション統合を使用してアプリケーションをサードパーティ製CMSに統合する

例：

* コメントアプリ: [https://codepen.io/dharafyre/pen/oYoJdP](https://codepen.io/dharafyre/pen/oYoJdP)

* レビューアプリ: [https://codepen.io/dharafyre/pen/GXgvvd](https://codepen.io/dharafyre/pen/GXgvvd)

* メディアウォール: [https://codepen.io/dharafyre/pen/dNMPvM](https://codepen.io/dharafyre/pen/dNMPvM)

* SDKを使用した高度なカスタマイズについては、StreamHub SDKを参照してください。

## APIの実装 {#apiimplementation}

カスタマイズされたエクスペリエンスおよびデータの視覚化を作成するには、BootstrapおよびStream APIを使用してLivefyreとSocialデータを利用することで、Livefyreアプリケーションを一から作成できます。

## サードパーティ認証の統合 {#thirdpartyauth}

認証が必要なLivefyreアプリケーションについては、サードパーティ認証プラットフォームの [ID統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md) を参照してください。

## 顧客事例 {#customerexamples}

次のお客様は、LivefyreとサードパーティCMS統合を実装しています。

* [SSOツアーメディアウォール](https://www.pgatour.com/social-hub.html)

* [Timeout](https://www.timeout.com/london/restaurants/forest-bar-kitchen#tab_panel_3)
