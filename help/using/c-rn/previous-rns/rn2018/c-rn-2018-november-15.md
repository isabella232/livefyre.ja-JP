---
description: 2018年11月16日リリースのリリースノートです。
seo-description: 2018年11月16日リリースのリリースノートです。
seo-title: リリースノート
solution: Experience Manager
title: リリースノート
uuid: 34e64943-dea6-46ac-9fcc-8febeab6aa42
translation-type: tm+mt
source-git-commit: 573e815799fbae2c2c4f1d98a01ea0ae04108a34

---


# リリースノート{#release-notes}

2018年11月16日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版でリリースされた新機能：

* **Instagramの検索とストリームに対する更新。** Instagramのビジネスアカウントを使用して、次のこ *とを行うことができます* 。

   * ユーザーによるInstagramのソーシャル検索を実行します（ユーザーはInstagramのビジネスアカウントである必要もあります）。

   * 特定のInstagramユーザーアカウント（アカウントは、会社のアカウントも含む）からInstagramストリームを作成します。

   * 部分的に自動化されたワークフローを使用して、Instagramにアセットの権限を要求します。

   * Instagramアカウントの設定および権限の要求に必要な種類について詳しくは、Instagramアカウントに [ついてを参照してください](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)。

* **ビジネスアカウントベースの検索に対する使用権限リクエストの応答を自動で監視する。** ビジネスアカウントベースの検索のみ — 権限要求への応答を自動的に監視し、Livefyreのアクティビティ履歴を更新する機能を使用できます。

Instagramアカウントの権限を要求する方法について詳しくは、Instagram権限リクエストの手動 [送信](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md) および部分的に自動化されたInstagram権限リクエストの [送信を参照してください](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)。

* **Adobe Target の統合.** Adobeターゲットとの統合が追加され、Livefyre Appsを直接Adobeターゲットオファーライブラリと共有できるようになりました。 LivefyreをAdobeターゲットと併用する方法について詳しくは、 [ターゲットドキュメントを参照してください](hhttps://docs.adobe.com/content/help/en/livefyre/using/library/livefyre-target.html)。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

### 実稼働版リリース

| 問題のタイプ | コンポーネント | リリースノート |
|--- |--- |--- |
| 問題 | AppService: Livefyre ID | クリックしても [! UICONTROL Reset to Default] （デフォルトにリセット）を選択しても、Studio/統合設定/Livefyre IDの「ログインモーダル」の下のロゴがデフォルトの画像にリセットされませんでした。 |
| 問題 | ライブラリ | ビデオがライブラリにアップロードされ、アセットの詳細で表示されると正しく表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品が表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品タグが使用できない問題を修正しました。 |
| 機能強化 | スタジオ | 製品IDがLivefyre Studioに表示されない問題を修正しました。 |
| 問題 | スタジオ： ModQ | 削除したコンテンツが削除後もModQに表示され続ける問題を修正しました。 |

### UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 問題 | Socialコンポーネント： カルーセル | IE11およびMozilla Firefoxで、共有リンクが期待どおりに応答してURLをコピーしない問題を修正しました。 |