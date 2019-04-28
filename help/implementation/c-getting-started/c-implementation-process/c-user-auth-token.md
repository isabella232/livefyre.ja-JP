---
description: この節では、ユーザーのアプリケーションへのログインに必要なUser Authenticationトークンを作成するUserAuth JSONオブジェクトの生成方法について説明します。
seo-description: この節では、ユーザーのアプリケーションへのログインに必要なUser Authenticationトークンを作成するUserAuth JSONオブジェクトの生成方法について説明します。
seo-title: User Authトークン
solution: Experience Manager
title: User Authトークン
uuid: 6483dend-453c-4780- b19c-1d8041693617
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# User Authトークン{#user-auth-token}

この節では、ユーザーのアプリケーションへのログインに必要なUser Authenticationトークンを作成するUserAuth JSONオブジェクトの生成方法について説明します。

この節では、ユーザーのアプリケーションへのログインに必要なUser Authenticationトークンを作成するUserAuth JSONオブジェクトの生成方法について説明します。

トークンを作成するには、以下のパラメーターを渡すために使用する言語ライブラリを使用します。

| パラメータ | タイプ | 説明 |
|---|---|---|
| NetworkName | 文字列 *が必要です* | Livefyreネットワークの名前（Livefyreが提供します）。 |
| NetworkKey | 文字列 *が必要です* | この特定のネットワークの秘密鍵（Livefyreが提供します）。 |
| userId | 文字列 *が必要です* | ユーザー管理システムに保存されているユーザーのID（英数字、ダッシュ、アンダースコアおよびドット文字のみ）。 [a- zA- Z0-9_-.]). **注意:** userIdは一意である必要があります。 |
| expires | *必要な整数* | トークンの有効期限が今すぐ切れる場合（秒単位）。**注意:** この値は、floatとして渡すこともできます。生成されたJSON Webトークンは、この値をUNIXエポック時間に格納します。 |
| displayName | 文字列 *が必要です* | UIおよびコメントでこのユーザーを識別するテキスト。（最大文字数:50.） |

## Java {#section_b42_mjz_1cb}

```
network.buildUserAuthToken(userId, displayName, expires); 
 
```

## NodeJS {#section_c42_mjz_1cb}

```
network.buildUserAuthToken(userId, displayName, expires); 
```

## PHP {#section_d42_mjz_1cb}

```
$network->buildUserAuthToken(userId, displayName, expires); 
```

## Python {#section_e42_mjz_1cb}

```
network.build_user_auth_token(userId, displayName, expires) 
```

## ルビ {#section_f42_mjz_1cb}

```
network.build_user_auth_token(userId, displayName, expires) 
```

>[!NOTE]
>
>ネットワークキーはLivefyreの人口統計アカウントで共有されません。Livefyreが環境をプロビジョニングしたときにネットワークキーを受け取ります。このキーは非公開にする必要があります。

