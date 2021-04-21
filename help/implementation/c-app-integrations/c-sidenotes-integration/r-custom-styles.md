---
description: カスタムスタイルは、Sidentsコンストラクタに挿入されたオブジェクトを通して適用されます。
title: カスタムスタイルを示す
exl-id: 846605b7-a21e-4600-bf17-18841d2ed96d
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# カスタムスタイルを示す{#sidenotes-custom-styles}

カスタムスタイルは、Sidentsコンストラクタに挿入されたオブジェクトを通して適用されます。

「キー」はDOM要素を表すオブジェクトキーです。「プロパティ」は特定のキーに対してCSSプロパティをサポートしています。 例えば、blockBtn（Sidentプーバーを起動するボタン）のスタイルをカスタマイズするには、次のようなオブジェクトを作成します。

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
| `blockBtn` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | 「表示可能」として指定された要素の横に配置される「ランチャーアイコン」。 |
| `blockBtnActive` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | アクティブ状態のときのランチャーアイコン。 |
| `commentAvatar` | ‘height’、‘width’ | 最上位レベルのメモの左にあるアバター画像。 |
| `commentBody` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | スレッド付きノートのテキスト本文。 |
| `commentDisplayName` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモを残したユーザーの名前を表示します。 |
| `commentDownvote` | 「fontColor」、「fontSize」 | メモの「投票を停止」ボタン。 |
| `commentReplyExpand` | 「backgroundColor」、「borderColor」、「borderWidth」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | 多数の返信を持つスレッドを展開するためのボタン。 |
| `commentTags` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモ上のユーザーに関するタグ。 |
| `commentUpvote` | 「fontColor」、「fontSize」 | メモの「投票」ボタン。 |
| `editorTextarea` | 「height」、「width」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | メモを残すためのテキスト領域入力ボックス。 |
| `mediaBlockBtn` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | メディア項目(img、video)の上に表示された場合のメディアランチャーアイコン |
| `mediaBlockBtnActive` | 「fontColor」、「fontSize」、「left」、「position」、「right」、「top」 | アクティブ状態のメディアランチャーアイコン。 |
| `numSidenotes` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」、「backgroundColor」、「borderColor」、「borderWidth」、「height」、「width」、「width」 | コレクション内のサイト数を表示するクリック可能なボタン。 |
| `numSidenotesPopover` | 「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」、「backgroundColor」、「borderColor」、「borderWidth」、「height」、「width」、「width」 | ユーザーのサイドに関する簡単な説明を含むポーバー。 |
| `popover` | ‘backgroundColor’ | ランチャーアイコンを呼び出したときに表示されるポーバー。 |
| `popoverArrowLeft` | 「backgroundImage」、「height」、「left」、「right」、「top」、「width」 | ランチャーアイコンが含まれているDOM要素を指すポーバー上の左向き矢印要素。 |
| `popoverArrorRight` | 「backgroundImage」、「height」、「left」、「right」、「top」、「width」 | ランチャーアイコンが含まれているDOM要素を指すポーバー上の右向き矢印要素。 |
| `popoverArrowTop` | 「backgroundImage」、「height」、「left」、「right」、「top」、「width」 | ランチャーアイコンを含むDOM要素を指すポーバー上の上向き矢印要素。 |
| `replyAvatar` | ‘height’、‘width’ | 返信レベルのメモの左側のアバター画像。 |
| `streamPoweredBy` | 「backgroundColor」、「borderColor」、「lineHeight」 | 「powered by」フッターがポーバーに表示されます。 |
| `streamQueueButton` | 「backgroundColor」、「borderColor」、「borderWidth」、「fontColor」、「fontFamily」、「fontSize」、「fontWeight」、「lineHeight」 | 開いているポーバーに新しいメモがストリーミングされるタイミングを示すボタンです。 |
| `userAvatar` | ‘height’、‘width’ | テキスト領域エディターの左にある、認証済みユーザーのアバター画像。 |
