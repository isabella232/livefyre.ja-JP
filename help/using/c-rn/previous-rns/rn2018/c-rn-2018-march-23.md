---
description: 2018年3月24日リリースのリリースノートです。
seo-description: 2018年3月24日リリースのリリースノートです。
seo-title: 2018 年 3 月 24 日
solution: Experience Manager
title: 2018 年 3 月 24 日
uuid: b69b8715- ace4-48e0-8f54- ce4e12170ef3
translation-type: tm+mt
source-git-commit: 35feb87bb82d1f298496717a65f1972cf4e71104

---


# 2018年3月24日{#march}

2018年3月24日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の機能が新機能です。

* **プロダクションの新機能:** FacebookでFacebookログインにセキュリティ更新が作成され、顧客のFacebookログインが正しく機能しなくなりました。この問題を修正するには、次の点に注意してください。

   1. クライアントOAuth設定の **[!UICONTROL Valid OAuth redirect URIs]** フィールドに次のURLを追加します。正しい `<networkname>` ネットワーク名に置き換えます。
      `https://identity.livefyre.com/<networkname>/api/v1.0/public/profile/social/complete/facebook_fyre`

   1. に切り替え **[!UICONTROL Use Strict Mode for Redirect URI]** **[!UICONTROL Yes]** ます。

* **UATの新機能:** ストリーム内のスマートタグの信頼性しきい値を選択できるようになりました。タグに精度スコア（0~100）を設定すると、取得するアセットの正確性を制御できます。

## 雑誌号 {#section_ehw_ndt_wcb}

このリリースでは、次の表の問題が解決しました。

## 実稼働リリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| バグ | メディアウォール | Instagram投稿がストリームルールから追加されたときにタグがクリックできないMediaウォールの問題を修正しました。 |
| バグ | Modq | Modqが正しく読み込まれない問題を修正しました。 |
| バグ | Modq | オーディオを埋め込むと、MOQが機能しなくなる問題を修正しました。 |

## UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 機能強化 | フィルムストリップ | フィルムストリップにアクセスできるようになる問題を修正しました。 |
| 機能強化 | Studio | IMSログインを使用してLivefyreにログインできるようになりました。 |

