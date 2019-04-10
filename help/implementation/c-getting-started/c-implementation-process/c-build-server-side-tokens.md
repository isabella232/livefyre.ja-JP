---
description: CollectionMetaおよび認証トークンを構築するためのガイドです。
seo-description: CollectionMetaおよび認証トークンを構築するためのガイドです。
seo-title: ビルドサーバー側トークン
solution: Experience Manager
title: ビルドサーバー側トークン
uuid: 8313f26e-5ceb-414e- a61a-480bb7a8ba66
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# ビルドサーバー側トークン{#build-server-side-tokens}

CollectionMetaおよび認証トークンを構築するためのガイドです。

Livefyreがリクエストを検証するために使用するトークンを作成すると、Livefyreネットワークの更新のみが可能になります。

## CollectionMetaトークン

新しい既存の会話を作成して表示するトークンを作成する方法について説明します。

## 認証トークン

ユーザー管理用にJanrain Captureを使用しない場合に、統合プロセスの必要な手順を実行するためのトークンを構築する方法について説明します。

## User Authトークン {#section_l5l_hwt_bbb}

この節では、ユーザーのアプリケーションへのログインに必要なUser Authenticationトークンを作成するUserAuth JSONオブジェクトの生成方法について説明します。

トークンを作成するには、以下のパラメーターを渡すために使用する言語ライブラリを使用します。

| パラメータ | タイプ | 説明 |
|---|---|---|
| NetworkName | 文字列 *が必要です* | Livefyreネットワークの名前（Livefyreが提供します）。 |
| NetworkKey | 文字列 *が必要です* | この特定のネットワークの秘密鍵（Livefyreが提供します）。 |
| userId | 文字列 *が必要です* | ユーザー管理システムに保存されているユーザーのID（英数字、ダッシュ、アンダースコアおよびドット文字のみ）。 `[a-zA-Z0-9_-.]`）を参照してください。**注意:** userIdは一意である必要があります。 |
| expires | *必要な整数* | トークンの有効期限が今すぐ切れる場合（秒単位）。**注意:** この値は、floatとして渡すこともできます。生成されたJSON Webトークンは、この値をUNIXエポック時間に格納します。 |
| displayName | 文字列 *が必要です* | UIおよびコメントでこのユーザーを識別するテキスト。（最大文字数:50.） |

