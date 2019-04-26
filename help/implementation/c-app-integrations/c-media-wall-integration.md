---
description: コンテンツストリーミングを使用して、コンテンツのストリーミングをリアルタイムで作成します。
seo-description: コンテンツストリーミングを使用して、コンテンツのストリーミングをリアルタイムで作成します。
seo-title: メディアウォール
solution: Experience Manager
title: メディアウォール
uuid: c6087c80- a35b-44d2-9dd4- ba9cd471172d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# メディアウォール{#media-wall}

コンテンツストリーミングを使用して、コンテンツのストリーミングをリアルタイムで作成します。

Mediaウォールを使用すると、サイトのリアルタイムのソーシャルウォールを作成できます。Livefyre JavaScript SDKのStreamHub- warepackageを使用して、Livefyreのソーシャルフィードを視覚的に魅力的でフルスクリーンのコンテンツエクスペリエンスとして表示したり、ライブイベントをホスティングしたり、写真コンテストをホストしたり、Webサイトのソーシャルセクションを活用したりすることができます。

## 統合{#section_jfm_bwb_c1b}

メディアウォールを追加する最も迅速な方法は、LivefyreのCDNでホストされているビルドバージョンを使用することです。

まず、Livefyre. jsを [サイト](https://github.com/Livefyre/Livefyre.js) に追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

次に、メディアウォールが表示される要素を配置します。

```
<div id="wall"></div>
```

最後に、コンポーネントを構築 `Livefyre.require` します。

```
<script> 
Livefyre.require([ 
    'streamhub-wall#5' 
], function(MediaWall) {     
    var wall = window.wall = new MediaWall({ 
        el: document.getElementById("wall"), 
        collection: { 
            "network": "client-solutions.fyre.co", 
            "siteId": "364309", 
            "articleId": "answers-mediawall" 
        } 
    }); 
}); 
</script>
```

ウォールが表示されます。この例で [は、すべてを実行](https://codepen.io/gobengo/pen/dFwDL)中です。

**エラーをヒットしますか?** 正しい環境パラメーターを渡すことを確認してください。オプションには、 `livefyre.com` （実稼働）または `t402.livefyre.com` UATが含まれます。

>[!NOTE]
>
>Mediaウォールアプリでレンダリングされるツイートのスタイル設定のカスタマイズは、Twitter [の表示要件に従って行う必要](https://dev.twitter.com/terms/display-requirements)があります。

## Config Options {#section_ucv_qvb_c1b}

`columns`

ウォールの構築時に、Mediaウォールの列数を定義できます。このオプションを設定した場合、各列の幅は、指定した数の列を維持しながら、メディアウォールのコンテナサイズに合わせて自動的に調整されます。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5 
});
```

`initial`

ページ読み込み時にレンダリングするコンテンツアイテムの数。デフォルトは50です。

```
var wallView = new MediaWall({ 
   el: document.getElementById('wall'), 
   initial: 10 
});
```

`minContentWidth`

Mediaウォールのコンテナ要素内の各列の最小（ピクセル）幅を設定できます。（Mediaウォールでは、コンテナ要素の幅に応じて、適切な数の列が自動的に選択されます。デフォルトでは、Mediaウォールの幅が最小コンテンツの幅（300pxの場合）で割り、列数が決まります。

>[!NOTE]
>
>このオプションは、列オプションと組み合わせて使用しないでください。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    minContentWidth: 300 
});
```

`modal`

デフォルトでは、コンテンツの一部の添付ファイルがある場合、メディアウォールにクリック可能なサムネールが表示されます。「アプリ」をクリックすると、写真/ビデオの添付ファイル全体がモーダル表示されます。このオプションを無効にするには、モーダルをfalseに設定します。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5, 
    modal: false 
});
```

`postButton`

ウォールに表示する [!UICONTROL Post Content] ボタンを定義します。このオプションを使用するには、 `opts.collection`ページにLivefyre. js認証の統合を渡す必要があります。

`postButton` パラメーター:

* `false` （デフォルト）:「投稿コンテンツ」ボタンを表示しない。（読み取り専用のMediaウォールを作成します）。
* `true` （また `LiveMediaWall.postButtons.contentWithPhotos`は）:ユーザーがテキストコンテンツを追加できるボタンを追加します。

* `LiveMediaWall.postButtons.content`:ユーザーがテキストコンテンツを追加できるが、写真を添付できないボタンを含めます。
* `LiveMediaWall.postButtons.photo`:ユーザーが写真を追加できるがテキストは追加できないボタンを含めます。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    collection: collection, 
    postButton: true, 
    minContentWidth: 300 
});
```

