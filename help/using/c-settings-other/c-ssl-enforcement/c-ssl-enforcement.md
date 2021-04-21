---
title: SSLの強制
description: SSLの強制
exl-id: 033e15d9-84f6-42d5-8457-04263dcbd11c
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 2%

---

# SSL強制{#ssl-enforcement}

データを安全に保つため、HTTPSは非推奨です。 AdobeのLivefyreは、2018年8月末までに、HTTP暗号化および安全でないすべてのSSL/TLS暗号化を完全に無効にします。 これは、ユーザーとユーザーのプライバシーを保護するために設計されたAdobe標準です。

## 誰が影響を受ける？{#section_jf2_4yz_kcb}

これは、次のようなLivefyreのお客様に影響を与える可能性があります。

* CRM、CMS、WordPressまたは他のクライアントからのサーバー間呼び出し。
* モバイル統合（AndroidおよびiOSアプリ）
* カスタムアプリケーションまたはカスタムコード

## 必要なアクションについて{#section_unv_dc5_kcb}

1. Livefyreのすべてのお客様は、HTTPS経由ですべてのAPIと通信する必要があります。この場合、次のようなトラフィックが発生します。

   * サーバー間統合（CRM、CMS、WordPressなど）
   * モバイル統合（AndroidおよびiOSアプリ）
   * カスタムアプリケーション（Streamhub SDKまたは直接コード化）

1. サーバー間およびモバイルHTTPクライアントはTLS 1.2をサポートする必要がある
1. ホスト名を`{*}.<network>.fyre.co`から`<network>.{*}.fyre.co`に変更します。 例えば、ホスト名`example.network.fyre.co`は`network.`example.fyre.co&quot;に変更されます。 例：

   * `bootstrap.<network_name>.fyre.co` を   `<network_name>.bootstrap.fyre.co`

   * `quill.<network_name>.fyre.co` を   `<network_name>.quill.fyre.co`

   * `admin.<network_name>.fyre.co` を   `<network_name>.admin.fyre.co`

## 変更を行ったかどうかを知る方法{#section_sqk_5d5_kcb}

既にHTTPSを使用している場合もありますが、Livefyreでは重複チェックをお勧めします。特に次の場合に使用します。

* CMSまたはCRMからのサーバー間呼び出し。
* JavaScriptまたはモバイルで、カスタムアプリのカスタムコードまたはSDKの使用。
* 統合が1年を超える場合。
* スタック内のテクノロジが1年以上古い場合。

既にHTTPSを使用している場合でも、APIクライアントがTLS 1.2をサポートしていることを確認する必要があります。

## APIクライアントがTLS 1.2をサポートしていることを確認するにはどうすればよいですか。{#section_nd1_j25_kcb}

サイトの開発に取り組む人は、次のことができます。

* クライアントソフトウェアを識別します。
* バージョンを識別します。
* ドキュメントを読み、APIクライアントがTLS 1.2をサポートしていることを確認してください。
* 必要に応じてデバッグモードをオンにします。

## TLS 1.2のJavaサポート{#section_lwn_rwk_ycb}

Java 8以降のoracleおよびOpenJDK JVMは、デフォルトでは、すべてのSSL接続にTLS 1.2を使用するように設定されています。 Java 8以降を使用する場合は、追加の操作を行う必要はありません。

Java 7以前のバージョンをご利用のお客様は、TLS 1.2を有効にする方法に関する公開ドキュメントを参照してください。

## ホスト名を変更する必要がある理由{#section_d5q_p25_kcb}

Livefyreは`{*}.<network>.fyre.co`ドメインにSSL証明書を持っていません。 単にURLをHTTPSに変更すると、アプリケーションが壊れます。

## Livefyre SDKの最新バージョンにアップグレードする必要がありますか。{#section_dw5_s25_kcb}

いいえ。代わりに、コードにパッチを適用できます。 コードにパッチを適用するには、静的な文字列を変更してコードを再構築します。 HTTPクライアントが古い場合は、それもアップグレードするか、別のクライアントを使用する必要があります。

## どれくらいかかる？{#section_lgd_v25_kcb}

所要時間は、設定に応じて異なります。 単純な実装がある場合、確認にほとんど時間がかかりません。 多くのカスタマイズを行っている場合は、更新されたコードをサーバーにテストして導入するか、新しいアプリをアプリストアに導入する必要があります。 最良の結果を得るために、長期の作業を計画できるように、作業の初期監査を行うことをお勧めします。

## この作業を完了する時間帯は何か。{#section_kgk_w25_kcb}

Livefyreは、2018年8月末までにアドビのサービスに対するポート80(HTTP)を無効にし、443(HTTPS)への接続のみをサポートします。 HTTPを使用しようとするブラウザーや他のクライアントは失敗します。

## 私はいつこの仕事を終える必要がありますか？{#section_rvb_x25_kcb}

2018年7月末までに、すべてのお客様がHTTPSを使用する必要があります。 この期限を満たせない場合は、prioritysupport@livefyre.comでアドビのチームにお問い合わせください。
