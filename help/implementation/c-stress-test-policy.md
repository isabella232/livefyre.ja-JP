---
description: Livefyreプラットフォームに対してストレステストを実行します。
seo-description: Livefyreプラットフォームに対してストレステストを実行します。
seo-title: ストレステストポリシー
solution: Experience Manager
title: ストレステストポリシー
uuid: f2d49b55- f4fc-485f-9aea- a17ce64813ee
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# ストレステストポリシー{#stress-test-policy}

Livefyreプラットフォームに対してストレステストを実行します。

このドキュメントでは、Livefyreプラットフォームに対するストレステストの実行について説明します。通知のない顧客によるアドホックテストは、厳密に禁止されています。[禁止および許可され](#c_stress_test_policy/section_mhs_bfz_vdb)ているアクティビティについての詳細。

>[!NOTE]
>
>ストレステストはオプションです。ストレステストを実行する必要はありません。Adobe Livefyreは、リリースプロセスの一部として通常のストレステストおよび検証を実行します。テストを実行する場合は、このドキュメントに、ストレステストを実行するための要件と制約事項について説明します。

## 通知 {#section_ihs_bfz_vdb}

開始する予定のテストの3週間前に、Livefyreカスカスサクセススペシャリストおよびアドビテクニカルコンサルタントにお知らせください。

Livefyreに通知するには、Livefyreカスタマーサクセススペシャリストおよびアドビテクニカルコンサルタントに以下の情報を送信します。

* テストの目的と説明
* テストしている使用例
* テストで使用するLivefyre APIのリスト
* テストの日付、時間、期間
* テストを開始するIPアドレス

## 要件 {#section_khs_bfz_vdb}

テストは、以下の要件を満たしている場合にのみ実行できます。

* テストを開始する前に、アドビのテクニカルコンサルタントから書面による明示的な承認を受け取る必要があります。
* **テストを実行できるのはUAT Networkのみです。**
* 現実的なシナリオに対してテストする必要があります。例えば、これが現実的なシナリオではないので、プロパティが毎日 *何百万* もの投稿リクエストをサービスするとしないとします。お客様のシナリオが現実的かどうか判断する必要がある場合は、Livefyreカスタマーサクセススペシャリストまたはアドビテクニカルコンサルタントにお問い合わせください。
* テストは、太平洋標準タイムゾーン\（UTC-7\）の業務時間中に実施します。
* データとテストのロジックが必要な場合があります。

## ガバナンス {#section_mhs_bfz_vdb}

テストを実行するときにいつでもテストを終了する権限をLivefyreに付与します。

* 実稼動ネットワーク上。
* アドビテクニカルコンサルタントの書面による明示的な承認がない場合は、3週間以上前に承認してください。
* 実際のシナリオに反しています。

APIへのアクセスをブロックし、Livefyreネットワークを無効にし、要件を満たさない場合はロードテストリクエストを再試行することで、Livefyreのテストを終了します。