`showMore`

[!UICONTROL Show More] ボタンをクリックしたときにウォールに追加するコンテンツ項目の数を定義します。

```
var wallView = new LiveMediaWall({ 
    el: document.getElementById('wall'), 
    showMore: 10 
});
```

## スタイル設定オプション {#section_ztv_dvb_c1b}

Media Wallには、テキストの色、スタイル、サイズをカスタマイズできるいくつかの設定オプションもあります。これらのオプションを実装するには、次の構文を使用します。

```
var wall2 = window.wall2 = new MediaWall({ 
   el: document.getElementById("listView1"), 
   collection: collection, 
   cardBackgroundColor: '#333', 
   textColor: 'magenta', 
   linkColor: 'orange', 
   footerTextColor: 'lime', 
   displayNameColor: 'cyan', 
   usernameColor: 'red', 
   fontFamily: 'Helvetica, Arial', 
   linkAttachmentBackgroundColor: '#555', 
   linkAttachmentBorderColor: '#888' 
}); 
```

有効な入力については、CSS [フォントファミリー](https://www.w3.org/TR/CSS2/fonts.html#propdef-font-family)、 [フォントサイズ](https://www.w3.org/TR/CSS2/fonts.html#font-size-props)、 [行の高さおよび](https://www.w3.org/TR/CSS2/visudet.html#propdef-line-height)[色](https://www.w3.org/TR/css3-color/#colorunits) のプロパティのW3C標準を参照してください。

* **bodyFontSize***（CSSフォントサイズ文字列）* コンテンツ本文テキストのフォントサイズ。

* **bodylineHeight***（CSS行の高さの文字列）* コンテンツ本文のテキストの高さの高さ。

* **buttonActiveBackgroundColor***（CSSカラー文字列）**ボタンの背景のカラー。

* **buttonBorderColor***（CSSカラー文字列）**ボタンの境界線のカラー。

* **buttonHoverBackgroundColor***（CSSカラー文字列）* カーソルを合わせたときのボタンの背景色。

* **buttonTextColor***（CSSカラー文字列）* ボタンのラベルのカラー。

* **cardBackgroundColor***（CSSカラー文字列）* メディアウォール内のコンテンツカードの背景色。

* **displayNameColor***（CSSカラー文字列）* Byline内の表示名のカラー。

* **fontFamily***（CSS Font Family String）* 本文テキストのフォントファミリー。

* **FooterTextColor***（CSSカラー文字列）* セカンダリテキストのカラー（フッターテキスト、およびその後のユーザー名など）。

* **linkAttachmentBackgroundColor***（CSSカラー文字列）* リンク添付ファイル（スタック添付ファイル）の背景色。

* **linkAttachmentBorderColor***（CSSカラー文字列）* リンク添付ファイル（スタック添付ファイル）の境界線のカラー。

* **linkAttachmentTextColor***（CSS Color String）* リンクの添付テキストのカラー。

* **linkColor***（CSSカラー文字列）* ハイパーリンクの色（本文テキスト内のリンク、および表示名リンクなど）。

* **TextColor***（CSSカラー文字列）* 本文テキストのカラー。

* **TitleFontSize***（CSSフォントサイズ文字列）* コンテンツタイトルのフォントサイズ。

* **titleLineHeight***（CSS行の高さの文字列）* コンテンツタイトルの行の高さ。

* **sourceToGColor***（CSSカラー文字列）* ソースロゴのカラー。

* **userNameColor***（CSS Color String）* Byline内のusernameのカラー。
