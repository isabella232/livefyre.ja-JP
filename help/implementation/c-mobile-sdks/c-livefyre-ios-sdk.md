---
description: 追加LivefyreをネイティブのiOSアプリケーションにアップロードします。
seo-description: 追加LivefyreをネイティブのiOSアプリケーションにアップロードします。
seo-title: Livefyre iOS SDK
solution: Experience Manager
title: Livefyre iOS SDK
uuid: bfdef31a-49fc-4b25-b0c5-300f27067302
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---


# Livefyre iOS SDK{#livefyre-ios-sdk}

追加LivefyreをネイティブのiOSアプリケーションにアップロードします。

このオープンソースライブラリを使用して、LivefyreサービスをネイティブiOSアプリに統合します。 Livefyre StreamHub iOS SDKは、優れたAFNetworkingライブラリに基づき、共通のAPIメカニズムの周りにシンレイヤーを提供します。

また、このSDKに基づく2つのiOSサンプルアプリを提供しています。コメントストリームとレビューサンプルアプリ

## SDKをプロジェクトにCocoa Podとして統合する（推奨） {#section_qc5_h3v_zz}

プロジェクトにStreamHub-iOS SDKを追加する最も便利な方法は、CocoaPodを使用することです。 CocoaPodがない場合は、gemのインストール用のココアポッドとポッドの設定を実行します。 以下にポッドファイルの例を示します。

```
source 'https://github.com/Livefyre/cocoapods.git' 
source 'https://github.com/CocoaPods/Specs.git' 
  
platform :ios, :deployment_target => '6.0' 
  
pod 'StreamHub-iOS-SDK', '~> 0.3.0'
```

また、CocoaPodのインストールにSpecsリポジトリを追加する必要があります（これにより`~/.cocoapods/repos`ディレクトリにコピーされます）。

```
pod repo add livefyre https://github.com/Livefyre/cocoapods.git
```

アプリプロジェクトのルートにポッドファイルを作成し、上記のリポジトリを追加したら、次を実行します。

```
pod install
```

これにより、すべての依存関係がダウンロードされ、MyApp.xcworkspaceファイルが作成されます。これ以降は、Xcodeでアプリプロジェクトを開く際に使用する必要があります。

## Xcodeサブプロジェクトとして{#section_jcm_g3v_zz}

または、リポジトリをコピーします。

```
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
```

次に、Xcodeプロジェクト(LFSClient.xcodeproj)をサブプロジェクトとしてアプリに追加します（LFSClient.xcodeprojファイルをXcodeのプロジェクトナビゲーターペインにドラッグするだけで簡単に行えます）。

また、任意の依存関係([AFNetworking](https://github.com/AFNetworking/AFNetworking)、[JSONKit](https://github.com/escherba/JSONKit))に対しても同じ処理を行う必要があります。

## すべてを一度にダウンロード（推奨しません） {#section_rpb_f3v_zz}

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
>Xcode 6でテストを実行するには、Pod-test-XCTest+OHTTPStubSuiteCleanUpポッド[https://stackoverflow.com/a/24651704](https://stackoverflow.com/a/24651704)のFRAMEWORK_SEARCH_PATHSに$(PLATFORM_DIR)/Developer/Library/Framaworeworksを追加する必要があります。

LivefyreからLFSTestConfig.plistファイルが必要です。これはLivefyreがリクエストに応じて提供します。

## Xcodeドキュメント{#section_arl_b3v_zz}

[ドキュメント](https://livefyre.github.com/StreamHub-iOS-SDK/)を参照するか、Xcodeで「Documentation」ターゲットを構築できます（appledocをインストールする必要があります）。

## 要件 {#section_m5l_13v_zz}

v0.2.0以降のStreamHub iOS SDKバージョンでは、iOS 6.0以降が必要です。

## 付録（JSONのサポート） {#section_pcd_5hv_zz}

StreamHub-iOS SDKの内部をご覧の場合は、[JSONKit](https://github.com/escherba/JSONKit)の修正版をデフォルトのJSONパーサーとして使用します（Appleが提供するNSJSONSerializationの代わりに）。 これを行う必要があったのは、Appleのパーサーは、システムで表される値より大きい整数や浮動小数点数を含むJSONファイルのデコードをサポートしていないからです。 JSONKitの修正版では、非常に大きな数字が、例外をスローする代わりに、対応するシステムの最大数に切り捨てられます。
