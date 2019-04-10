---
description: 使用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。
seo-description: 使用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。
seo-title: CSSクラス
solution: Experience Manager
title: CSSクラス
uuid: 8714e7e5-3858-458f- a464- de87fd2f0ff0
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# CSSクラス{#css-classes}

使用可能なCSSクラスを使用して、アプリの表示をカスタマイズします。

チャット、コメント、ライブブログ、レビュー、およびSsiicingで利用できます。

CSSを使用して、デフォルトのApp CSSを自分のスタイルシートで上書きするだけで、Livefyreアプリをカスタマイズしてページとの統合をより完全に実行できます。ここでは、使用可能なCSSのカスタマイズについて説明します。

* [エディターCSS](#c_css_classes/section_edx_prh_xz)
* [並べ替えオプションCSS](#c_css_classes/section_btq_4rh_xz)
* [コメントCSS](#c_css_classes/section_mlv_nrh_xz)
* [重点コメントCSS](#c_css_classes/section_m2v_mrh_xz)
* [Archived Comments CSS](#c_css_classes/section_bs5_lrh_xz)
* [コメント通知CSS](#c_css_classes/section_dy4_krh_xz)
* [Storify CSSクラス](../c-app-customizations/c-storify-css-classes.md#c_storify_css_classes)

## エディターCSS {#section_edx_prh_xz}

ポストエディターインターフェイスを変更するには、これらのクラスを使用します。

| クラス | 説明 |
|---|---|
| . fyre- comment- count | コメント数を表示するテキスト。 |
| . fyre- login- bar | ログインバーとオプションを含むバウンディングボックスです。 |
| . fyre- live- container | リスニングしている人とそのアバターの周囲のバウンディングボックス。 |
| . fyre- editor | . fyre- login- bar、. fyre- live- container、およびユーザーがコメントを書き込むテキスト領域の周囲のバウンディングボックス。 |
| . fyre- stream- sort | 並べ替えオプションの周囲のバウンディングボックス。 |

エディターフィールドの背景色や、エディター内に表示されるフォントの色、サイズ、テキストファミリーなど、アプリ設定自体でスタイルを編集することもできます。

コメントエディターをカスタマイズするには、editorCSSを追加します。{}オブジェクトをfyre. conv. load（）に、目的のスタイルを設定します。例えば、カスタムCSSを使用してエディターを更新するには:

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
| . fyre- stream- sort | 並べ替えオプションdiv全体。 |
| . fyre- stream- sort- fatest | 「新機能」オプション。 |
| . fyre- stream- sort- latest | 「古い」オプション。 |
| . fyre- stream- sort- bar | オプション間の区切りバー。 |
| . fyre- stream- sort- selected | 現在選択されている並べ替えオプションです。 |

HTML構造:

```
<div class="fyre-stream-sort"> 
   <a href="#" class="fyre-stream-sort-newest fyre-stream-sort-selected">Newest</a>  
   <span class="fyre-stream-sort-bar"> | </span> 
   <a href="#" class="fyre-stream-sort-oldest">Oldest</a> 
</div>
```

"|「並べ替え」オプションを区切ります。

```
.fyre-stream-sort .fyre-stream-sort-bar { 
    display: none !important; 
}
```

## コメントCSS {#section_mlv_nrh_xz}

| クラス | 説明 |
|---|---|
| . fyre- comment- author- tag- *`custom tag name`* | Livefyreでは、LivefyreのStudioで [追加された各ユーザータグに対して、CSSクラスが作成](/help/implementation/t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-sync-with-livefyre-using-ping-for-pull.md)されます。このクラスを使用して、そのタグを含むユーザーアカウントによって投稿されたコンテンツの背景のスタイルを設定できます。 |
| . fyre- tag- content- icon- *`tag name`* | Livefyreは、Livefyre [Studio経由で追加されたコンテンツタグごとにCSSクラスを作成](/help/implementation/c-app-customizations/c-adding-users-to-groups.md)します。このクラスは、タグを追加したコンテンツのスタイル設定に使用できます。 |
| . fyre- comment- user | ユーザープロファイルの画像を含むバウンディングボックスです。 |
| . fyre- comment- username | ユーザー名。 |
| . fyre-モデレーター | モデレーターのバウンディングボックス。 |
| . fyre- comment | コメントテキスト/リンクの周囲のバウンディングボックス。 |
| . fyre- comment- article | コメントコンテンツ全体のバウンディングボックスです。 |
| . fyre- comment- date | 「投稿後の時間」エレメントに付加されるタグ。 |
| . fyre- comment- media | メディアコンテンツの周囲のバウンディングボックス。 |
| . fyre- comment- actions | コメントに対して実行するアクションの周囲のバウンディングボックス。 |
| . fyre- comment- like | 「いいね!"リンクの周囲のバウンディングボックス。 |
| . fyre- comment- reply | 「返信」リンクの周囲のバウンディングボックス。 |

## 重点コメントCSS {#section_m2v_mrh_xz}

>[!NOTE]
>
>すべてのコメントCSSクラスを特集コンテンツに適用することもできます。

| クラス | 説明 |
|---|---|
| . fyre- social- content- wrapper | 読者のコンテナdivです。 |
| . fyre- features- header | 先頭のタイトルバー。 |
| . fyre- features- header- icon | ヘッダーの四重アイコン。 |
| . fyre- features- title | ヘッダーテキスト。 |
| . fyre- feasures- body | 読者の特集コンテンツのコンテナdiv。 |
| . fyre- feasures- quotes | 各コンテンツアイテムを開始する引用符。 |

## Archived Comments CSS {#section_bs5_lrh_xz}

>[!NOTE]
>
>コンテンツのCSSクラスは、アーカイブされたコンテンツにも適用できます。

| クラス | 説明 |
|---|---|
| . fyre- archive- stream- title | 「アーカイブから」テキスト。 |
| . fyre- archive- stream- title- icon | 「アーカイブ」ヘッダーのロゴ。 |

## コメント通知CSS {#section_dy4_krh_xz}

Livefyreコメント通知をカスタマイズするクラスです。

| クラス | 説明 |
|---|---|
| . fyre- notification | リスト項目のdiv（新しいコンテンツとアーカイブコンテンツの両方）。 |
| . fyre- notifier | Notifierのコンテンツのラッパーです。 |
| . fyre- notifier- archive | 最新の投稿以外のすべての新しいコンテンツのラッパー。 |
| . fyre- notifier- avatar | アバターの画像。 |
| . fyre- notifier- avatar- container | ユーザーアバターのコンテナdivです。位置を定義できます。 |
| . fyre- notifier- avatar- laying | アバターdivの網掛け。 |
| . fyre- notifier- banner | 通知者のプレビューコンテンツのコンテナ。これにより、最近投稿された品目のユーザーアバターおよびコンテンツスニペットが表示されます。 |
| . fyre- notifier- base | 新しいコメントの数、通知子のキャプションおよび閉じるボタンの数を表示する、Notifierの情報部分のコンテナです。 |
| . fyre- notifier- base- close | 通知子の閉じるボタン（x）のコンテナdiv。 |
| . fyre- notifier- base- shadow | Notifierのベースのシェーディング。 |
| . fyre- notifier- caption | 通知者に表示されるテキスト。デフォルトでは「新しいコメント」です。 |
| . fyre- notifier- close | 通知者を閉じるボタン。 |
| . fyre- notifier- container | Notifierのコンテナには、バナーとベースの両方が含まれます。 |
| . fyre- notifier- counter | Notifierに一覧表示されている番号のコンテナです。 |
| . fyre- notifier- list | 最新のコンテンツのコンテナです。 |
| . fyre- notifier- message | 表示されるコンテンツの最初の~30文字。 |
| . fyre- notifier- message- container | ヘッダーメッセージのコンテナdivです。 |
