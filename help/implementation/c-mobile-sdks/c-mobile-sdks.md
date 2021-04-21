---
description: 追加Livefyreをネイティブのモバイルアプリケーションにアップロードします。
title: モバイル SDK
exl-id: e05001a4-6199-4d98-a661-123e031b657b
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# モバイル SDK{#mobile-sdks}

追加Livefyreをネイティブのモバイルアプリケーションにアップロードします。

モバイル実装には、行う予定のカスタマイズの範囲に応じて、いくつかのオプションを使用できます。

* モバイルWebアプリ
* Livefyre AndroidまたはiOS SDK
* HTTP API

## モバイルWebアプリ{#section_t2k_vpb_11b}

モバイルデバイスでWebページを開くと、画面サイズの縮小に合わせたスタイルや、タッチイベントに対応する変更など、モバイル向けに最適化されたLivefyreコンテンツストリームが自動的に取得されます。

>[!NOTE]
>
>Android WebViewでLivefyreアプリを使用する場合、Android [WebSettings.setDomStorageEnabled](https://developer.android.com/reference/android/webkit/WebSettings.html)パラメーターをtrueに設定する必要があります。 localStorageが有効になっていないと、LivefyreはユーザーをLivefyreアプリにログインできません。

モバイル用に最適化するために、Livefyreではコメント、ライブブログ、およびチャットアプリの機能セットを以下のように制限しています。

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

また、Livefyreは次の2つのモバイルSDKも提供しています。iOS SDKとAndroid SDK これらのSDKは、データの送受信を容易にするために構築された、アドビのHTTPエンドポイントを囲むラッパーです。 これらのSDKにはインターフェイスが備わっていません。これにより、モバイルアプリ内でのコンテンツの表示方法や使用方法を柔軟に指定できます。

AndroidおよびiOS SDKは、コメント、ライブブログ、チャットに関して次の機能をサポートしています。

| iOSの機能： | Androidの機能： |
|--- |--- |
| <ul><li> 投稿 </li><li>編集 </li><li>フラグ </li><li>いいね！ </li><li>返信 </li><li>ホットスレッド</li></ul> | <ul><li>投稿 </li><li>編集 </li><li>いいね！ </li><li>返信 </li><li>ホットスレッド</li></ul> |

## HTTP API {#section_yqb_qpb_11b}

HTTP APIは、Livefyreプラットフォーム上で会話やコンテンツを作成できるエンドポイントのグループです。 また、すべてのLivefyreのパワーを初期設定の状態で与えます。 このソリューションはエンジニアリングチームによる開発時間が長くなりますが、Livefyre製品スイートを使用する際の柔軟性が高まり、ネイティブモバイル統合も可能です。

>[!IMPORTANT]
>
>**ユーザー認証トークンはモバイルクライアント内に作成しないで** ください。作成するには、保護されていないアプリ内でLivefyre秘密ネットワークキーを公開する必要があります。より堅牢で安全なソリューションについては、「ユーザー認証トークン」の節を参照してください。
