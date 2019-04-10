---
description: カスタムスタイルは、Somicingコンストラクターに挿入されたオブジェクトを通して適用されます。
seo-description: カスタムスタイルは、Somicingコンストラクターに挿入されたオブジェクトを通して適用されます。
seo-title: siposing Custom Styles
title: siposing Custom Styles
uuid: 0f6d7ad6-1f6a-4ed2- b86a-0d03782e591e
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# siposing Custom Styles{#sidenotes-custom-styles}

カスタムスタイルは、Somicingコンストラクターに挿入されたオブジェクトを通して適用されます。

「キー」はDOM要素を表すオブジェクトキーで、「プロパティ」は特定のキーのCSSプロパティをサポートしています。例えば、blockBtnのスタイルをカスタマイズするために、次のようなオブジェクトを構築するとします。

```
var styles = { 
   'blockBtn': { 
      'fontColor': '#555', 
      'fontSize': '18px' 
   } 
}; 
new Livefyre.Sidenotes({ 
   customStyles: styles, 
      ...  
})
```

| **キー** | **プロパティ** | 説明 |
|---|---|---|
| `anonymousAvatar` | "height"、"width" | テキスト領域エディターの左に表示される匿名アバター画像。 |
| `blockBtn` | 'fontColor'、'fontSize'、'left'、'position'、'right'、'top' | サイトの横に配置される「ランチャーアイコン」は、sidision- ableとして指定されています。 |
| `blockBtnActive` | 'fontColor'、'fontSize'、'left'、'position'、'right'、'top' | アクティブ状態のときのランチャーアイコン。 |
| `commentAvatar` | "height"、"width" | トップレベルのメモの左側にあるアバター画像。 |
| `commentBody` | 'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight' | スレッドメモのテキスト本文。 |
| `commentDisplayName` | 'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight' | メモを離れたユーザーの名前を表示します。 |
| `commentDownvote` | 'fontColor'，'fontSize' | コメントの下に投票ボタンをクリックしてください。 |
| `commentReplyExpand` | backgroundColor、'borderColor'、'borderWidth'、'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight' | 多数の返信を持つ拡張スレッドのボタン。 |
| `commentTags` | 'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight' | メモ上のユーザーに関するタグ。 |
| `commentUpvote` | 'fontColor'，'fontSize' | メモの「アップ投票」ボタンを参照してください。 |
| `editorTextarea` | "height"、"width"、"fontColor"、"fontFamily"、"fontSize"、"fontWeight"、"lineHeight" | メモを残すためのTextarea入力ボックス。 |
| `mediaBlockBtn` | 'fontColor'、'fontSize'、'left'、'position'、'right'、'top' | メディアの上部にあるメディアランチャーアイコン（img、video）。 |
| `mediaBlockBtnActive` | 'fontColor'、'fontSize'、'left'、'position'、'right'、'top' | アクティブ状態のメディアランチャーアイコン。 |
| `numSidenotes` | 'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight'、'lineHeight'、'borderColor'、'borderWidth'、'height'、'width' | コレクション内のSocialの数を示すクリック可能なボタン。 |
| `numSidenotesPopover` | 'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight'、'lineHeight'、'borderColor'、'borderWidth'、'height'、'width' | ポップオーバーを参照してください。 |
| `popover` | 'backgroundColor' | ランチャーアイコンが呼び出されたときに取得されるポップオーバー。 |
| `popoverArrowLeft` | "backgroundImage"、"height"、"left"、"right"、"top"、"width" | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上の左矢印要素。 |
| `popoverArrorRight` | "backgroundImage"、"height"、"left"、"right"、"top"、"width" | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上の右矢印要素。 |
| `popoverArrowTop` | "backgroundImage"、"height"、"left"、"right"、"top"、"width" | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上のトップ矢印要素。 |
| `replyAvatar` | "height"、"width" | 返信レベルのメモの左側にアバター画像。 |
| `streamPoweredBy` | backgroundColor、'borderColor'、'lineHeight' | ポップオーバーの"Powered by"フッター。 |
| `streamQueueButton` | backgroundColor、'borderColor'、'borderWidth'、'fontColor'、'fontFamily'、'fontSize'、'fontWeight'、'lineHeight' | 新しいメモが開いているポップオーバーにいつストリームを流し込むかを示すボタン。 |
| `userAvatar` | "height"、"width" | 認証済みユーザーのアバター画像（テキスト領域エディターの左側）。 |

