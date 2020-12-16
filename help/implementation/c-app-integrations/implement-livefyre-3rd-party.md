---
description: Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。
seo-description: Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。
seo-title: Livefyreとサードパーティの統合の統合
solution: Experience Manager
title: LivefyreをCMSに統合する
uuid: 5a3e18e8-8568-45bb-9070-d0fa43dd819b
translation-type: tm+mt
source-git-commit: 2436c389cbe14c7d64dd8c0392a3e0f031468836
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---


# Livefyreのサードパーティとの統合の実装

Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。

BootstrapとストリームAPIを使用してLivefyreとソーシャルデータを利用することで、Livefyreアプリを一から作成できます。

認証が必要なLivefyreアプリについては、サポートされるサードパーティの認証プラットフォームについて、IDの統合（英語）を参照してください。

会話アプリ（コメント、チャット、ライブブログ、サイド）の実装：

1. アプリの統合を実行します。
a.CollectionMetaトークンを使用したコレクションの作成を参照してください。
b.Livefyre.jsの埋め込みコード構造を使用して、Livefyreアプリをサイトに統合します。

   * Livefyre.jsの埋め込みコード構造の使用方法について詳しくは、[アプリの埋め込み](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)を参照してください。

   * Comments Appの統合方法について詳しくは、[コメント](/help/using/c-about-apps/c-comments/c-comments.md)を参照してください。

   * チャットアプリの統合方法については、[チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md)を参照してください。

   * Live Blog Appの統合方法について詳しくは、[Live Blog](/help/using/c-about-apps/c-liveblog-app/c-liveblog-app.md)を参照してください。

   * Sidentsアプリの統合方法について詳しくは、[Sidents](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)を参照してください。

1. 認証統合を実行します。
a.ユーザー認証トークンを作成して、Livefyreにユーザーデータを渡して保存します。
b.サードパーティのユーザーおよび認証プラットフォームを統合する。 サポートされるプラットフォームのリストについては、[ID統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)を参照してください。

1. アプリのカスタマイズを実行します。 アプリのカスタマイズオプションを使用して、ブランドやスタイルに合わせたり、カスタム機能を追加したりできます。

ビジュアライゼーションアプリ(Map、Media Wall、Trending、Carousel、Filmstrip、Storify、Feature Card、Mosaic、Poling)を作成するには：

1. アプリの統合を実行します。
a.CollectionMetaトークンを使用したコレクションの作成を参照してください。
b.Livefyre.jsの埋め込みコード構造を使用して、Livefyreアプリをサイトに統合します。 Livefyre.jsの埋め込みコード構造の使用方法について詳しくは、[アプリの埋め込み](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)を参照してください。

   * マップアプリの統合方法について詳しくは、[マップ](/help/using/c-about-apps/c-map-app/c-map-app.md)を参照してください。

   * Media Wallアプリの統合方法について詳しくは、[Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md)を参照してください。

   * トレンド分析アプリの統合方法について詳しくは、[トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md)を参照してください。

1. 認証統合を実行します。
a.ユーザー認証トークンを作成して、ユーザーデータをLivefyreに渡して保存します。
b.サードパーティのユーザーおよび認証プラットフォームを統合する。 サポートされるプラットフォームのリストについては、[ID統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)を参照してください。

>[!NOTE]
>
>Livefyreは、Livefyre.jsを使用したカルーセル、Filmstrip、Storify、Feature Card、Mosaicおよびポーリングアプリをサポートしていません。

[アプリを作成](/help/using/c-about-apps/c-create-an-app.md)プロセスを使用して、これらのアプリを統合します。