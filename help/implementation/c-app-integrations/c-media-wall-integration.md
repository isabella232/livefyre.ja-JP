---
description: コンテンツをリアルタイムでストリーミングするメディアウォールを作成します。
title: メディアウォール
exl-id: 597af7e1-9ada-4893-9071-e17c21ef0d04
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# メディアウォール{#media-wall}

コンテンツをリアルタイムでストリーミングするメディアウォールを作成します。

Media Wallを使用すると、サイトのリアルタイムのソーシャルウォールを作成できます。 Livefyre JavaScript SDKのstreamhub-wallパッケージを使用すると、Livefyreのソーシャルフィードを、ライブイベントのカバー、写真コンテストのホスト、Webサイトのソーシャルセクションのパワーを視覚的に魅力的なフルスクリーンのタイル形式で表示できます。

## 統合 {#section_jfm_bwb_c1b}

メディアウォールを追加する最も簡単な方法は、LivefyreのCDN上にホストされているビルトバージョンを使用することです。

まず、[Livefyre.js](https://github.com/Livefyre/Livefyre.js)をサイトに追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script> 
```

次に、メディアウォールが表示される要素を配置します。

```
<div id="wall"></div>
```

最後に、`Livefyre.require`を使用してコンポーネントを構築します。

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

壁がある！ [この例](https://codepen.io/gobengo/pen/dFwDL)で実際に起こっているものをすべて見て下さい。

**エラーを発生させる？** 正しい環境パラメーターが渡されていることを確認します。`livefyre.com` （実稼働環境）または`t402.livefyre.com` (UAT)を選択できます。

>[!NOTE]
>
>Media Wallアプリでレンダリングされるツイートのスタイルをカスタマイズするには、Twitterの[表示要件](https://dev.twitter.com/terms/display-requirements)に従って行う必要があります。

## 構成オプション{#section_ucv_qvb_c1b}

`columns`

壁を作成する際に、メディアウォールの列数を定義できます。 このオプションを設定すると、指定した数の列を維持しながら、各列の幅がメディアウォールのコンテナサイズに自動的に適合します。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    columns: 5 
});
```

`initial`

ページの読み込み時にレンダリングするコンテンツアイテムの数。 初期設定は50です。

```
var wallView = new MediaWall({ 
   el: document.getElementById('wall'), 
   initial: 10 
});
```

`minContentWidth`

メディアウォールのコンテナ要素内の各列の最小（ピクセル単位）の幅を設定できます。 (メディアウォールでは、コンテナ要素の幅に応じて、適切な数の列が自動的に選択されます。 デフォルトでは、メディアウォールの幅をコンテンツの幅の最小値（未定義の場合は300px）で割った値によって列数が決まります。

>[!NOTE]
>
>列オプションと組み合わせて使用しないでください。

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

壁に表示する[!UICONTROL Post Content]ボタンを定義します。 このオプションを使用するには、`opts.collection`を渡し、Livefyre.js Auth統合をページに追加する必要があります。

`postButton` パラメーター：

* `false` （デフォルト）:「投稿コンテンツ」ボタンを表示しません。（読み取り専用のMedia Wallを作成します）。
* `true` (または `LiveMediaWall.postButtons.contentWithPhotos`):テキストコンテンツを追加するボタンと、写真を添付します。

* `LiveMediaWall.postButtons.content`:ユーザーがテキストコンテンツを追加できるが、写真は添付できないボタンを含めます。
* `LiveMediaWall.postButtons.photo`:ユーザーが写真を追加できるが、テキストは追加できないボタンを含めます。

```
var wallView = new MediaWall({ 
    el: document.getElementById('wall'), 
    collection: collection, 
    postButton: true, 
    minContentWidth: 300 
});
```

`showMore`

[!UICONTROL Show More]ボタンをクリックしたときに壁に追加するコンテンツ項目の数を定義します。

```
var wallView = new LiveMediaWall({ 
    el: document.getElementById('wall'), 
    showMore: 10 
});
```

## 設定オプションのスタイル設定{#section_ztv_dvb_c1b}

Media Wallには、文字の色、スタイル、サイズをカスタマイズできるいくつかの設定オプションもオファーされています。 これらのオプションを実装するには、次の構文を使用します。

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

有効な入力については、CSS [フォントファミリー](https://www.w3.org/TR/CSS2/fonts.html#propdef-font-family)、[フォントサイズ](https://www.w3.org/TR/CSS2/fonts.html#font-size-props)、[行の高さ、](https://www.w3.org/TR/CSS2/visudet.html#propdef-line-height)、[色](https://www.w3.org/TR/css3-color/#colorunits)のW3C規格を参照してください。

* **bodyFontSize** *(CSS Font Size String)* コンテンツの本文のフォントサイズ。

* **bodyLineHeight** *(CSSの行の高さ*  String)コンテンツの本文の行の高さ。

* **buttonActiveBackgroundColor** *（CSSカラー文字列）**アクティブなボタンの背景のカラー。

* **buttonBorderColor** *(CSS Color String)**ボタンの境界線のカラー。

* **buttonHoverBackgroundColor** *（CSSカラー文字列）* ：カーソルを合わせたときのボタンの背景のカラー。

* **buttonTextColor** *（CSSカラー文字列）* ：ボタンのラベルのカラー。

* **cardBackgroundColor** *（CSSカラー文字列）* ：メディアウォール内のコンテンツカードの背景色。

* **displayNameColor** *（CSSカラー文字列）* 署名内の表示名のカラー。

* **fontFamily** *（CSSフォントファミリー文字列）* 本文のフォントファミリー。

* **footerTextColor** *（CSSカラー文字列）* ：セカンダリテキストのカラー（フッターテキスト、バイライン内のユーザー名など）。

* **linkAttachmentBackgroundColor** *（CSSカラー文字列）* リンク添付ファイル（スタック添付ファイル）の背景色。

* **linkAttachmentBorderColor** *（CSSカラー文字列）* リンク添付ファイル（スタック添付ファイル）の境界線のカラー。

* **linkAttachmentTextColor** *（CSSカラー文字列）* ：リンクの添付テキストのカラー。

* **linkColor** *（CSSカラー文字列）* ハイパーリンク（本文内のリンク、表示名リンクなど）のカラー。

* **textColor** *(CSS Color String)* ：本文のカラー。

* **titleFontSize** *（CSSのフォントサイズ文字列）* コンテンツタイトルのフォントサイズ。

* **titleLineHeight** *(CSSの行の高さ*  String)コンテンツタイトルの行の高さ。

* **sourceLogoColor** *(CSS Color String)* ：ソースロゴのカラー。

* **usernameColor** *(CSS Color String)* ：バイライン内のユーザー名のカラー。
