---
description: リリースノート（2018年11月16日リリース）。
title: リリースノート
exl-id: 3f904022-b770-4f35-a3b0-790e15748763
source-git-commit: beb224fdccf68c98fc3eff62b0867f22fa52902b
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 6%

---

# リリースノート{#release-notes}

リリースノート（2018年11月16日リリース）。

## 新機能 {#section_syx_mdt_wcb}

本番版のこのリリースでは、次の新機能がリリースされました。

* **instagramの検索とストリームの更新。**  *Instagramビジネスアカウントは次の目的で使用* できます。

   * ユーザーによるInstagramソーシャル検索を実行します(ユーザーはInstagramビジネスアカウントである必要もあります)。

   * 独自のInstagramを含む、特定のInstagramユーザーアカウント（アカウントもビジネスアカウントである必要があります）から、ストリームを作成します。

   * 部分的に自動化されたワークフローを使用して、Instagramからアセットに対する権限をリクエストします。

   * instagramの権限を設定してリクエストする必要があるInstagramアカウントの種類について詳しくは、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。

* **使用権限リクエストの応答をビジネスアカウントベースの検索で自動監視する。** ビジネスアカウントベースの検索のみ — Livefyreで、権限リクエストに対する応答を自動的に監視し、アクティビティ履歴を更新する機能を使用できます。

instagramアカウントの権限をリクエストする方法について詳しくは、[Instagram権限リクエストの手動での送信](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md)および[部分的に自動化されたInstagram権限リクエストの送信](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)を参照してください。

* **Adobe Target の統合.** Adobe Targetとの統合が追加され、Livefyre AppsをAdobe Targetオファーライブラリと直接共有できるようになりました。LivefyreとAdobe Targetの使用について詳しくは、[Targetのドキュメント](https://experienceleague.adobe.com/docs/livefyre/using/library/livefyre-target.html)を参照してください。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

### 実稼動版リリース

| 問題のタイプ | コンポーネント | リリースノート |
|--- |--- |--- |
| 問題 | AppService:Livefyre ID | [!UICONTROL Reset to Default]をクリックしても、Studio/統合設定/ Livefyre IDのログインモーダルのロゴがデフォルトの画像にリセットされない問題を修正しました。 |
| 問題 | ライブラリ | ライブラリにアップロードされ、アセットの詳細で表示されたビデオが正しく表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールに商品が表示されない問題を修正しました。 |
| 問題 | ストリーム | ストリームルールで製品タグを使用できない問題を修正しました。 |
| 機能強化 | Studio | Livefyre Studioで製品IDが表示されない問題を修正しました。 |
| 問題 | スタジオ：ModQ | 削除したコンテンツが削除後もModQに表示される問題を修正しました。 |

### UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 問題 | ソーシャルコンポーネント：カルーセル | IE11およびMozilla Firefoxで、共有リンクが期待どおりに応答せず、URLをコピーしなかった問題を修正しました。 |
