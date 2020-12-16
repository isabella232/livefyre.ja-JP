---
description: Pingを使用して引き出しを行い、Livefyreをユーザー管理システムと同期させます。
seo-description: Pingを使用して引き出しを行い、Livefyreをユーザー管理システムと同期させます。
seo-title: Pingを使用したLivefyreとの同期（取り込み用）
solution: Experience Manager
title: Pingを使用したLivefyreとの同期（取り込み用）
uuid: 7b059064-1cca-46d7-8055-dfe59f493ac1
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---


# Pingを使用したプル{#sync-with-livefyre-using-ping-for-pull}のLivefyreとの同期

Pingを使用して引き出しを行い、Livefyreをユーザー管理システムと同期させます。

一般に、Webサイト/アプリのユーザーがプロファイル（表示名、アバターなど）を更新するときに&#x200B;***Ping*** Livefyreを実行し、Livefyre ***Pulls*** Livefyreを実行してプロファイルを取り込みます。

![](assets/Ping-for-Pull.png)

プルシーケンスのping:

1. お客様がLivefyreにpingリクエスト（更新対象のユーザーを含む）を送信します。
1. LivefyreがHTTP 200/Successを使用してPingを受け取ったことを確認するメッセージを表示します。
1. Livefyreはプルリクエストを処理します。
1. Livefyre queuesプルリクエスト
1. Livefyreは、更新されたユーザー情報を取り込むために、エンドポイントへのプル要求を実行します。
1. 顧客がプル応答を受け取り、検証します。
1. Livefyreは、プルエンドポイントに含まれる外部プロファイル情報でリモートプロファイルを更新します。

ユーザーがプロファイル情報を更新するたびにLivefyreにpingを送信する。 プル完了時間に対するpingは、ネットワークの負荷に応じて異なる場合がありますが、1 ～ 10分の間にユーザー情報が更新されます。 更新されたプロファイルの変更は、Livefyre Studio/ユーザー内で最初に表示されます。

更新されたプロファイル情報は、次の2つのイベントの後、Livefyre Appsに表示されます。

* ユーザーがログアウトした後、アプリケーションに再度ログインします。 userAuthTokenの表示名の値は、プルアップデートの場合はPingよりも優先されます。 ユーザーがログアウト/ログインすると、トークンが更新され、セッションが更新されます。

   プロファイル情報が更新されたときに新しいuserAuthTokensを生成するには、SSO authDelegateを使用してユーザーをログアウトし、バックグラウンドで再びログインします。

* コレクションに対するブートストラップの更新により、更新された情報が取り込まれます（最大5 ～ 10分ごと）。

ユーザプロファイルシステムの引き出し用にPingを実装するには：

1. [プルエンドポイントを構築します](#t_build_the_pull_endpoint)。

   >[!NOTE]
   >
   >Livefyreライブラリには、ユーザープロファイルを最新の状態に保つためのsyncUserメソッドが含まれています。 Livefyreライブラリを使用する場合は、次の2つの手順をスキップします。

1. [Studioでプルエンドポイントを登録します](#register_the_endpoint_with_studio)。
1. [Pingを構築します](#t_build_the_ping)。
1. [プル応答用のPingを構築します]。(#reference_n3x_pzb_mz)
