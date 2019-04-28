---
description: LivefyreによるAndroidアプリの作成
seo-description: LivefyreによるAndroidアプリの作成
seo-title: Android SDK
solution: Experience Manager
title: Android SDK
uuid: 68793fa9-3ea1-4890- b36d- b631f1c6f7de
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Android SDK{#android-sdk}

LivefyreによるAndroidアプリの作成

このライブラリを使用して、LivefyreサービスをネイティブAndroidアプリケーションに統合します。[Livefyre StreamHub SDKは、Gradle/Android](https://github.com/Livefyre/StreamHub-Android-SDK) Studio開発環境に基づいて、共通のAPIメカニズムの周囲に細いレイヤーを提供します。

Livefyreも、このSDKに基づいた [アプリケーション](https://github.com/Livefyre/StreamHub-iOS-Reviews-App) のサンプルを紹介しています。

このLivefyre Android SDKは、EclipseとAndroid Studioの両方で使用できます。

>[!NOTE]
>
>Livefyre Android SDKをインストールする前に、Android SDKを [環境に](https://developer.android.com/sdk/index.html) インストールしておく必要があります。Android Developer docs&gt;の説明に従って、Android SDKパッケージを追加する必要もあります。
>[SDKパッケージの追加](https://developer.android.com/sdk/installing/adding-packages.html)

すべての推奨パッケージをインストールするには、Android SDK Manager（Android StudioまたはEclipseツールバーから利用可能）を使用します。Android Support Repositoryも含めます。

## Eclipse {#section_dtm_slv_zz}

EclipseでLivefyre Android SDKをプロジェクトに追加するには:

1. GitHubから最新 [のStreamHub- Android- SDK](https://github.com/Livefyre/StreamHub-Android-SDK) を入手してください。
1. 既存のプロジェクトから開始するか、新しいプロジェクトを作成します。
1. StreamHub- Android- SDKをワークスペースに読み込むには、に移動 **[!UICONTROL File > Import > General > Existing Project into Workspace]** します。
1. StreamHub- Android- SDKを参照して選択します。これで、パッケージエクスプローラーに表示されます。
1. プロジェクトを右クリックし、&quot;Android&quot;タブを選択 **[!UICONTROL Properties,]** します。
1. 「ライブラリ」セクションで、 **[!UICONTROL Add button,]** ライブラリのリストから&quot;StreamHub- Android- SDK&quot;を選択します。
1. **[!UICONTROL Apply]** 「および **[!UICONTROL OK]** 」をクリックします。

## Android Studio {#section_vpw_klv_zz}

Android StudioでLivefyre Android SDKをプロジェクトに追加するには:

1. GitHubから最新 [のStreamHub- Android- SDK](https://github.com/Livefyre/StreamHub-Android-SDK) を入手してください。
1. 既存のプロジェクトから開始するか、新しいプロジェクトを作成します。
1. プロジェクトを右クリックして、を選択 **[!UICONTROL Open Module Settings]** します。
1. ウィンドウの左上隅にある **[!UICONTROL +]** ボタンを選択します。
1. 選択（ **[!UICONTROL Import Existing Project.]** 新しいバージョンのAndroid Studioでは、以下を検索 **[!UICONTROL Import Existing Project]** できます） **[!UICONTROL More Modules]** 。

1. StreamHub- Android- SDKを参照して選択します。

Android Studioでは、SDKをバージョンのgradleに変換することが要求される場合があります。その場合は、を選択 **[!UICONTROL next]** **[!UICONTROL finish]** します。

依存関係下の **プロジェクトフォルダー/app folder/build. gradle** ファイルに移動して、次の依存関係を追加します。

```
dependencies {   compile project(':streamHubAndroidSDK') } 
```

**プロジェクトフォルダ/settings. gradle** ファイルに次の行があることを確認してください。

```
include ':streamHubAndroidSDK' 
```

>[!NOTE]
>
>設定は、Config. java内からカスタマイズできます。

## クライアント {#section_yfq_blv_zz}

StreamHub Android SDKは、Livefyre APIエンドポイントのリクエストに使用できるクライアントクラスをいくつか公開します。

* **ユーザー情報、キー、その他のメタデータに対してユーザー認証トークンを** 交換します。

* **BootstrapClient** 特定のコレクションに関する最新のコンテンツとメタデータを取得します。

* **StreamClient** コレクションのストリームをポーリングして、新規、更新、削除されたコンテンツを取得します。

* **writeClient** コレクション内の投稿、フラグ、および同様のコンテンツ。

