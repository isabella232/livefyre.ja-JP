---
description: 利用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。
seo-description: 利用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。
seo-title: CSSクラス
solution: Experience Manager
title: CSSクラス
uuid: 8714e7e5-3858-458f-a464-de87fd2f0ff0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# CSSクラス{#css-classes}

利用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。

チャット、コメント、ライブブログ、レビュー、およびサイドに使用できます。

CSSを使用してLivefyreアプリをカスタマイズし、ページとの統合をより完了します。初期設定のアプリCSSを独自のスタイルシートで上書きするだけです。 この節では、使用可能なCSSのカスタマイズについて説明します。

* [エディターCSS](#c_css_classes/section_edx_prh_xz)
* [並べ替えオプションCSS](#c_css_classes/section_btq_4rh_xz)
* [コメントCSS](#c_css_classes/section_mlv_nrh_xz)
* [重点コメントCSS](#c_css_classes/section_m2v_mrh_xz)
* [アーカイブ済みコメントCSS](#c_css_classes/section_bs5_lrh_xz)
* [コメント通知CSS](#c_css_classes/section_dy4_krh_xz)
* [CSSクラスの保存](../c-app-customizations/c-storify-css-classes.md#c_storify_css_classes)

## エディターCSS {#section_edx_prh_xz}

ポストエディターのインターフェイスを変更するには、これらのクラスを使用します。

| クラス | 説明 |
|---|---|
| .fyre-comment-count | コメント数を表示するテキスト。 |
| .fyre-login-bar | ログインバーとオプションが含まれるバウンディングボックス。 |
| .fyre-live-container | リスニングする人とアバターの数を囲むバウンディングボックス。 |
| .fyreエディター | .fyre-login-bar、.fyre-live-containerおよびユーザーがコメントを記述するテキスト領域の周囲のバウンディングボックス。 |
| .fyre-stream-sort | 並べ替えオプションを囲むバウンディングボックス。 |

エディターフィールドの背景色、エディター内に表示されるテキストのフォントの色、サイズ、ファミリーなど、アプリ設定自体でスタイルを編集することもできます。

コメントエディターをカスタマイズするには、editorCss:{}オブジェクトをfyre.conv.load()に追加し、目的のスタイル設定を含めます。 例えば、カスタムCSSでエディターを更新するには：

```
fyre.conv.load(networkConfig, [{ 
   siteId: LF_siteId, 
   el: 'livefyre', 
   articleId: LF_articleId, 
   collectionMeta: #CollectionMeta 
   editorCss: { 
      background: '#ccc', 
      color: 'red', 
      font: '30px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif' 
   } 
}]);
```

## 並べ替えオプションCSS {#section_btq_4rh_xz}

| クラス | 説明 |
|---|---|
| .fyre-stream-sort | 並べ替えオプションdiv全体。 |
| .fyre-stream-sort-newest | 「新しい」オプション。 |
| .fyre-stream-sort-oldest | 「古い」オプション。 |
| .fyre-stream-sort-bar | オプション間の区切りバー。 |
| .fyre-stream-sort-selected | 現在選択されている並べ替えオプションです。 |

HTML構造：

```
<div class="fyre-stream-sort"> 
   <a href="#" class="fyre-stream-sort-newest fyre-stream-sort-selected">Newest</a>  
   <span class="fyre-stream-sort-bar"> | </span> 
   <a href="#" class="fyre-stream-sort-oldest">Oldest</a> 
</div>
```

並べ替えオプションを区切る「|」を非表示にします。

```
.fyre-stream-sort .fyre-stream-sort-bar { 
    display: none !important; 
}
```

## コメントCSS {#section_mlv_nrh_xz}

| クラス | 説明 |
|---|---|
| .fyre-comment-author-tag- *`custom tag name`* | Livefyreは、LivefyreのStudioのプロファイル同期を通じて追加された各ユーザータグに対して、この形式のCSSクラスを [作成します](/help/implementation/t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-sync-with-livefyre-using-ping-for-pull.md)。 このクラスは、そのタグを含むユーザーアカウントによって投稿されたコンテンツの背景のスタイル設定に使用できます。 |
| .fyre-tag-content-icon- *`tag name`* | Livefyre [Studioで追加された各コンテンツタグに対して、この形式のCSSクラスが作成されます](/help/implementation/c-app-customizations/c-adding-users-to-groups.md)。 このクラスは、タグを追加したコンテンツのスタイル設定に使用できます。 |
| .fyre-comment-user | ユーザープロファイルの画像を含むバウンディングボックスです。 |
| .fyre-comment-username | ユーザー名。 |
| .fyreモデレータ | モデレーターのバウンディングボックスです。 |
| .fyre-comment | コメントのテキスト/リンクの周囲のバウンディングボックス。 |
| .fyre-comment-article | コメントコンテンツ全体のバウンディングボックス。 |
| .fyre-comment-date | 「投稿からの時間」要素に添付されたタグ。 |
| .fyre-comment-media | メディアコンテンツの周囲のバウンディングボックス。 |
| .fyre-comment-actions | コメントに対して実行できるアクションの周囲のバウンディングボックス。 |
| .fyre-comment-like | 「いいね！」リンクの周囲のバウンディングボックス。 |
| .fyre-comment-reply | 「返信」リンクの周囲のバウンディングボックス。 |

## 重点コメントCSS {#section_m2v_mrh_xz}

>[!NOTE]
>
>すべてのコメントCSSクラスは、重点コンテンツにも適用できます。

| クラス | 説明 |
|---|---|
| .fyre-featured-content-wrapper | リーダーのコンテナdiv。 |
| .fyre-featured-header | 先頭のタイトルバー。 |
| .fyre-featured-header-icon | ヘッダーのクイルアイコン。 |
| .fyre-featured-title | ヘッダーのテキストです。 |
| .fyre-featured-body | 読者の特集コンテンツのコンテナdiv。 |
| .fyre-featured-quote | 各コンテンツアイテムを開始する引用符アイコン。 |

## アーカイブ済みコメントCSS {#section_bs5_lrh_xz}

>[!NOTE]
>
>すべてのコンテンツCSSクラスは、アーカイブ済みコンテンツにも適用できます。

| クラス | 説明 |
|---|---|
| .fyre-archive-stream-title | 「アーカイブから」のテキスト。 |
| .fyre-archive-stream-title-icon | 「アーカイブから」ヘッダーのロゴ。 |

## コメント通知CSS {#section_dy4_krh_xz}

Livefyreコメント通知機能をカスタマイズするためのクラスです。

| クラス | 説明 |
|---|---|
| .fyre-notification | リスト項目のdiv（新しいコンテンツとアーカイブコンテンツの両方）。 |
| .fyre通知子 | Notifierのコンテンツのラッパー。 |
| .fyre-notifier-archive | 最新の投稿以外のすべての新しいコンテンツのラッパー。 |
| .fyre-notifier-avatar | アバターの画像。 |
| .fyre-notifier-avatar-container | ユーザーアバターのコンテナdiv。 位置決めを定義できます。 |
| .fyre-notifier-avatar-shading | アバターdivのシェーディング。 |
| .fyre-notifier-banner | Notifierのプレビューコンテンツ用のコンテナです。このコンテナには、最近投稿されたアイテムに関するユーザーアバターとコンテンツスニペットが表示されます。 |
| .fyre-notifier-base | Notifierの情報部分のコンテナ。新しいコメント数、Notifierのキャプション、閉じるボタンをリストします。 |
| .fyre-notifier-base-close | Notifierの閉じるボタン(x)のコンテナdiv。 |
| .fyre-notifier-base-shadow | Notifierベースのシェーディング。 |
| .fyre-notifier-caption | 通知者に対して表示されるテキスト。 デフォルトでは「新しいコメント」です。 |
| .fyre-notifier-close | 通知を閉じるボタン。 |
| .fyre-notifier-container | Notifierのコンテナには、バナーとベースの両方が含まれます。 |
| .fyre-notifier-counter | Notifierにリストされている番号のコンテナです。 |
| .fyre-notifier-list | 最新のコンテンツのコンテナです。 |
| .fyre-notifier-message | 表示されるコンテンツの最初の30文字。 |
| .fyre-notifier-message-container | ヘッダーメッセージのコンテナdiv。 |
