---
description: 2018年3月24日リリースのリリースノートです。
seo-description: 2018年3月24日リリースのリリースノートです。
seo-title: 2018 年 3 月 24 日
solution: Experience Manager
title: 2018 年 3 月 24 日
uuid: b69b8715-ace4-48e0-8f54-ce4e12170ef3
translation-type: tm+mt
source-git-commit: 35feb87bb82d1f298496717a65f1972cf4e71104

---


# March 23, 2018{#march}

2018年3月24日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の機能が新たに追加されました。

* **** 実稼働環境の新機能：Facebookは、顧客のFacebookログインが正しく機能しない原因となるFacebookログインのセキュリティ更新を作成しました。 この問題を修正するには、次の操作を行う必要があります。

   1. クライアントOAuth設定のフィールド **[!UICONTROL Valid OAuth redirect URIs]** に次のURLを追加します。 正しいネ `<networkname>` ットワーク名に置き換えます。
      `https://identity.livefyre.com/<networkname>/api/v1.0/public/profile/social/complete/facebook_fyre`

   1. に切り **[!UICONTROL Use Strict Mode for Redirect URI]** 替えま **[!UICONTROL Yes]**&#x200B;す。

* **** UATの新機能：ストリーム内のスマートタグの信頼性のしきい値を選択できるようになりました。 タグの精度スコア(0 ～ 100)を設定すると、取得するアセットの精度を制御できます。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

## 実稼働版リリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| バグ | メディアウォール | Media wallで、Instagramの投稿がストリームルールから追加された場合にタグがクリックできない問題を修正しました。 |
| バグ | ModQ | ModQが正しく読み込まれない問題を修正しました。 |
| バグ | ModQ | オーディオを埋め込むとModQが機能しなくなる問題を修正しました。 |

## UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 機能強化 | Filmstrip | フィルムストリップのアクセシビリティを向上させるためのいくつかの問題を修正しました。 |
| 機能強化 | スタジオ | IMSログインを使用してLivefyreにログインできるようになりました。 |

