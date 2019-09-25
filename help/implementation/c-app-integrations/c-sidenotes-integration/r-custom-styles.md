---
description: カスタムスタイルは、Sidentsコンストラクターに挿入されたオブジェクトを通じて適用されます。
seo-description: カスタムスタイルは、Sidentsコンストラクターに挿入されたオブジェクトを通じて適用されます。
seo-title: カスタムスタイルをサイト表示
title: カスタムスタイルをサイト表示
uuid: 0f6d7ad6-1f6a-4ed2-b86a-0d03782e591e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# カスタムスタイルをサイト表示{#sidenotes-custom-styles}

カスタムスタイルは、Sidentsコンストラクターに挿入されたオブジェクトを通じて適用されます。

「キー」はDOM要素を表すオブジェクトキーですが、「プロパティ」は特定のキーのCSSプロパティでサポートされています。 例えば、blockBtn（Sidenteポーバーを起動するボタン）のスタイルをカスタマイズするには、次のようなオブジェクトを作成します。

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
| `anonymousAvatar` | ‘height’、‘width’ | テキスト領域エディターの左にある匿名アバター画像。 |
| `blockBtn` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | 「ランチャーアイコン」は、サイト表示可能な要素の横に配置されます。 |
| `blockBtnActive` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | アクティブ状態のときのランチャーアイコン。 |
| `commentAvatar` | ‘height’、‘width’ | 最上位レベルのメモの左側のアバター画像。 |
| `commentBody` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | スレッド付きノートのテキスト本文。 |
| `commentDisplayName` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモを残したユーザーの名前を表示します。 |
| `commentDownvote` | 「fontColor」、「fontSize」 | メモの「投票を停止」ボタン。 |
| `commentReplyExpand` | 「backgroundColor」、「borderColor」、「borderWidth」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | 多数の返信を持つスレッドを展開するためのボタン。 |
| `commentTags` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモ上のユーザーに関するタグ。 |
| `commentUpvote` | 「fontColor」、「fontSize」 | メモの上に「賛成票」ボタン。 |
| `editorTextarea` | 「height」、「width」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモを残すためのテキスト領域入力ボックス。 |
| `mediaBlockBtn` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | メディアアイテム(img、video)の上に表示された場合のメディアランチャーアイコン。 |
| `mediaBlockBtnActive` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | アクティブ状態のメディアランチャーアイコン |
| `numSidenotes` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」、「backgroundColor」、「borderColor」、「borderWidth」、「height」、「width」 | コレクション内のサイドの数を表示するクリック可能なボタン。 |
| `numSidenotesPopover` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」、「backgroundColor」、「borderColor」、「borderWidth」、「height」、「width」 | ユーザーのサイドに関する簡単な説明を記載したポーバー。 |
| `popover` | ‘backgroundColor’ | ランチャーアイコンが呼び出されたときに表示されるポーバー。 |
| `popoverArrowLeft` | ‘backgroundImage’、‘height’、‘left’、‘right’、‘top’、‘width’ | ランチャーアイコンを含むDOM要素を指すポーバー上の左向き矢印要素。 |
| `popoverArrorRight` | ‘backgroundImage’、‘height’、‘left’、‘right’、‘top’、‘width’ | ランチャーアイコンを含むDOM要素を指すポーバー上の右矢印要素。 |
| `popoverArrowTop` | ‘backgroundImage’、‘height’、‘left’、‘right’、‘top’、‘width’ | ランチャーアイコンを含むDOM要素を指すポーバー上の上矢印要素。 |
| `replyAvatar` | ‘height’、‘width’ | 返信レベルのメモの左側のアバター画像。 |
| `streamPoweredBy` | 「backgroundColor」、「borderColor」、「lineHeight」 | 「powered by」フッターがポーバーに表示されます。 |
| `streamQueueButton` | 「backgroundColor」、「borderColor」、「borderWidth」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | 開いているポーバーに新しいメモがストリーミングされるタイミングを示すボタンです。 |
| `userAvatar` | ‘height’、‘width’ | 認証済みユーザーのアバター画像（テキスト領域エディターの左）。 |

