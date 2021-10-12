---
description: Livefyre をネイティブのiOSアプリに追加します。
title: Livefyre iOS SDK
exl-id: 961c41dc-fee8-480c-a189-a20a689e705f
source-git-commit: 3091db9d7b9611e26ad65c1432856c9465694e92
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 0%

---

# Livefyre iOS SDK{#livefyre-ios-sdk}

Livefyre をネイティブのiOSアプリに追加します。

このオープンソースライブラリを使用して、Livefyre サービスをネイティブのiOSアプリに統合します。 Livefyre StreamHub iOS SDK は、優れた AFNetworking ライブラリに基づいて、共通の API メカニズムの周りにシンレイヤーを提供します。

Livefyre は、この SDK に基づいて、2 つのiOSサンプルアプリを提供しています。コメントストリームとレビューサンプルアプリ

## Cocoa ポッドとしてのプロジェクトへの SDK の統合（推奨） {#section_qc5_h3v_zz}

StreamHub-iOS SDK をプロジェクトに追加する最も便利な方法は、CocoaPods を使用することです。 CocoaPods がない場合は、gem のインストール cocoapods とポッドの設定を実行します。 ポッドファイルの例を次に示します。

```
source 'https://github.com/Livefyre/cocoapods.git' 
source 'https://github.com/CocoaPods/Specs.git' 
  
platform :ios, :deployment_target => '6.0' 
  
pod 'StreamHub-iOS-SDK', '~> 0.3.0'
```

また、Specs リポジトリを CocoaPod のインストールに追加する必要があります（`~/.cocoapods/repos` ディレクトリにコピーされます）。

```
pod repo add livefyre https://github.com/Livefyre/cocoapods.git
```

アプリプロジェクトのルートにポッドファイルを作成し、上記のリポジトリを追加したら、次のコマンドを実行します。

```
pod install
```

これにより、すべての依存関係がダウンロードされ、MyApp.xcworkspace ファイルが作成されます。このファイルを今後使用して、Xcode でアプリプロジェクトを開く必要があります。

## Xcode サブプロジェクトとして {#section_jcm_g3v_zz}

または、リポジトリのクローンを作成します。

```
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
```

次に、Xcode プロジェクト (LFSClient.xcodeproj) をサブプロジェクトとしてアプリに追加します（Xcode のプロジェクトナビゲータペインに LFSClient.xcodeproj ファイルをドラッグするだけで簡単に実行できます）。

また、依存関係 ([AFNetworking](https://github.com/AFNetworking/AFNetworking)、[JSONKit](https://github.com/escherba/JSONKit)) に対しても同じ処理を行う必要があります。

## すべてを一度にダウンロード（非推奨） {#section_rpb_f3v_zz}

```
cd ~/dev 
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
cd StreamHub-iOS-SDK 
git submodule init 
git submodule update 
pod repo add livefyre https://github.com/Livefyre/cocoapods.git 
pod install 
cd examples/CommentStream 
pod install 
open CommentStream.xcworkspace
```

>[!NOTE]
>
>Xcode 6 でテストを実行するには、Pods-test-XCTest+HTTPStubSuiteCleanUp ポッド [https://stackoverflow.com/a/24651704](https://stackoverflow.com/a/24651704) の FRAMEWORK_SEARCH_PATHS に$(PLATFORM_DIR)/Developer/Library/Frameworks を追加する必要があります。

Livefyre の LFSTestConfig.plist ファイルが必要です。Livefyre はリクエストに応じて提供します。

## Xcode ドキュメント {#section_arl_b3v_zz}

[documentation](https://github.com/Livefyre/StreamHub-iOS-SDK) を参照するか、Xcode で「Documentation」ターゲットを構築できます（appledoc をインストールする必要があります）。

## 要件 {#section_m5l_13v_zz}

v0.2.0 以降の StreamHub iOS SDK バージョンには、iOS 6.0 以降が必要です。

## 付録（JSON のサポート） {#section_pcd_5hv_zz}

StreamHub-iOS SDK の内部をお探しの方は、(Appleが提供する NSSONSerialization の代わりに ) デフォルトの JSON パーサーとして [JSONKit](https://github.com/escherba/JSONKit) の変更版を使用していることにご注意ください。 これを行う必要があったのは、Appleが提供するパーサーは、システムで表現できる整数や浮動小数点数より大きい整数や浮動小数点数を含む JSON ファイルのデコードをサポートしていないからです。 アドビの JSONKit の修正バージョンでは、非常に大きな数を、対応するシステムの最大値に切り捨て、例外をスローします。
