---
description: null
seo-description: null
seo-title: SSLの実施
solution: Experience Manager
title: SSLの実施
uuid: e64af8c2-3ab6-4034- b385-0e552d828c6e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# SSLの実施{#ssl-enforcement}

データのセキュリティ保護を確実に行うために、HTTPSを使用することは推奨されません。Adobe Livefyreは、2018年8月末までにHTTPおよびセキュアSSL/TLS暗号を完全に無効にします。これは、ユーザーおよびユーザーのプライバシーを保護するために設計されたAdobe Standardです。

## 誰が影響を受けているか {#section_jf2_4yz_kcb}

これは、Livefyreのお客様に影響を与える可能性があります。

* CRM、CMS、Wordpressまたはその他のクライアントからのサーバー間呼び出し。
* モバイル統合（AndroidおよびiOSアプリ）
* カスタムアプリケーションまたはカスタムコード

## 必要な操作 {#section_unv_dc5_kcb}

1. すべてのLivefyreユーザーは、すべてのトラフィックについて、次のようなHTTPS経由のすべてのAPIと通信する必要があります。

   * サーバーからサーバーへの統合（CRM、CMS、Wordpressなど）
   * モバイル統合（AndroidおよびiOSアプリ）
   * カスタムアプリケーション（StreamHub SDKまたは直接コード化）

1. サーバーからサーバーおよびモバイルHTTPクライアントはTLS1.2をサポートする必要がある
1. ホスト名 `{*}.<network>.fyre.co``<network>.{*}.fyre.co`の変更例えば、ホスト名 `example.network.fyre.co` が `network.`example. fyre. coに変更されたとします。次に例を示します。

   * `bootstrap.<network_name>.fyre.co` to `<network_name>.bootstrap.fyre.co`

   * `quill.<network_name>.fyre.co` to `<network_name>.quill.fyre.co`

   * `admin.<network_name>.fyre.co` to `<network_name>.admin.fyre.co`

## 変更をおこなったかどうかを知るにはどうしますか。 {#section_sqk_5d5_kcb}

既にHTTPSを使用している可能性がありますが、Livefyreは次の場合に特に確認することをお勧めします。

* CMSまたはCRMからのサーバー間呼び出し。
* カスタムコードまたはJavaScriptまたはモバイルのカスタムアプリ用SDKを使用します。
* 統合が1年以上経っている場合。
* スタック内の技術が1年より古い場合。

HTTPSを使用している場合でも、APIクライアントがTLS1.2をサポートしていることを確認する必要があります。

## APIクライアントがTLS1.2をサポートしていることを確認する方法を教えてください。 {#section_nd1_j25_kcb}

サイトの開発で働いている人は、次のことができます。

* クライアントソフトウェアを特定します。
* バージョンを特定します。
* APIクライアントがTLS1.2をサポートするようにするためのドキュメントを読みます。
* 必要に応じてデバッグモードを有効にします。

## TLS1.2のJavaサポート {#section_lwn_rwk_ycb}

Java8以降のOracleおよびOpenJDK JVMは、デフォルトでTLS1.2をすべてのSSL接続に使用するように設定されています。Java8以降を使用する場合は、追加のアクションを実行する必要はありません。

TLS1.2を有効にする方法については、Java7以前のユーザーにお問い合わせください。

## ホスト名を変更する必要があるのはなぜですか。 {#section_d5q_p25_kcb}

Livefyreにはドメインに `{*}.<network>.fyre.co` SSL証明書はありません。URLをHTTPSに変更するだけでアプリケーションが破損します。

## 最新バージョンのLivefyre SDKにアップグレードする必要がありますか? {#section_dw5_s25_kcb}

いいえ。コードにはパッチを適用できます。コードにパッチを適用するには、いくつかの静的文字列を変更し、コードを再構築します。HTTPクライアントが古くなっている場合は、それをアップグレードしたり、別のものを使用したりする必要があります。

## この時間はどのくらいですか。 {#section_lgd_v25_kcb}

この所要時間は、設定によって異なります。シンプルな実装の場合、確認にはほとんど時間がかかりません。多数のカスタマイズがある場合は、更新されたコードをテストして、サーバーまたは新しいアプリケーションをApp Storeにデプロイする必要があります。最良の結果を得るには、作業の最初の監査を実行して、長期的な作業を計画できるようにすることをお勧めします。

## この作業を完了するためのタイムラインは何ですか。 {#section_kgk_w25_kcb}

Livefyreは、2018年8月末までにアドビのサービスにポート80（HTTP）を無効にし、443（HTTPS）への接続のみをサポートします。HTTPを使用しようとするブラウザーなどのクライアントは失敗します。

## この作業を終了する必要があるのはいつですか。 {#section_rvb_x25_kcb}

すべてのお客様は、2018年7月末までにHTTPSを使用する必要があります。このデッドラインを満たすことができない場合は、prioritysupport@livefyre.comでチームにお問い合わせください。
