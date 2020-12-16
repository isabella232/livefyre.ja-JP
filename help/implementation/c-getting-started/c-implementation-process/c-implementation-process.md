---
description: Livefyre Studioの実装時の期待値
seo-description: Livefyre Studioの実装時の期待値
seo-title: 実装プロセス
solution: Experience Manager
title: 実装プロセス
uuid: 9a0f394e-3467-47d1-9816-45e2130db440
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 3%

---


# 実装プロセス{#implementation-process}

Livefyreの実装に要する時間は、実装と作業範囲によって異なります。

## Livefyreネットワークアーキテクチャの概要{#section_dgj_l32_rbb}

Livefyreでは、ネットワークアーキテクチャについて説明する際に次の用語を使用します。

* ネットワーク. Livefyreの使用を予定している最上位レベルのドメイン。
* Sites. ネットワークの一部であるサブドメインまたはサイトセクション。
* アプリ. サイト上でのコンテンツのレンダリング。 ビジュアライゼーションアプリ（Mosaic、Carousel、Feature Cardなど）を使用して、コンテンツがアプリに視覚的に表示されます。 またはテキスト形式で、会話アプリ（コメント、レビュー、チャットなど）を使用します。 1つ以上のアプリをサイトに配置できます。
* ストリーム。 ストリームとは、ソーシャルメディアや他のサイトを検索して、コンテンツを自動的に収集し、モデレート用またはアプリ内の直接投稿用にストリームを使用するフィルターです。
* コンテンツ（例えば、UGC、コメント）。 アプリに表示する内容。 コンテンツは、ビジュアル（写真やビデオなど）、オーディオのみ、テキストのいずれかです。

次の図に、ネットワーク、サイト、アプリ、コンテンツの関係を示します。

![](assets/network_site_architecture.png)

独自のLivefyreインスタンスがあり、これがコンテンツのモデレートやユーザーの管理などを中央ダッシュボードとして行う場合、 Livefyreインスタンスにアクセスするには、CSMにお問い合わせください。

## 統合手順 {#section_s2j_d2x_tz}

Livefyreの統合には、主に次の3つの手順があります。

* アプリの統合

   Livefyreを実装する場合、実装のスタイルは使用事例によって異なります。 各実装タイプ](/help/implementation/c-getting-started/c-implementation-process/c-app-integration-types.md#c_app_integration_types)の[を増やします。

* 認証の統合

   会話用アプリ(App)や、サイトでエンドユーザーの認証を必要とするその他のアプリケーションを使用するには、既存のユーザー管理システムをLivefyreと統合する必要があります。 現在、ユーザー管理ツールを使用していない場合は、Livefyre IDを使用できます。 [Livefyre IDの詳細、概要、設定方法](/help/implementation/c-livefyre-identity-comp/c-livefyre-identity-comp.md#c_livefyre_identity)

* カスタマイズ

   カスタマイズはオプションですが、ほとんどのお客様はブランドに合わせてアプリをカスタマイズできます。

