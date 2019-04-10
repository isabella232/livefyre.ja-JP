---
description: Livefyre Studioの実装について考えてみましょう。
seo-description: Livefyre Studioの実装について考えてみましょう。
seo-title: 実装プロセス
solution: Experience Manager
title: 実装プロセス
uuid: 9a0f394e-3467-47d1-9816-45e2130db440
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 実装プロセス{#implementation-process}

Livefyre実装の所要時間は、実装および作業範囲によって異なります。

## Livefyreネットワークアーキテクチャの概要 {#section_dgj_l32_rbb}

Livefyreではネットワークアーキテクチャについて以下の用語を使用しています。

* ネットワーク。Livefyreを使用する予定の最上位ドメインです。
* サイトを参照してください。ネットワークの一部であるサブドメインまたはサイトセクション。
* アプリを参照してください。サイト上のコンテンツのレンダリング。コンテンツは、視覚化アプリ（Mosaic、Carousel、Feature Cardなど）を使用して、視覚的にアプリに表示されます。またはテキスト形式で、会話アプリ（コメント、レビュー、チャットなど）を使用します。1つまたは複数のアプリをサイトに配置できます。
* ストリームを参照してください。ストリームは、ソーシャルメディアや他のサイトを検索して、アプリでモデレートまたは直接公開するためにコンテンツを自動的に収集するフィルターです。
* コンテンツ（UGC、コメントなど）アプリに表示される内容コンテンツには、ビジュアル（写真やビデオなど）、オーディオ専用、またはテキストを使用できます。

次の図に、ネットワーク、サイト、アプリおよびコンテンツの関係を示します。

![](assets/network_site_architecture.png)

独自のLivefyreインスタンスがあり、コンテンツのモデレート、ユーザー管理などのための中央ダッシュボードがあります。Livefyreインスタンスにアクセスするには、CSMにお問い合わせください。

## 統合手順 {#section_s2j_d2x_tz}

Livefyre統合の主な手順は次の3つです。

* アプリの統合

   Livefyreを実装する場合、実装のスタイルは使用例によって異なります。実装 [タイプ](/help/implementation/c-getting-started/c-implementation-process/c-app-integration-types.md#c_app_integration_types)について詳しくは、を参照してください。

* 認証の統合

   サイトでのエンドユーザー認証を必要とする、会話アプリおよびその他のアプリ用に、既存のユーザー管理システムをLivefyreと統合する必要があります。ユーザー管理ツールを現在使用していない場合は、Livefyre IDを使用できます。Livefyre [Identityについて、およびその設定方法と設定方法について](/help/implementation/c-livefyre-identity-comp/c-livefyre-identity-comp.md#c_livefyre_identity)詳しくは、を参照してください。

* カスタマイズ

   カスタマイズはオプションですが、ほとんどの顧客はブランドに合うようにアプリをカスタマイズします。

