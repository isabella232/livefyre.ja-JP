---
description: Livefyreアプリを一から作成して、カスタマイズしたエクスペリエンスとデータの視覚化を作成します。
seo-description: Livefyreアプリを一から作成して、カスタマイズしたエクスペリエンスとデータの視覚化を作成します。
seo-title: Livefyreとサードパーティ統合の統合
solution: Experience Manager
title: LivefyreのCMSへの統合
uuid: 5a3e18e8-8568-45bb-9070- d0fa43dd819b
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyreとサードパーティ統合の実装

Livefyreアプリを一から作成して、カスタマイズしたエクスペリエンスとデータの視覚化を作成します。

Livefyreアプリは、BootstrapおよびStream APIを使用してLivefyreとSocialデータを利用して作成できます。

認証を必要とするLivefyreアプリケーションの場合は、サポートされているサードパーティ認証プラットフォームに関する情報の"ID統合」を参照してください。

会話アプリ（コメント、チャット、Liveブログ、Sidees）を実装するには:

1. アプリ統合を実行します。
a. CollectionMetaトークンを使用したコレクションの作成を参照してください。
b. Livefyre. js埋め込みコード構造を使用してLivefyreアプリケーションをサイトに統合します。

   * Livefyre. js埋め込みコード構造の使用方法について詳しくは、アプリの埋め込みを [](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)参照してください。

   * コメントアプリを統合する方法について詳しくは [、コメント](/help/using/c-about-apps/c-comments/c-comments.md)を参照してください。

   * チャットアプリの統合方法については [、チャット](/help/using/c-about-apps/c-chat-app/c-chat-app.md)を参照してください。

   * Live Blogアプリの統合方法について詳しくは [、Live Blog](/help/using/c-about-apps/c-liveblog-app/c-liveblog-app.md)を参照してください。

   * Socialアプリを統合する方法については [、"Sideinding](/help/using/c-about-apps/c-sidenotes-app/c-sidenotes-app.md)」を参照してください。

1. 認証統合を実行します。
a. Livefyreにユーザーデータを渡すためのユーザー認証トークンを作成します。
b. サードパーティのユーザーおよび認証プラットフォームを統合します。サポートされているプラットフォームのリストについては [、"ID統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)」を参照してください。

1. アプリのカスタマイズを実行します。アプリのカスタマイズオプションを使用して、ブランドとスタイルに一致し、カスタム機能を追加できます。

ビジュアライゼーションアプリ（マップ、メディアウォール、トレンド、カルーセル、フィルムストリップ、ストーミング、機能カード、モザイク、ポール）を作成するには:

1. アプリ統合を実行します。
a. CollectionMetaトークンを使用したコレクションの作成を参照してください。
b. Livefyre. js埋め込みコード構造を使用してLivefyreアプリケーションをサイトに統合します。Livefyre. js埋め込みコード構造の使用方法について詳しくは、アプリの埋め込みを [](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)参照してください。

   * マップアプリを統合する方法について詳しくは [、マップ](/help/using/c-about-apps/c-map-app/c-map-app.md)を参照してください。

   * Mediaウォールアプリの統合方法について詳しくは [、Media Wall](/help/using/c-about-apps/c-media-wall-app/c-media-wall-app.md)を参照してください。

   * トレンドアプリの統合方法について詳しくは [、トレンド](/help/using/c-about-apps/c-trending-app/c-trending-app.md)を参照してください。

1. 認証統合を実行します。
a. ユーザー認証トークンを作成して、Livefyreにユーザーデータを渡すことができます。
b. サードパーティのユーザーおよび認証プラットフォームを統合します。サポートされているプラットフォームのリストについては [、"ID統合](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)」を参照してください。

>[!NOTE]
>
>LivefyreはLivefyre. jsを使用して、カルーセル、フィルムストリップ、Storify、Feature Card、Mosaic、およびポールアプリをサポートしていません。
アプリケーションを [作成](/help/using/c-about-apps/c-create-an-app.md) プロセスを使用して、これらのアプリを統合します。