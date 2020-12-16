---
description: 2018年11月16日リリースのリリースノートです。
seo-description: 2018年11月16日リリースのリリースノートです。
seo-title: リリースノート
solution: Experience Manager
title: リリースノート
uuid: 34e64943-dea6-46ac-9fcc-8febeab6aa42
translation-type: tm+mt
source-git-commit: efb031b58f01ec69c8297a808998d25a0015f102
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 7%

---


# リリースノート{#release-notes}

2018年11月16日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版でリリースされた新機能：

* **Instagramの検索とストリームに対する更新。** Instagramのビジネス *アカウン* トは次のように使用できます。

   * ユーザーによるInstagramのソーシャル検索を実行します（ユーザーはInstagramのビジネスアカウントである必要もあります）。

   * 特定のInstagramユーザーアカウント（アカウントは、会社のアカウントも含む）からInstagramストリームを作成します。

   * 部分的に自動化されたワークフローを使用して、Instagramにアセットの権限を要求します。

   * Instagramアカウントの設定と要求に必要な種類について詳しくは、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。

* **ビジネスアカウントベースの検索に対する使用権限リクエストの応答を自動で監視する。** ビジネスアカウントベースの検索のみ — 権限要求への応答を自動的に監視し、Livefyreのアクティビティ履歴を更新する機能を使用できます。

Instagramアカウントの権限を要求する方法について詳しくは、[Instagram権限要求を手動で送信](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md)および[部分的に自動化されたInstagram権限要求の送信](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)を参照してください。

* **Adobe Target の統合.** Adobe Targetとの統合が追加され、Livefyre Appsを直接Adobe Targetオファーライブラリで共有できるようになりました。LivefyreをAdobe Targetと併用する方法について詳しくは、[ターゲットドキュメント](hhttps://docs.adobe.com/content/help/en/livefyre/using/library/livefyre-target.html)を参照してください。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

### 実稼働版リリース

| 問題のタイプ | コンポーネント | リリースノート |
|--- |--- |--- |
| 問題 | AppService:Livefyre ID | Studio/統合設定/Livefyre IDの「ログインモーダル」で[!UICONTROL Reset to Default]をクリックしても、ロゴがデフォルトの画像にリセットされない問題を修正しました。 |
| 問題 | ライブラリ | ビデオがライブラリにアップロードされ、アセットの詳細で表示されると正しく表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品が表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品タグが使用できない問題を修正しました。 |
| 機能強化 | スタジオ | 製品IDがLivefyre Studioに表示されない問題を修正しました。 |
| 問題 | スタジオ：ModQ | 削除したコンテンツが削除後もModQに表示され続ける問題を修正しました。 |

### UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 問題 | Socialコンポーネント：カルーセル | IE11およびMozilla Firefoxで、共有リンクが期待どおりに応答してURLをコピーしない問題を修正しました。 |