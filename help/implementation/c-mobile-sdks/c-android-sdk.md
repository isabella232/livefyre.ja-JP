---
description: Livefyreを利用したAndroidアプリを作成します。
title: Android SDK
exl-id: 54ea6537-5f27-4174-af25-d17257f23e48
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 1%

---

# Android SDK{#android-sdk}

Livefyreを利用したAndroidアプリを作成します。

このライブラリを使用して、LivefyreサービスをネイティブAndroidアプリに統合します。 [Livefyre StreamHub Android SDK](https://github.com/Livefyre/StreamHub-Android-SDK)は、Gradle/Android Studio開発環境に基づき、アドビの一般的なAPIメカニズムを中心にシンレイヤーを提供します。

また、このSDKに基づく[レビュー](https://github.com/Livefyre/StreamHub-iOS-Reviews-App)サンプルアプリも提供しています。

このLivefyre Android SDKは、EclipseとAndroid Studioの両方で使用できます。

>[!NOTE]
>
>Livefyre Android SDKをインストールする前に、環境に[Android SDK](https://developer.android.com/sdk/index.html)がインストールされている必要があります。 また、Android開発者ドキュメント/で説明されているように、追加のAndroid SDKパッケージを含める必要もあります。
>[SDKパッケージの追加](https://developer.android.com/sdk/installing/adding-packages.html)

Android SDK Manager（Android StudioまたはEclipseツールバーから利用可能）を使用して、すべての推奨パッケージをインストールします。 必ずAndroidサポートリポジトリも含めてください。

## Eclipse {#section_dtm_slv_zz}

EclipseでプロジェクトにLivefyre Android SDKを追加するには：

1. GitHubから最新の[StreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK)を取得します。
1. 既存のプロジェクトとの開始、または新しいプロジェクトの作成
1. StreamHub-Android-SDKをワークスペースに読み込むには、**[!UICONTROL File > Import > General > Existing Project into Workspace]**&#x200B;に移動します。
1. StreamHub-Android-SDK；を参照して選択します。これで、パッケージエクスプローラーに表示されます。
1. プロジェクトを右クリックし、「**[!UICONTROL Properties,]**」を選択してから、「Android」タブを選択します。
1. 「ライブラリ」セクションで、**[!UICONTROL Add button,]**&#x200B;を選択し、ライブラリのリストからStreamHub-Android-SDKを選択します。
1. **[!UICONTROL Apply]**&#x200B;と&#x200B;**[!UICONTROL OK]**&#x200B;をクリックします。

## Android Studio {#section_vpw_klv_zz}

Android StudioでプロジェクトにLivefyre Android SDKを追加するには：

1. GitHubから最新の[StreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK)を取得します。
1. 既存のプロジェクトとの開始、または新しいプロジェクトの作成
1. プロジェクトを右クリックし、**[!UICONTROL Open Module Settings]**&#x200B;を選択します。
1. ウィンドウの左上隅にある&#x200B;**[!UICONTROL +]**&#x200B;ボタンを選択します。
1. **[!UICONTROL Import Existing Project.]**&#x200B;を選択します（新しいバージョンのAndroid Studioでは、**[!UICONTROL More Modules]**&#x200B;の下に&#x200B;**[!UICONTROL Import Existing Project]**&#x200B;があります）。

1. StreamHub-Android-SDKを参照して選択します。

Android Studioは、SDKをグレード版に変換するように要求する場合があります。この場合は、「**[!UICONTROL next]**」、「**[!UICONTROL finish]**」の順に選択します。

依存関係の下の&#x200B;**プロジェクトフォルダー/appフォルダー/build.gradle**&#x200B;ファイルに移動し、次の依存関係を追加します。

```
dependencies {   compile project(':streamHubAndroidSDK') } 
```

次の行が&#x200B;**プロジェクトフォルダー> settings.gradle**&#x200B;ファイル内にあることを確認します。

```
include ':streamHubAndroidSDK' 
```

>[!NOTE]
>
>設定は、Config.java内でカスタマイズできます。

## クライアント {#section_yfq_blv_zz}

StreamHub Android SDKは、Livefyre APIエンドポイントをリクエストするのに使用できる複数のクライアントクラスを公開します。

* **AdminClientExchangeユーザー情報、** キー、その他のメタデータ用のユーザー認証トークンを交換します。

* **BootstrapClientGet特定のコレクションに関する最新のコンテンツとメタデータを取得し** ます。

* **StreamClientPollコレクションのストリームをポーリングし、新しい、更新された、および削除されたコンテンツを取得します。** 

* **コレクション内の** WriteClientPost、フラグ、「いいね！」コンテンツ。
