---
description: Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。
seo-description: Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。
seo-title: Livefyreとサードパーティ統合の統合
solution: Experience Manager
title: CMSへのLivefyreの統合
uuid: 5a3e18e8-8568-45bb-9070-d0fa43dd819b
translation-type: tm+mt
source-git-commit: 40cd8c2c89c17134bfcda510527dd6fff41400b5

---


# Livefyreとサードパーティ統合の実装

Livefyreアプリを最初から作成して、カスタマイズしたエクスペリエンスとデータのビジュアライゼーションを作成します。

BootstrapとStream APIを使用してLivefyreとソーシャルデータを利用することで、Livefyreアプリを一から作成できます。

認証を必要とするLivefyreアプリについては、サポートされるサードパーティ認証プラットフォームについて、ID統合を参照してください。

会話アプリ（コメント、チャット、ライブブログ、サイド）を実装するには：

1. アプリの統合を実行します。
a.CollectionMetaトークンを使用したコレクションの作成を参照してください。
b.Livefyre.js埋め込みコード構造を使用して、Livefyreアプリをサイトに統合します。

   * Livefyre.js埋め込みコード構造の使用方法について詳しくは、「アプリの埋め込み」を [参照してください](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)。

   * Comments appの統合方法について詳しくは、コメントを参照してく [ださい](/help/using/c-about-apps/c-comments/c-comments.md)。

   * Chat appの統合方法について詳しくは、「チャット」を参照してく [ださい](/help/using/c-about-apps/c-chat-app/c-chat-app.md)。

   * Live Blog appの統合方法について詳しくは、Live Blogを参照し [てください](/help/using/c-about-apps/c-liveblog-app/c-liveblog-app.md)。

   * Sidents appの統合方法について詳しくは、Sidentsを参照してく [ださい](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)。

1. 認証統合を実行します。
a.ユーザー認証トークンを作成して、Livefyreにユーザーデータを渡し、保存します。
b.サードパーティのユーザーおよび認証プラットフォームを統合します。 サポートされるプラットフォームのリストについては、「ID統 [合」を参照してくださ](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)い。

1. アプリのカスタマイズを実行します。 アプリのカスタマイズオプションを使用して、ブランドやスタイルに合わせたり、カスタム機能を追加したりできます。

ビジュアライゼーションアプリ(Map、Media Wall、Trending、Carousel、Filmstrip、Storify、Feature Card、Mosaic、Poling)を作成するには：

1. アプリの統合を実行します。
a.CollectionMetaトークンを使用したコレクションの作成を参照してください。
b.Livefyre.js埋め込みコード構造を使用して、Livefyreアプリをサイトに統合します。 Livefyre.js埋め込みコード構造の使用方法について詳しくは、「アプリの埋め込み」を [参照してください](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)。

   * Map appの統合方法について詳しくは、Mapを参照してく [ださい](/help/using/c-about-apps/c-map-app/c-map-app.md)。

   * Media Wallアプリの統合方法について詳しくは、Media wallを参照し [てください](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md)。

   * Trending appの統合方法について詳しくは、 [Trendingを参照してください](/help/using/c-about-apps/c-trending-app/c-trending-app.md)。

1. 認証統合を実行します。
a.ユーザーデータをLivefyreに渡して保存するユーザー認証トークンを作成します。
b.サードパーティのユーザーおよび認証プラットフォームを統合します。 サポートされるプラットフォームのリストについては、「ID統 [合」を参照してくださ](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)い。

>[!NOTE]
>
>Livefyreは、Livefyre.jsを使用したCarousel、Filmstrip、Storify、Feature Card、MosaicおよびPollingの各アプリをサポートしていません。
「アプリを作成」プロセスを使用して [これらのアプリを統合し](/help/using/c-about-apps/c-create-an-app.md) ます。