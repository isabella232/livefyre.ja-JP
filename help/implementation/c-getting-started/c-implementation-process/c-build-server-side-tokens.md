---
description: collectionMetaトークンとauthトークンを構築するためのガイドです。
seo-description: collectionMetaトークンとauthトークンを構築するためのガイドです。
seo-title: サーバー側トークンの構築
solution: Experience Manager
title: サーバー側トークンの構築
uuid: 8313f26e-5ceb-414e-a61a-480bb7a8ba66
translation-type: tm+mt
source-git-commit: 5bf937c8cb1a9ca12216ee1884142b8787ff063e

---


# サーバー側トークンの構築{#build-server-side-tokens}

collectionMetaトークンとauthトークンを構築するためのガイドです。

Livefyreが要求を検証する際に使用するトークンを作成すると、Livefyreネットワークを更新できるのは自分だけです。

## CollectionMeta Token

トークンを作成して新しい会話を作成し、既存の会話を表示する方法を説明します。

## 認証トークン

ユーザー管理にJanrain Captureを使用しない場合は、統合プロセスで必要な手順である、ユーザー認証用のトークンの構築方法を説明します。

## ユーザー認証トークン {#section_l5l_hwt_bbb}

ここでは、ユーザーのアプリへのログインに必要なユーザー認証トークンを作成するUserAuth JSONオブジェクトを生成する方法について説明します。

トークンを作成するには、使用する言語ライブラリを使用して次のパラメーターを渡します。

| パラメーター | タイプ | 説明 |
|---|---|---|
| networkName | 文字列が必要 *です* | Livefyreネットワークの名前（Livefyreが提供）。 |
| networkKey | 文字列が必要 *です* | この特定のネットワークの秘密キー（Livefyreが提供）。 |
| userId | 文字列が必要 *です* | ユーザー管理システムに保存されているときにログインするユーザーのID（英数字、ダッシュ、アンダースコアおよびドット文字のみ使用できます）。 `[a-zA-Z0-9_-.]`)。 **** 注意：userIdは一意である必要があります。 |
| expires | 整数が必要 *です* | トークンの有効期限が今後切れる日時（秒）。 **** 注意：この値は、floatとして渡すこともできます。 生成されたJSON webトークンは、この値をUNIXエポック時間で保存します。 |
| displayName | 文字列が必要 *です* | UIおよびコメントでこのユーザーを識別するテキスト。 (最大文字数：50.) |

