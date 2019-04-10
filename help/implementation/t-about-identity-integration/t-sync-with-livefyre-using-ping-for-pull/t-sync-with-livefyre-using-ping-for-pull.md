---
description: Pingを使用してLivefyreをユーザ管理システムと同期します。
seo-description: Pingを使用してLivefyreをユーザ管理システムと同期します。
seo-title: LivefyreとPingを使用してLivefyreと同期
solution: Experience Manager
title: LivefyreとPingを使用してLivefyreと同期
uuid: 7b059064-1cca-46d7-8055- dfe59f493ac1
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# LivefyreとPingを使用してLivefyreと同期{#sync-with-livefyre-using-ping-for-pull}

Pingを使用してLivefyreをユーザ管理システムと同期します。

一般に ***、*** Webサイトやアプリケーションのユーザーがプロファイル（表示名、アバターなど）を更新し、Livefyre ***がそのユーザーの更新プロファイルを取り込む*** たびにPing Livefyreが使用されます。

![](assets/Ping-for-Pull.png)

Ping for Pull Sequence:

1. 顧客はLivefyreにPingリクエストを送信します（更新するユーザーを含む）。
1. HTTP200/Successでpingの受信を確認します。
1. Livefyreプロセスのプル要求。
1. Livefyre Queuesのプル要求。
1. Livefyreは、エンドポイントにプル要求を実行して、更新されたユーザー情報を取り込みます。
1. 顧客はプルレスポンスを受け取り、検証を行います。
1. Livefyreは、プルエンドポイントに含まれる外部プロファイル情報を使用してリモートプロファイルを更新します。

Ping Livefyreユーザーがプロファイル情報を更新するたびに、PingのPingの完了時間はネットワークの負荷によって異なりますが、1~10分の間にユーザー情報が更新されます。プロファイル変更がLivefyre Studio/ユーザー内で最初に表示されます。

次の2つのイベントの後、プロファイル情報がLivefyreアプリケーションに表示されます。

* ユーザーがログアウトしてから、アプリにログインします。プルアップのPingよりもUserAuthTokenの表示名の値が優先されます。ユーザーがログアウトまたはログインすると、トークンが更新され、セッションが更新されます。

   プロファイル情報の更新時に新しいUserAuthTokensを生成するには、SSO AuthDelegateを使用してユーザーをバックグラウンドで再度ログアウトします。

* コレクションのブートストラップの更新により、更新された情報が取得されます（5~10分ごと）。

Ping for your User ProfileシステムのPingを実装するには:

1. [プルエンドポイントを構築](#t_build_the_pull_endpoint)します。

   >[!NOTE]
   >
   >Livefyreライブラリには、ユーザープロファイルを最新の状態に保つためのSyncUserメソッドが含まれています。Livefyreライブラリを使用する場合は、次の2つの手順をスキップします。

1. [Studioでプルエンドポイントを登録](#register_the_endpoint_with_studio)します。
1. [Pingを構築](#t_build_the_ping)します。
1. [Ping for Pull Response]を構築します。（# reference_ n3x_ pzb_ mz）
