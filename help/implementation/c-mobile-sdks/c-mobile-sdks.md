---
description: ネイティブモバイルアプリにLivefyreを追加します。
seo-description: ネイティブモバイルアプリにLivefyreを追加します。
seo-title: モバイル SDK
solution: Experience Manager
title: モバイル SDK
uuid: 84c7ca1c-3401-492a-bfa5-62b996947a44
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# モバイル SDK{#mobile-sdks}

ネイティブモバイルアプリにLivefyreを追加します。

モバイル実装には、行う予定のカスタマイズの範囲に応じて、次のいくつかのオプションを使用できます。

* モバイルWebアプリ
* Livefyre AndroidまたはiOS SDK
* HTTP API

## モバイルWebアプリ {#section_t2k_vpb_11b}

モバイルデバイスでWebページを開いた顧客は、縮小された画面サイズに合わせたスタイル設定や、タッチイベントを処理するための変更など、モバイル用に最適化されたLivefyreコンテンツストリームを自動的に取得します。

>[!NOTE]
>
>Android webViewでLivefyre appを使用する場合は、Android [WebSettings.setDomStorageEnabled](https://developer.android.com/reference/android/webkit/WebSettings.html) パラメーターをtrueに設定する必要があります。 localStorageが有効になっていない場合、LivefyreはユーザーをLivefyreアプリにログインできません。

Livefyreでは、モバイル用に最適化するために、コメント、ライブブログ、およびチャットアプリの機能セットに次のものが含まれるように制限されています。

* 投稿
* 編集
* Flag
* いいね！
* 返信
* リスナー数
* コメント数
* インライン保留モデレート
* ホバーカード
* 上位のコメント
* ホットスレッド
* Queue Comments

モバイルWebアプリで、発言者の名前をクリックすると、新しいページにカード情報が開きます。

## Livefyre Android SDKまたはiOS SDK {#section_zdz_spb_11b}

また、Livefyreは2つのモバイルSDKを提供します。ios SDKとAndroid SDKの2つのURLが含まれます。 これらのSDKは、データの送受信をより簡単にするために構築された、HTTPエンドポイントの周囲のラッパーです。 これらのSDKにはインターフェイスが備わっていないので、モバイルアプリ内でのコンテンツの表示方法と使用方法を柔軟に指定できます。

AndroidおよびiOS SDKは、コメント、ライブブログ、およびチャットに関して次の機能をサポートしています。

| iOSの機能： | Androidの機能： |
|--- |--- |
| <ul><li> 投稿 </li><li>編集 </li><li>Flag </li><li>いいね！ </li><li>返信 </li><li>ホットスレッド</li></ul> | <ul><li>投稿 </li><li>編集 </li><li>いいね！ </li><li>返信 </li><li>ホットスレッド</li></ul> |

## HTTP API {#section_yqb_qpb_11b}

HTTP APIは、Livefyreプラットフォーム上で会話やコンテンツを作成できるエンドポイントのグループです。 また、すべてのLivefyreを初期状態のストリームにパワーを与えます。 このソリューションは、エンジニアリングチームによる開発時間が長くなりますが、Livefyre製品スイートを使用する際の柔軟性が高まり、ネイティブモバイル統合が可能になります。

>[!IMPORTANT]
>
>**ユーザー認証トークンは** 、モバイルクライアント内で作成しないでください。作成すると、保護されていないアプリ内でLivefyre秘密ネットワークキーを公開する必要があります。 より堅牢で安全なソリューションについては、「ユーザー認証トークン」の節を参照してください。

