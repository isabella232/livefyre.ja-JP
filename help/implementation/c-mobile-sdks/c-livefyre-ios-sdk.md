---
description: ネイティブiOSアプリにLivefyreを追加します。
seo-description: ネイティブiOSアプリにLivefyreを追加します。
seo-title: Livefyre iOS SDK
solution: Experience Manager
title: Livefyre iOS SDK
uuid: bfdef31a-49fc-4b25-b0c5-300f27067302
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre iOS SDK{#livefyre-ios-sdk}

ネイティブiOSアプリにLivefyreを追加します。

このオープンソースライブラリを使用して、LivefyreサービスをネイティブiOSアプリに統合します。 Livefyre streamHub iOS SDKは、優れたAFNetworkingライブラリに基づいて、共通のAPIメカニズムの周りにシンレイヤーを提供します。

また、このSDKに基づくiOSサンプルアプリケーションが2つ用意されています。コメントストリームとレビューサンプルアプリ

## CocoaポッドとしてのSDKのプロジェクトへの統合（推奨） {#section_qc5_h3v_zz}

StreamHub-iOS SDKをプロジェクトに追加する最も便利な方法は、CocoaPodを使用することです。 CocoaPodを持っていない場合は、gemのインストール用Cocoapodとポッドの設定を実行します。 ポッドファイルの例を次に示します。

```
source 'https://github.com/Livefyre/cocoapods.git' 
source 'https://github.com/CocoaPods/Specs.git' 
  
platform :ios, :deployment_target => '6.0' 
  
pod 'StreamHub-iOS-SDK', '~> 0.3.0'
```

また、CocoaPodのインストールにSpecsリポジトリを追加する必要があります(これによりディレクトリにコピー `~/.cocoapods/repos` されます)。

```
pod repo add livefyre https://github.com/Livefyre/cocoapods.git
```

アプリプロジェクトのルートにポッドファイルを作成し、上記のリポジトリを追加したら、次を実行します。

```
pod install
```

これにより、すべての依存関係がダウンロードされ、MyApp.xcworkspaceファイルが作成されます。これ以降は、Xcodeでアプリプロジェクトを開く際に使用する必要があります。

## Xcodeサブプロジェクトとして {#section_jcm_g3v_zz}

または、リポジトリをコピーします。

```
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
```

次に、Xcodeプロジェクト(LFSClient.xcodeproj)をサブプロジェクトとしてアプリに追加します（XcodeのプロジェクトナビゲーターペインにLFSClient.xcodeprojファイルをドラッグするだけで簡単に実行できます）。

また、任意の依存関係([AFNetworking](https://github.com/AFNetworking/AFNetworking)、 [JSONKit](https://github.com/escherba/JSONKit))でも同じ処理を行う必要があります。

## すべてを一度にダウンロードする（非推奨） {#section_rpb_f3v_zz}

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
>Xcode 6でテストを実行するには、Pods-test-XCTest+OHTTPStubSuiteCleanUp podhttps://stackoverflow.com/a/24651704内のFRAMEWORK_SEARCH_PATHSに$(PLATFORM_DIR)/Developer/Library/Frameworksを追加する必要があり[ます](https://stackoverflow.com/a/24651704)。

LivefyreからLFSTestConfig.plistファイルが必要です。これはLivefyreが要求に応じて提供します。

## Xcodeドキュメント {#section_arl_b3v_zz}

ドキュメントを参照す [るか](https://livefyre.github.com/StreamHub-iOS-SDK/) 、Xcodeで「Documentation」ターゲットを構築できます（appledocをインストールする必要があります）。

## 要件 {#section_m5l_13v_zz}

v0.2.0以降のStreamHub iOS SDKバージョンでは、iOS 6.0以降が必要です。

## 付録（JSONのサポート） {#section_pcd_5hv_zz}

StreamHub-iOS SDKの内部を見る場合は、変更されたバージョンの [JSONKitを(Appleが提供するNSJSONSerializationの代わりに](https://github.com/escherba/JSONKit) )デフォルトのJSONパーサーとして使用します。 これを行う必要があったのは、Appleが提供するパーサーが、システムで表すことのできる整数や浮動小数点数より大きい整数を含むJSONファイルのデコードをサポートしていないからです。 JSONKitの修正バージョンでは、非常に大きな数値が、例外をスローする代わりに、対応するシステムの最大値に切り詰められます。
