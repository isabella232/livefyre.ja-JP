---
description: 統合アプリケーションで使用できるCSSクラス。
seo-description: 統合アプリケーションで使用できるCSSクラス。
seo-title: Storify CSSクラス
solution: Experience Manager
title: Storify CSSクラス
uuid: 168a0db0- a209-417a- ba91- a33b4d411c8d
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Storify CSSクラス{#storify-css-classes}

統合アプリケーションで使用できるCSSクラス。

CSSを使用して、単に初期設定のCSSを独自のスタイルシートで上書きするだけで、ページとの統合をより完全に行うために、Storifyアプリケーションをカスタマイズします。ここでは、使用可能なCSSのカスタマイズについて説明します。

## 作成者エレメント {#section_tdy_hsh_xz}

投稿の作成者アバター、発言者名およびタイムスタンプのスタイル設定をカスタマイズできます。

![](assets/StorifyAuthorCSS.png)

| クラス | 説明 |
|---|---|
| . s- author- name | 作成者 |
| . s- author- avatar | 発言者のアバター。 |
| . s- img | 発言者のアバター画像。 |
| . s- timestamp | 日付コンテンツのタイムスタンプが投稿されました。 |

## ヘッダー要素 {#section_nbv_gsh_xz}

ストーリーページのヘッダーセクションをカスタマイズできます。

![](assets/StorifyHeaderCSS-countdown-1.png)

| **クラス** | **説明** |
|---|---|
| . super- header | メインヘッダ |
| . outside- header | メインヘッダー行1 |
| . s-カウントダウン | メインヘッダー行1カウントダウンタイマー |
| . s- lity | メインヘッダー行1「ライブ」ステータス |
| . base- header | メインヘッダー行2 |
| . s- dropdown | メインヘッダー行2並べ替えドロップダウントリガー |
| . s- dropdown- menu | メインヘッダー行2の並べ替えドロップダウンメニュー。 |
| . s- dropdown- thirangle | メインヘッダー行2の並べ替えドロップダウンメニューのキャレット。 |
| . s- dropdown- option | メインヘッダー行2の並べ替えドロップダウンメニュー項目。 |
| . s- views | メインヘッダー行2のビュー数。 |
| . s- share- buttonボタン | メインヘッダー行2共有ボタン |
| . s- share- menu | メインヘッダー行2共有メニュー |

## 投稿要素 {#section_lrs_fsh_xz}

投稿のストーリー要素のスタイル設定をカスタマイズできます。

![](assets/StorifyPostCSS.png)

| **クラス** | **説明** |
|---|---|
| . s- livelog | ストーリー要素全体のコンテナ |
| . s- post | 投稿コンテナ |
| . s-モーダル- content | 投稿モーダルコンテナ |
| . s- element- content | 投稿内のすべてのコンテンツ要素 |
| . s- element- text ul | テキスト要素 |
| . s- element- text h2 | テキスト要素のヘッドライン |
| . s- element- text p | テキスト要素の段落 |
| . s- element- text ul | テキスト要素の番号付けされていないリスト |
| . s- element- text ol | テキスト要素番号付きリスト |
| . s- element- text li | テキスト要素のリスト項目 |
| . s- element- text blockquote | ブロック引用 |
| . s- element- text blockquote:before | ブロック引用の開始アイコン |
| . s- element- text blockquote:after | ブロック引用の終わりのアイコン |
| . s- element- image | インライン画像要素コンテナ |
| . s- img | `<img>` element |
| . s- image- caption | ソーシャルメディアに存在する画像およびビデオのキャプション（例:Instagram画像） |
| . s- upload- image- caption | ストーリーエディターを使用してアップロードされた画像およびビデオのキャプション |
| . s- element- video | ビデオ要素 |
| . s- element- quotes | 引用要素（例:ツイートのw/テキストのみ） |
| . s- element- quote- image | "w/image"要素の見積もりツイートのw/image |
| . s- element- quotes- video | w/video要素の見積もり:ツイートのw/ビデオ） |
| . s- link- body | 引用符内のリンクプレビュー（例:ツイートのW/リンクプレビュー |

## フッター要素 {#section_ozc_zrh_xz}

個々の投稿ごとにフッターセクションをカスタマイズできます。

![](assets/storify_CSS_footer.png)

| **クラス** | **説明** |
|---|---|
| . s- post- footer | 投稿のフッター。 |
| . s- sireize a | 投稿のフッターにあるSocatesボタン。 |
| . s- like | 投稿のフッターにある「いいね!"ボタン。 |
