---
description: 2018年9月6日リリースのリリースノートです。
seo-description: 2018年9月6日リリースのリリースノートです。
seo-title: 2018年9月6日
solution: Experience Manager
title: 2018年9月6日
uuid: 8dbe8be0- cc3c-4d96- af56-1808d8555af3
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 2018年9月6日{#september}

2018年9月6日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の新機能がリリースされました。

* [Experience Manager Livefyre](/help/using/c-features-livefyre/c-call-to-action-button.md#topic_EBE23A0F827645E0A0C619DCF3872EE5) のカスタム誘い文句（CTA:コールトゥアクション）ボタン

   Experience Manager Livefyreの新しいカスタムの誘い文句（CTA:コールトゥアクション）ボタンを使用すると、自社のWebサイト上でUGCを利用して、ビジネスを進めることができます。カスタムCTAボタンを使用して、販売の増加、リードのキャプチャ、より深く関与したり、オーディエンスにとる行動を促進したりします。カスタムCTAボタンを使用すると、次のことができます。

   * Livefyreメディアのウォール、モザイク、カルーセル、フィルムストリップ、個々の機能カードのUGCにカスタムボタンを追加します。
   * 各UGCのボタン、メッセージ、アイコン、色およびリンクの数を自由に制御できます。
   * 設定とライブラリ内からカスタムの誘い文句（CTA:コールトゥアクション）を作成、管理、再利用します。
   * Adobe Analyticsを使用してクリックスルー率を測定します。

* [スマートタグ](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md#c_smart_tags) の機能強化

   * アップロードされたファイル用のスマートタグ:Googleドライブ、ドロップボックス、Flickrなどのファイルなど、「すべてのアセット」のアップロード機能を使用してライブラリにアップロードされるスマートタグ画像を追加しました。
   * 作業に安全であり、作業（NSW）スマートタグには安全ではありません。Livefyreを介してキュレーションされた画像は、AI性能の微妙な検出システムによってタグ付けされるようになり、NSW画像を自動的にフィルターして、ストリームやUGCライブラリの安全性を向上させることができます。

      * ソーシャル検索またはストリームを介してキュレーションされた画像は、保存時にヌード検出システムによって分類されます。
      * UGC管理を迅速に実行するために、SFL/NSWタグによるライブラリのフィルタリング機能。
      * ストリームからNSFW UGCを自動的に削除する機能。

## 雑誌号 {#section_ehw_ndt_wcb}

このリリースの実稼働版では、次の表の問題が解決しました。

## 実稼働リリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| バグ | コメント | コメントアプリでオーディオファイルが正しく再生されなかった問題を修正しました。 |
| バグ | ライブラリ | ライブラリURL検索を使用してInstagramの検索で、カードにビデオではなく画像が表示された場合に、サムネール上に再生ボタンが表示される問題を修正しました。 |
| バグ | ライブラリ | Instagram URL検索の実行から取得されたアプリにコンテンツを公開するとサムネールが表示されなかった問題を修正しました。 |
| バグ | ライブラリ | アセットをアセットに追加し、そのアセットの詳細を開くと、そのアセットの詳細を開くと、そのアセットの製品が表示されなかった問題を修正しました。 |

## UATリリース {#section_EE91B0C9313E45C5B4CBD59CFBCCFCFE}

このリリースのUATバージョンでは、次の表の問題が解決しました。

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| バグ | Socialコンポーネント:メディアアップロード | ユーザーがフィルムストリップにメディアをアップロードできなかった問題を修正しました。 |
