---
description: Release Notes for the November 1, 2018 release.
seo-description: Release Notes for the November 1, 2018 release.
seo-title: 2018 年 11 月 2 日
solution: Experience Manager
title: 2018 年 11 月 2 日
uuid: ed1a3bf1-b3f1-4746-8462-07283723ba62
translation-type: tm+mt
source-git-commit: 09011bac06f4a1c39836455f9d16654952184962

---


# 2018 年 11 月 2 日{#november}

Release Notes for the November 1, 2018 release.

## 新機能 {#section_syx_mdt_wcb}

The following new features were released in the production version of this release:

* ビデオスマートタグ

   Leverage state of the art computer vision technology, powered by Adobe Sensei, to automatically tag video content when you save it to the Library. Smart Tags help you manage UGC more effectively but also create super precise curation rules (streams) that collect content based on what's in the video, not just the text, saving you significant effort moderating unwanted content.

   機能の詳細：

   * スマートタグは、ソーシャル検索、ストリームおよびライブラリ内のアップロードされたビデオファイルから取得したビデオに自動的に追加されます。 個々のビデオのアセットの詳細のタグの表示
   * ビデオに.MP4、.MOVおよびAVI形式のタグを付けます。
   * 最大60秒または50 MBのビデオへのタグ付け
   * ビデオには、次の2つのカテゴリのスマートタグが適用されます。特徴（動物、物、場所など）と行動（走る、歩く、歌うなど）
   For more information see [Smart Tags](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md#c_smart_tags)

* Instagramのレート制限

   Instagramは、Livefyreを含むInstagram APIを使用する会社が1時間あたり5,000件のリクエストを行えるリクエスト数を、トークンあたり1時間あたり200件のリクエストに変更しました。 これは、レート制限と呼 *ばれます*。 詳しくは、Instagramのレート制限 [を参照してください](/help/using/c-streams/c-instagram-rate-limiting.md)。

* ライブラリ内のオーディオファイル

   ライブラリパネルからオーディオファイルに対して次の機能を実行できるようになりました。

   * 検索
   * プレビュー
   * インポート
   * オーディオファイルでのフィルター
   * ファイルをデザイナーにドラッグ&amp;ドロップします

## タスク {#section_ehw_ndt_wcb}

本番バージョンのこのリリースでは、新しい問題は解決されませんでした。 上記の [節を参照](#c_rn/section_syx_mdt_wcb)。

## UATリリース {#section_EE91B0C9313E45C5B4CBD59CFBCCFCFE}

次の表に示す問題は、このリリースのUATバージョンで解決されました。

| **問題のタイプ** | **コンポーネント** | **リリースノート** |
|---|---|---|
| 機能強化 | GDPR | Analytics内の以前のお客様に関連付けられたデータはすべて削除されます。 |
| バグ | ライブラリ | ビデオがライブラリにアップロードされ、アセットの詳細で表示されると、正しく表示されない問題を修正しました。 |
| バグ | Mosaic | Instagramのカルーセルのコンテンツの最後の部分を、カードではなくサムネールとしてMosaicが表示する問題を修正しました。 |
| バグ | ソーシャル検索 | Instagramのソーシャル検索が期待どおりに動作しない問題を修正しました。 |

