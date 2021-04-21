---
description: 2018年3月24日リリースのリリースノートです。
title: 2018 年 3 月 24 日
exl-id: 85fd6f79-7fa8-425e-b4c7-2e1635d6ef17
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 7%

---

# 2018 年 3 月 23 日{#march}

2018年3月24日リリースのリリースノートです。

## 新機能 {#section_syx_mdt_wcb}

このリリースの実稼働版では、次の機能が新しく追加されました。

* **本番環境の新機能：** Facebookは、お客様のFacebookログインが正しく動作しない原因となる、Facebookログインのセキュリティ更新を作成しました。この問題を修正するには、次の操作を行う必要があります。

   1. 追加クライアントOAuth設定の&#x200B;**[!UICONTROL Valid OAuth redirect URIs]**&#x200B;フィールドへの次のURL。 `<networkname>`を正しいネットワーク名に置き換えます。
      `https://identity.livefyre.com/<networkname>/api/v1.0/public/profile/social/complete/facebook_fyre`

   1. **[!UICONTROL Use Strict Mode for Redirect URI]**&#x200B;を&#x200B;**[!UICONTROL Yes]**&#x200B;に切り替えます。

* **UATの新機能：ストリ** ーム内のスマートタグの信頼性のしきい値を選択できるようになりました。タグの精度スコア(0 ～ 100)を設定すると、取得するアセットの精度を制御できます。

## タスク {#section_ehw_ndt_wcb}

次の表に示す問題は、このリリースで解決されました。

## 実稼働版リリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| バグ | メディアウォール | instagramの投稿がストリームルールから追加された場合に、メディアウォールでタグがクリックできない問題を修正しました。 |
| バグ | ModQ | ModQが正しく読み込まれない問題を修正しました。 |
| バグ | ModQ | オーディオを埋め込むとModQの機能が停止する問題を修正しました。 |

## UATリリース

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 機能強化 | Filmstrip | フィルムストリップのアクセシビリティを高めるためのいくつかの問題を修正しました。 |
| 機能強化 | スタジオ | IMSログインを使用してLivefyreにログインできるようになりました。 |
