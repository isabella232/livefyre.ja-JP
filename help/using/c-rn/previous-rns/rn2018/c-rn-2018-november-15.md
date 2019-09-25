---
description: 2018年11月16日リリースのリリースノートです。
seo-description: 2018年11月16日リリースのリリースノートです。
seo-title: リリースノート
solution: Experience Manager
title: リリースノート
uuid: 34e64943-dea6-46ac-9fc-8febeab6aa42
translation-type: tm+mt
source-git-commit: 35feb87bb82d1f298496717a65f1972cf4e71104

---


# リリースノート{#release-notes}

2018年11月16日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の新機能がリリースされました。

* **Instagramの検索とストリームに対する更新です。** Instagramのビジネスアカウントを使 *用して、次の操作を行うことができ* ます。

   * ユーザーによるInstagramソーシャル検索を実行します（ユーザーはInstagramのビジネスアカウントである必要もあります）。

   * 特定のInstagramユーザーアカウントからInstagramストリームを作成します（アカウントは、自分のアカウントもビジネスアカウントにする必要があります）。

   * 部分的に自動化されたワークフローを使用して、Instagramにアセットの権限を要求します。

   * Instagramに対して設定および要求権限を行う必要があるInstagramアカウントの種類について詳しくは、Instagramアカウントにつ [いてを参照してくださ](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)い。

* **ビジネスアカウントベースの検索に対する使用権限リクエスト応答の自動監視。** For business accounts-based searches only--the ability to automatically monitor responses to rights requests and update the activity history in Livefyre is available.

Instagramアカウントの権限を要求する方法について詳しくは、Instagram権限要求を手動で送信 [する](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md) 、および部 [分的に自動化されたInstagram権限要求の送信を参照してください](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)。

* **Adobe Target の統合.** Adobe targetとの統合が追加され、LivefyreアプリをAdobe targetオファーライブラリと直接共有できるようになりました。 Adobe targetでのLivefyreの使用について詳しくは、 [Targetのドキュメントを参照してください](https://marketing.adobe.com/resources/help/en_US/livefyre/livefyre-target.html)。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

### 実稼働版リリース

| 問題のタイプ | コンポーネント | リリースノート |
|--- |--- |--- |
| 問題 | AppService:Livefyre ID | クリックすると [UICONTROL Reset to Default] （デフォルトにリセット）が、Studio/統合設定/Livefyre IDの「ログインモーダル」の下のロゴをデフォルトの画像にリセットしなかった問題を修正しました。 |
| 問題 | ライブラリ | ビデオがライブラリにアップロードされ、アセットの詳細で表示されると、正しく表示されない問題を修正しました。 |
| 問題 | ストリーム | 製品がストリームルールに表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品タグが使用できない問題を修正しました。 |
| 機能強化 | スタジオ | 製品IDがLivefyre studioに表示されない問題を修正しました。 |
| 問題 | スタジオ：ModQ | 削除されたコンテンツが削除後もModQに表示され続ける問題を修正しました。 |

### UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 問題 | Socialコンポーネント：カルーセル | IE11およびMozilla Firefoxで、共有リンクが期待どおりに応答し、URLをコピーしない問題を修正しました。 |