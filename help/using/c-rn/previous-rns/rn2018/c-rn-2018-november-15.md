---
description: 2018年11月16日リリースのリリースノートです。
title: リリースノート
exl-id: 3f904022-b770-4f35-a3b0-790e15748763
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 6%

---

# リリースノート{#release-notes}

2018年11月16日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版でリリースされた新機能：

* **instagram検索とストリームの更新。** 次の目的で、 *Instagramビジネス* アカウントを使用できます。

   * ユーザーによるInstagramのソーシャル検索を実行します(ユーザーは、Instagramのビジネスアカウントである必要もあります)。

   * 特定のInstagramユーザーアカウント（自分のアカウントを含む、ビジネスアカウントのアカウント）からInstagramストリームを作成します。

   * 部分的に自動化されたワークフローを使用して、Instagramにアセットの権限を要求します。

   * 設定してInstagramから権限を要求する必要があるInstagramアカウントの種類については、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。

* **ビジネスアカウントベースの検索に対する使用権限リクエストの応答を自動で監視する。** ビジネスアカウントベースの検索のみ — 権限要求への応答を自動的に監視し、Livefyreのアクティビティ履歴を更新する機能を使用できます。

instagramアカウントの権限を要求する方法の詳細については、[「Instagram権限要求を手動で送信](/help/using/c-how-requesting-rights-works/c-send-instagram-manual-rights-request.md)」および「[部分的に自動化されたInstagram権限要求の送信](/help/using/c-how-requesting-rights-works/c-send-an-instagram-rights-request-from-the-library.md)」を参照してください。

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
