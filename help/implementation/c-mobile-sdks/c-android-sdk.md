---
description: LivefyreでAndroidアプリを作成します。
seo-description: LivefyreでAndroidアプリを作成します。
seo-title: Android SDK
solution: Experience Manager
title: Android SDK
uuid: 68793fa9-3ea1-4890-b36d-b631f1c6f7de
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Android SDK{#android-sdk}

LivefyreでAndroidアプリを作成します。

このライブラリを使用して、LivefyreサービスをネイティブAndroidアプリに統合します。 Livefyre streamHub Android SDK [](https://github.com/Livefyre/StreamHub-Android-SDK) (Android SDK)は、Gradle/Android studio開発環境に基づく、一般的なAPIメカニズムを中心にシンレイヤーを提供します。

また、このSDKに基づく [Reviews](https://github.com/Livefyre/StreamHub-iOS-Reviews-App) サンプルアプリも提供されています。

このLivefyre Android SDKは、EclipseとAndroid studioの両方で使用できます。

>[!NOTE]
>
>Livefyre Android SDKをインストールする前に、 [Android SDKを環境にインスト](https://developer.android.com/sdk/index.html) ールする必要があります。 また、Android開発者向けドキュメント/で説明されているように、追加のAndroid SDKパッケージを含める必要もあります。
>[SDKパッケージの追加](https://developer.android.com/sdk/installing/adding-packages.html)

Android SDK Manager（Android studioまたはEclipseツールバーから利用可能）を使用して、すべての推奨パッケージをインストールします。 必ずAndroidサポートリポジトリも含めてください。

## Eclipse {#section_dtm_slv_zz}

EclipseでプロジェクトにLivefyre Android SDKを追加するには：

1. GitHubから最新 [のStreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK) を入手します。
1. 既存のプロジェクトを使用するか、新しいプロジェクトを作成します。
1. StreamHub-Android-SDKをワークスペースに読み込むには、に進みます **[!UICONTROL File > Import > General > Existing Project into Workspace]**。
1. StreamHub-Android-SDK；を参照して選択します。パッケージエクスプローラーに表示されます。
1. プロジェクトを右クリックし、「Android」 **[!UICONTROL Properties,]** タブを選択します。
1. 「ライブラリ」セクションで、 **[!UICONTROL Add button,]** を選択し、ライブラリのリストから「StreamHub-Android-SDK」を選択します。
1. とをクリッ **[!UICONTROL Apply]** クしま **[!UICONTROL OK]**&#x200B;す。

## Android Studio {#section_vpw_klv_zz}

Android studioでプロジェクトにLivefyre Android SDKを追加するには：

1. GitHubから最新 [のStreamHub-Android-SDK](https://github.com/Livefyre/StreamHub-Android-SDK) を入手します。
1. 既存のプロジェクトを使用するか、新しいプロジェクトを作成します。
1. プロジェクトを右クリックし、を選択しま **[!UICONTROL Open Module Settings]**&#x200B;す。
1. ウィンドウ **[!UICONTROL +]** の左上隅にあるボタンを選択します。
1. 「 **[!UICONTROL Import Existing Project.]** (新しいバージョンのAndroid studioでは、を参照してく **[!UICONTROL Import Existing Project]** ださ **[!UICONTROL More Modules]**&#x200B;い。)

1. StreamHub-Android-SDKを参照して選択します。

Android studioは、SDKをグレード版に変換するように要求する場合があります。この場合は、「&gt;」を選 **[!UICONTROL next]** 択しま **[!UICONTROL finish]**&#x200B;す。

次の依存 **関係を追加するには、プロジェクトフォルダー/appフォルダー/build.gradle** fileに移動します。

```
dependencies {   compile project(':streamHubAndroidSDK') } 
```

次の行がプロジェクトフォルダー&gt; settings.gradleフ **ァイル内にあることを確認し** ます。

```
include ':streamHubAndroidSDK' 
```

>[!NOTE]
>
>設定は、Config.java内でカスタマイズできます。

## クライアント {#section_yfq_blv_zz}

StreamHub Android SDKは、Livefyre APIエンドポイントのリクエストに使用できる複数のクライアントクラスを公開します。

* **AdminClient** Exchangeユーザー情報、キー、その他のメタデータ用のユーザー認証トークンを取得します。

* **BootstrapClient** 特定のコレクションに関する最近のコンテンツとメタデータを取得します。

* **StreamClientは** 、コレクションのストリームをポーリングして、新しい、更新された、削除されたコンテンツを取得します。

* **WriteClient** Post、フラグ、コレクション内の「いいね！」コンテンツ。

