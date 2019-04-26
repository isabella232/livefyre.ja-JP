---
description: ネイティブiOSアプリケーションにLivefyreを追加します。
seo-description: ネイティブiOSアプリケーションにLivefyreを追加します。
seo-title: Livefyre iOS SDK
solution: Experience Manager
title: Livefyre iOS SDK
uuid: bfdef31a-49fc-4b25- b0c5-300f27067302
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre iOS SDK{#livefyre-ios-sdk}

ネイティブiOSアプリケーションにLivefyreを追加します。

このオープンソースライブラリを使用してLivefyreサービスをネイティブiOSアプリケーションに統合します。Livefyre StreamHub iOS SDKは、優れたAFNetworkingライブラリに基づいて、共通のAPIメカニズムの周囲に細いレイヤーを提供します。

Livefyreには、このSDKに基づくiOSサンプルアプリも2つ用意されています。コメントストリームと、アプリのサンプルを示します。

## プロジェクトへのSDKとプロジェクトの統合（推奨） {#section_qc5_h3v_zz}

プロジェクトにStreamHub- iOS SDKを追加する最も便利な方法は、CocoAPsを使用することです。codeAPsを持っていない場合は、gem installココスポッドとポッドの設定を実行します。以下に、ポッドファイルの例を示します。

```
source 'https://github.com/Livefyre/cocoapods.git' 
source 'https://github.com/CocoaPods/Specs.git' 
  
platform :ios, :deployment_target => '6.0' 
  
pod 'StreamHub-iOS-SDK', '~> 0.3.0'
```

また、CoposaODインストールにスペックリポジトリを追加する必要があります（これはディレクトリに `~/.cocoapods/repos` コピーされます）。

```
pod repo add livefyre https://github.com/Livefyre/cocoapods.git
```

アプリケーションプロジェクトのルートでポッドファイルを作成し、上記のリポジトリを追加したら、次のように実行します。

```
pod install
```

これにより、すべての依存関係がダウンロードされ、現在使用しているファイルMyApp. xcworkspaceがXcodeでアプリケーションプロジェクトを開くために作成されます。

## Xcodeサブプロジェクトとして {#section_jcm_g3v_zz}

または、リポジトリをコピーします。

```
git clone https://github.com/Livefyre/StreamHub-iOS-SDK.git 
```

次に、アプリケーションにXcodeプロジェクト（LFSCClient. xcodeproj）をサブプロジェクトとして追加します（LFSClient. xcodeprojファイルをXcodeのプロジェクトナビゲーターペインにドラッグして簡単に実行できます）。

また、どの依存関係（[afNetworking](https://github.com/AFNetworking/AFNetworking)、 [JSONKit](https://github.com/escherba/JSONKit)）も同様に行う必要があります。

## すべてを一度にダウンロード（お勧めしません） {#section_rpb_f3v_zz}

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
>Xcode6でテストを実行するには、Pod- test- XCTest+ OhHttpStoveriteCreateUppodhttps://stackoverflow.com/a/24651704のフレームワーク_ SEARCH_ PATHSに$（PLATFORM_ DIR）/Developer/Library/Frameworksを追加する必要[](https://stackoverflow.com/a/24651704)があります。

LivefyreからLfstTestConfig. plistファイルが必要です。Livefyreはリクエスト時に提供されます。

## Xcodeドキュメント {#section_arl_b3v_zz}

[ドキュメント](https://livefyre.github.com/StreamHub-iOS-SDK/) を参照することも、システムに「ドキュメント」のターゲットを作成することもできます（Appledocが必要な場合）。

## 要件 {#section_m5l_13v_zz}

StreamHub iOS SDKバージョンのバージョンは、iOS6.0以降が必要です。

## 付録（JSONサポート） {#section_pcd_5hv_zz}

StreamHub- iOS SDKの内部を参照しているユーザーの場合、修正版の [JSONKitを、デフォルトのJSONパーサー](https://github.com/escherba/JSONKit) （Appleが提供するNjsonSerializationではなく）として使用することに注意してください。これは、Appleが提供するパーサーは、システムで表現できる整数または浮動小数点数を含むJSONファイルのデコードをサポートしていないので、これを行う必要がありました。変更されたバージョンのJSONKitは、例外をスローするのではなく、対応するシステム最大値に対して非常に大きな番号を切り詰めます。
