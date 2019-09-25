---
description: コンテンツストリーミングをリアルタイムで使用するメディアウォールを作成します。
seo-description: コンテンツストリーミングをリアルタイムで使用するメディアウォールを作成します。
seo-title: メディアウォール
solution: Experience Manager
title: メディアウォール
uuid: c6087c80-a35b-44d2-9dd4-ba9cd471172d
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# メディアウォール{#media-wall}

コンテンツストリーミングをリアルタイムで使用するメディアウォールを作成します。

Media wallを使用すると、サイトのリアルタイムのソーシャルウォールを作成できます。 Livefyre javaScript SDKのstreamhub-wallパッケージを使用して、Livefyreのソーシャルフィードを、ライブイベントのカバー、写真コンテストのホスト、Webサイトのソーシャルセクションのパワー化に最適な、視覚的に魅力的なフルスクリーンのタイル形式のコンテンツエクスペリエンスで表示します。

## 統合 {#section_jfm_bwb_c1b}

Media wallを追加する最も簡単な方法は、LivefyreのCDN上でホストされているビルドバージョンを使用することです。

まず、 [Livefyre.jsをサイトに追加します](https://github.com/Livefyre/Livefyre.js) 。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

次に、メディアウォールが表示される要素を配置します。

```
<div id="wall"></div>
```

最後に、を使用し `Livefyre.require` てコンポーネントを作成します。

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

これで壁が出来た！ この例では、すべてを実際に使用し [ています](https://codepen.io/gobengo/pen/dFwDL)。

**エラーを発生させる？** 正しい環境パラメーターが渡されていることを確認します。 （実稼働）ま `livefyre.com` たは(UAT)のオ `t402.livefyre.com` プションがあります。

>[!NOTE]
>
>Media Wallアプリでレンダリングされるツイートのスタイル設定のカスタマイズは、Twitterの表示要件に従って行う必要 [があります](https://dev.twitter.com/terms/display-requirements)。

## 設定オプション {#section_ucv_qvb_c1b}

`columns`

壁を構築する際のメディアウォールの列数を定義できます。 このオプションを設定すると、各列の幅は、指定した数の列を維持しながら、メディアウォールのコンテナサイズに自動的に適合します。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5 
});
```

`initial`

ページの読み込み時にレンダリングされるコンテンツアイテムの数です。 初期設定は50です。

```
var wallView = new MediaWall({ 
   el: document.getElementById('wall'), 
   initial: 10 
});
```

`minContentWidth`

メディアウォールのコンテナ要素内の各列の最小（ピクセル）幅を設定できます。 (メディアウォールは、コンテナ要素の幅に応じて、適切な数の列を自動的に選択します。 デフォルトでは、メディアウォールの幅を最小コンテンツの幅で割って（未定義の場合は300px）、列数を決定します。

>[!NOTE]
>
>列オプションと組み合わせてこのオプションを使用しないでください。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    minContentWidth: 300 
});
```

`modal`

デフォルトでは、コンテンツに添付ファイルがある場合、メディアウォールにクリック可能なサムネールが表示されます。 クリックすると、アプリがモーダルを開き、写真/ビデオの添付ファイル全体が表示されます。 このオプションを無効にするには、modalをfalseに設定します。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5, 
    modal: false 
});
```

`postButton`

壁に表示す [!UICONTROL Post Content] るボタンを定義します。 このオプションを使用するには、Livefyre.js `opts.collection`認証統合をページに渡して追加する必要があります。

`postButton` パラメーター：

* `false` （デフォルト）:「投稿のコンテンツ」ボタンを表示しません。 （読み取り専用のMedia Wallを作成します）。
* `true` (または `LiveMediaWall.postButtons.contentWithPhotos`):ユーザーがテキストコンテンツを追加できるボタンと、写真が添付されているボタンを追加します。

* `LiveMediaWall.postButtons.content`:ユーザーがテキストコンテンツを追加できるが、写真は添付できないボタンを含めます。
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

ボタンをクリックしたときに壁に追加するコンテンツ項目の数 [!UICONTROL Show More] を定義します。

```
var wallView = new LiveMediaWall({ 
    el: document.getElementById('wall'), 
    showMore: 10 
});
```

## スタイル設定オプション {#section_ztv_dvb_c1b}

Media wallには、テキストの色、スタイル、サイズをカスタマイズできる設定オプションもいくつか用意されています。 これらのオプションを実装するには、次の構文を使用します。

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

有効な入力については、W3C for CSS [Font Family](https://www.w3.org/TR/CSS2/fonts.html#propdef-font-family)、Font Size [、](https://www.w3.org/TR/CSS2/fonts.html#font-size-props)Line Height [、](https://www.w3.org/TR/CSS2/visudet.html#propdef-line-height) ColorPropertiesの各プロパティを参照し [](https://www.w3.org/TR/css3-color/#colorunits) てください。

* **bodyFontSize** (CSS Font Size String) ** コンテンツの本文テキストのフォントサイズ。

* **bodyLineHeight** (CSSの行の高さ *文字列)* ：コンテンツの本文の行の高さです。

* **buttonActiveBackgroundColor** (CSS Color String) ***アクティブなボタンの背景のカラー。

* **buttonBorderColor** (CSS Color String) ***ボタンの境界線のカラー。

* **buttonHoverBackgroundColor** (CSSカラ *ー文字列)* ：カーソルを合わせたときのボタンの背景の色。

* **buttonTextColor** (CSS Color String) ** ボタンのラベルのカラー。

* **cardBackgroundColor** (CSS Color String) ** ：メディアウォール内のコンテンツカードの背景色。

* **displayNameColor** (CSS Color String) ** 署名内の表示名のカラー。

* **fontFamily** (CSS Font Family String) ** 本文テキストのフォントファミリー。

* **footerTextColor** (CSS Color String) ** ：セカンダリテキストのカラー（フッターテキスト、バイライン内のユーザー名など）。

* **linkAttachmentBackgroundColor** (CSS Color String) ** リンクの添付ファイル（スタックされた添付ファイル）の背景色。

* **linkAttachmentBorderColor** (CSS Color String) ** リンクの添付ファイル（スタックされた添付ファイル）の境界線のカラー。

* **linkAttachmentTextColor** (CSS Color String) ** リンクの添付テキストのカラー。

* **linkColor** (CSS Color String) ** ：ハイパーリンク（本文内のリンク、表示名リンクなど）のカラー。

* **textColor** (CSS Color String) ** 本文のテキストのカラー。

* **titleFontSize** (CSS Font Size String) ** コンテンツタイトルのフォントサイズ。

* **titleLineHeight** (CSSの *行の高さ文字列)* ：コンテンツタイトルの行の高さです。

* **sourceLogoColor** (CSS Color String) ** ソースロゴのカラー。

* **usernameColor** (CSS Color String) ** ：バイライン内のユーザー名の色。
