---
description: 'null'
seo-description: 'null'
seo-title: SSL強制
solution: Experience Manager
title: SSL強制
uuid: e64af8c2-3ab6-4034-b385-0e552d828c6e
translation-type: tm+mt
source-git-commit: 7dc3ac6725a27460cecfa6051549da85370ca053

---


# SSL強制{#ssl-enforcement}

データを安全に保つため、HTTPは非推奨となります。HTTPSをお勧めします。 Adobe Livefyreは、2018年8月末までに、すべてのHTTP暗号および安全でないSSL/TLS暗号を完全に無効にします。 これは、ユーザーとユーザーのプライバシーを保護するために設計されたAdobe Standardです。

## 誰が影響を受けるの？ {#section_jf2_4yz_kcb}

これは、次のようなLivefyreのお客様に影響を与える可能性があります。

* CRM、CMS、WordPressまたは他のクライアントからのサーバー間呼び出し。
* モバイル統合（AndroidおよびiOSアプリ）
* カスタムアプリケーションまたはカスタムコード

## 必要なアクションについて{#section_unv_dc5_kcb}

1. Livefyreのすべてのお客様は、以下を含むすべてのトラフィックについて、HTTPS経由ですべてのAPIと通信する必要があります。

   * サーバー間統合（CRM、CMS、WordPressなど）
   * モバイル統合（AndroidおよびiOSアプリ）
   * カスタムアプリケーション（Streamhub SDKまたは直接コード化）。

1. サーバー間およびモバイルHTTPクライアントはTLS 1.2をサポートする必要があります。
1. ホスト名をからに変 `{*}.<network>.fyre.co` 更しま `<network>.{*}.fyre.co`す。 例えば、ホスト名は `example.network.fyre.co` example.fyre.co `network.`に変更されます。 次に例を示します。

   * `bootstrap.<network_name>.fyre.co` を   `<network_name>.bootstrap.fyre.co`

   * `quill.<network_name>.fyre.co` を   `<network_name>.quill.fyre.co`

   * `admin.<network_name>.fyre.co` を   `<network_name>.admin.fyre.co`

## 変更を行ったかどうかを知るにはどうしたらよいですか。 {#section_sqk_5d5_kcb}

既にHTTPSを使用している場合もありますが、特に次の場合は、Livefyreで再確認することをお勧めします。

* CMSまたはCRMからのサーバー間呼び出し。
* JavaScriptまたはモバイルのカスタムアプリに対するカスタムコードまたはSDKの使用。
* 統合が1年以上経っている場合。
* スタック内の技術が1年以上古い場合。

HTTPSを既に使用している場合でも、APIクライアントがTLS 1.2をサポートしていることを確認する必要があります。

## APIクライアントがTLS 1.2をサポートしていることを確認する方法を教えてください。 {#section_nd1_j25_kcb}

サイトの開発に携わる人は、次のことができます。

* クライアントソフトウェアを識別します。
* バージョンを識別します。
* APIクライアントがTLS 1.2をサポートしていることを確認するドキュメントを読みます。
* 必要に応じてデバッグモードをオンにします。

## TLS 1.2のJavaサポート {#section_lwn_rwk_ycb}

Java 8以降用のOracleおよびOpenJDK JVMは、デフォルトで、すべてのSSL接続にTLS 1.2を使用するように設定されています。 Java 8以降を使用する場合は、追加のアクションを実行する必要はありません。

Java 7以前のバージョンをご利用のお客様は、TLS 1.2を有効にする方法に関する公開ドキュメントを参照してください。

## ホスト名を変更する必要があるのはなぜですか。 {#section_d5q_p25_kcb}

LivefyreはドメインにSSL証明書を持ってい `{*}.<network>.fyre.co` ません。 単にURLをHTTPSに変更するだけで、アプリケーションが壊れます。

## 最新バージョンのLivefyre SDKにアップグレードする必要がありますか。 {#section_dw5_s25_kcb}

いいえ。代わりに、コードにパッチを適用できます。 コードにパッチを適用するには、静的な文字列を変更し、コードを再構築します。 HTTPクライアントが古い場合は、それもアップグレードするか、別のクライアントを使用する必要があります。

## これにはどのくらい時間がかかりますか。 {#section_lgd_v25_kcb}

この処理にかかる時間は、設定によって異なります。 簡単な実装を行う場合は、確認にほとんど時間がかかりません。 多くのカスタマイズを行っている場合は、更新されたコードをテストしてサーバーにデプロイするか、新しいアプリをアプリストアにデプロイする必要があります。 最良の結果を得るために、最初に作業を監査し、長期の作業を計画することをお勧めします。

## この作業を完了するタイムラインは何ですか。 {#section_kgk_w25_kcb}

Livefyreは、2018年8月末までにアドビのサービスに対するポート80(HTTP)を無効にし、443(HTTPS)への接続のみをサポートします。 HTTPを使用しようとするブラウザーや他のクライアントは失敗します。

## 私はいつこの仕事を終える必要がありますか。 {#section_rvb_x25_kcb}

2018年7月末までに、すべてのお客様がHTTPSを使用する必要があります。 この期限に間に合わない場合は、prioritysupport@livefyre.comで当社のチームにお問い合わせください。
