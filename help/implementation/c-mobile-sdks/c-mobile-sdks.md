---
description: ネイティブモバイルアプリにLivefyreを追加します。
seo-description: ネイティブモバイルアプリにLivefyreを追加します。
seo-title: モバイルSDK
solution: Experience Manager
title: モバイルSDK
uuid: 84c7ca1c-3401-492a- bfa5-62b996947a44
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# モバイルSDK{#mobile-sdks}

ネイティブモバイルアプリにLivefyreを追加します。

実行する予定のカスタマイズ範囲に応じて、モバイル導入に使用できるオプションはいくつかあります。

* モバイルWebアプリ
* Livefyre AndroidまたはiOS SDK
* HTTP API

## モバイルWebアプリ {#section_t2k_vpb_11b}

モバイルデバイス上でWebページを開くお客様には、モバイル用に最適化されたLivefyreコンテンツストリームが自動的に取得されます。このコンテンツストリームは、タッチイベントを処理するための画面サイズや変更の低減に合わせて最適化されます。

>[!NOTE]
>
>Android WebViewでLivefyreアプリケーションを使用する場合、Android [WebSettings. setDomStorageEnabled](https://developer.android.com/reference/android/webkit/WebSettings.html) パラメーターをtrueに設定する必要があります。LocalStorageが有効になっていない場合、LivefyreはLivefyreアプリケーションにユーザーをログインできません。

モバイル用に最適化するために、Livefyreでは、コメント、ライブブログおよびチャットアプリの機能セットを次のように制限しています。

* Post
* 編集
* フラグ
* いいね!
* Reply
* リスナー数
* コメント数
* インライン保留中のモデレート
* ホバーカード
* 上位のコメント
* ホットスレッド
* Queue Comments

モバイルWebアプリで、作成者の名前をクリックすると、新しいページにhoverardの情報が表示されます。

## Livefyre Android SDKまたはiOS SDK {#section_zdz_spb_11b}

Livefyreも2つのモバイルSDKを提供しています。iOS SDKおよびAndroid SDK。これらのSDKは、HTTPエンドポイントの周りにラッパーを備えており、データの送受信の簡単な方法を提供します。これらのSDKにはインターフェイスがありません。これにより、モバイルアプリ内でコンテンツの表示と使用を柔軟に柔軟に行うことができます。

AndroidおよびiOS SDKでは、コメント、ライブブログおよびチャットの次の機能がサポートされています。

| iOSの機能: | Android機能: |
|--- |--- |
| <ul><li> Post </li><li>編集 </li><li>フラグ </li><li>いいね! </li><li>Reply </li><li>ホットスレッド</li></ul> | <ul><li>Post </li><li>編集 </li><li>いいね! </li><li>Reply </li><li>ホットスレッド</li></ul> |

## HTTP API {#section_yqb_qpb_11b}

HTTP APIは、Livefyreプラットフォーム上の会話やコンテンツを作成できるエンドポイントのグループです。また、すべてのLivefyreがデフォルトのストリームから提供されます。このソリューションにはエンジニアリングチームからのさらなる開発時間が必要ですが、Livefyre製品スイートを使用する際は柔軟性が高くなり、ネイティブモバイル統合が可能になります。

>[!IMPORTANT]
>
>**モバイルクライアント内にユーザー認証トークン** を作成しないでください。これは、保護されていないアプリケーション内にLivefyreシークレットネットワークキーを公開する必要があるからです。より強力で安全なソリューションについては、「ユーザー認証トークン」の節を参照してください。

