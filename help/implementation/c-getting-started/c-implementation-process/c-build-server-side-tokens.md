---
description: collectionMetaトークンと認証トークンの構築に関するガイドです。
title: サーバー側トークンの構築
exl-id: f709b79e-9236-443e-b862-c7d281815d91
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 1%

---

# サーバー側トークンの構築{#build-server-side-tokens}

collectionMetaトークンと認証トークンの構築に関するガイドです。

Livefyreが要求を検証する際に使用するトークンを作成すると、Livefyreネットワークを更新できるのは自分だけです。

## CollectionMeta Token

トークンを作成して、新しい会話を作成し、既存の会話を表示する方法を説明します。

## 認証トークン

ユーザーの認証にトークンを構築する方法を説明します。ユーザー管理にJanrain Captureを使用しない場合は、統合プロセスで必要な手順です。

## ユーザー認証トークン{#section_l5l_hwt_bbb}

この節では、ユーザーのアプリへのログインに必要なユーザー認証トークンを作成するUserAuth JSONオブジェクトを生成する方法について説明します。

トークンを作成するには、希望の言語ライブラリを使用して次のパラメーターを渡します。

| パラメーター | タイプ | 説明 |
|---|---|---|
| networkName | 文字列&#x200B;*必須* | Livefyreネットワークの名前（Livefyreが提供します）。 |
| networkKey | 文字列&#x200B;*必須* | この特定のネットワークの秘密キー（Livefyreが提供）。 |
| userId | 文字列&#x200B;*必須* | ユーザー管理システムに保存されている、ログインするユーザーのID（英数字、ダッシュ、アンダースコアおよびドット文字のみ使用できます）。`[a-zA-Z0-9_-.]`)。 **注意：userId** は一意である必要があります。 |
| expires | 整数&#x200B;*必須* | トークンの有効期限が切れる時間（秒）。 **注意：** この値は、floatとして渡すこともできます。生成されたJSON Webトークンは、UNIXエポック時間にこの値を格納します。 |
| displayName | 文字列&#x200B;*必須* | UIおよびコメントでこのユーザーを識別するテキスト。 (最大文字数：50.) |
