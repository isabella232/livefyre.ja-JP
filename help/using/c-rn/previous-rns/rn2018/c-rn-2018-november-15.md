---
description: リリースノートを参照してください。
seo-description: リリースノートを参照してください。
seo-title: リリースノート
solution: Experience Manager
title: リリースノート
uuid: 34e64943- dea6-46ac-9fcc-8feepab6aa42
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# リリースノート{#release-notes}

リリースノートを参照してください。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の新機能がリリースされました。

* **Instagram検索とストリームの更新。***Instagramのビジネスアカウントは次の* 目的に使用できます。

   * ユーザーによってInstagramソーシャル検索を実行します（ユーザーはInstagramのビジネスアカウントである必要があります）。

   * 特定のInstagramユーザーアカウント（アカウントも含む）からInstagramストリームを作成し、独自のアカウントを作成する必要があります。

   * 部分的に自動化されたワークフローを使用して、Instagramからのアセットの権限を要求します。

   * Instagramからの設定や、Instagramからの権限の要求に必要なInstagramアカウントのタイプについて詳しくは、Instagramアカウント [について](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。

* **ビジネスアカウントベースの検索に対する使用権限リクエスト応答の自動監視。** ビジネスアカウントベースの検索のみ——Livefyreの応答リクエストを自動的に監視し、Livefyreのアクティビティ履歴を更新できます。

Instagramアカウントの権限をリクエストする方法について詳しくは、Instagram [Rights Requestの手動](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md) 送信および [部分的に自動化されたInstagram Rights Requestの送信を参照](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)してください。

* **Adobe Targetの統合。** Adobe Targetとの統合が追加され、LivefyreアプリケーションをAdobe Targetオファーライブラリに直接共有できるようになりました。LivefyreとAdobe Targetの併用について詳しくは [、Targetのドキュメント](https://marketing.adobe.com/resources/help/en_US/livefyre/livefyre-target.html)を参照してください。

## 雑誌号 {#section_ehw_ndt_wcb}

このリリースでは、次の表の問題が解決しました。

### 実稼働リリース

| 問題のタイプ | コンポーネント | リリースノート |
|--- |--- |--- |
| 雑誌号 | AppService:Livefyre ID | [クリックすると、Studio/統合設定/Livefyre] Identityの「ログインモーダル」のロゴがデフォルトの画像にリセットされませんでした。 |
| 雑誌号 | ライブラリ | ライブラリにアップロードされたビデオが、アセットの詳細で表示されなかった問題を修正しました。 |
| 雑誌号 | ストリーム | 製品がストリームルールに表示されない問題を修正しました。 |
| 雑誌号 | ストリーム | 製品タグがストリームルールで使用できない問題を修正しました。 |
| 機能強化 | Studio | Livefyre Studioに製品IDが表示されない問題を修正しました。 |
| 雑誌号 | Studio:Modq | 削除されたコンテンツが削除後もMOQに表示される問題を修正しました。 |

### UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 雑誌号 | Socialコンポーネント:カルーセル | IE11およびMozilla Firefoxで共有リンクが応答してURLを期待どおりにコピーしなかった問題を修正しました。 |