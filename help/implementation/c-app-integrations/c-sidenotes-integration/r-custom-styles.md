---
description: カスタムスタイルは、Somicingコンストラクターに挿入されたオブジェクトを通して適用されます。
seo-description: カスタムスタイルは、Somicingコンストラクターに挿入されたオブジェクトを通して適用されます。
seo-title: siposing Custom Styles
title: siposing Custom Styles
uuid: 0f6d7ad6-1f6a-4ed2- b86a-0d03782e591e
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

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
| `anonymousAvatar` | &quot;height&quot;、&quot;width&quot; | テキスト領域エディターの左に表示される匿名アバター画像。 |
| `blockBtn` | &#39;fontColor&#39;、&#39;fontSize&#39;、&#39;left&#39;、&#39;position&#39;、&#39;right&#39;、&#39;top&#39; | サイトの横に配置される「ランチャーアイコン」は、sidision- ableとして指定されています。 |
| `blockBtnActive` | &#39;fontColor&#39;、&#39;fontSize&#39;、&#39;left&#39;、&#39;position&#39;、&#39;right&#39;、&#39;top&#39; | アクティブ状態のときのランチャーアイコン。 |
| `commentAvatar` | &quot;height&quot;、&quot;width&quot; | トップレベルのメモの左側にあるアバター画像。 |
| `commentBody` | &#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39; | スレッドメモのテキスト本文。 |
| `commentDisplayName` | &#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39; | メモを離れたユーザーの名前を表示します。 |
| `commentDownvote` | &#39;fontColor&#39;，&#39;fontSize&#39; | コメントの下に投票ボタンをクリックしてください。 |
| `commentReplyExpand` | backgroundColor、&#39;borderColor&#39;、&#39;borderWidth&#39;、&#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39; | 多数の返信を持つ拡張スレッドのボタン。 |
| `commentTags` | &#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39; | メモ上のユーザーに関するタグ。 |
| `commentUpvote` | &#39;fontColor&#39;，&#39;fontSize&#39; | メモの「アップ投票」ボタンを参照してください。 |
| `editorTextarea` | &quot;height&quot;、&quot;width&quot;、&quot;fontColor&quot;、&quot;fontFamily&quot;、&quot;fontSize&quot;、&quot;fontWeight&quot;、&quot;lineHeight&quot; | メモを残すためのTextarea入力ボックス。 |
| `mediaBlockBtn` | &#39;fontColor&#39;、&#39;fontSize&#39;、&#39;left&#39;、&#39;position&#39;、&#39;right&#39;、&#39;top&#39; | メディアの上部にあるメディアランチャーアイコン（img、video）。 |
| `mediaBlockBtnActive` | &#39;fontColor&#39;、&#39;fontSize&#39;、&#39;left&#39;、&#39;position&#39;、&#39;right&#39;、&#39;top&#39; | アクティブ状態のメディアランチャーアイコン。 |
| `numSidenotes` | &#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39;、&#39;lineHeight&#39;、&#39;borderColor&#39;、&#39;borderWidth&#39;、&#39;height&#39;、&#39;width&#39; | コレクション内のSocialの数を示すクリック可能なボタン。 |
| `numSidenotesPopover` | &#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39;、&#39;lineHeight&#39;、&#39;borderColor&#39;、&#39;borderWidth&#39;、&#39;height&#39;、&#39;width&#39; | ポップオーバーを参照してください。 |
| `popover` | &#39;backgroundColor&#39; | ランチャーアイコンが呼び出されたときに取得されるポップオーバー。 |
| `popoverArrowLeft` | &quot;backgroundImage&quot;、&quot;height&quot;、&quot;left&quot;、&quot;right&quot;、&quot;top&quot;、&quot;width&quot; | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上の左矢印要素。 |
| `popoverArrorRight` | &quot;backgroundImage&quot;、&quot;height&quot;、&quot;left&quot;、&quot;right&quot;、&quot;top&quot;、&quot;width&quot; | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上の右矢印要素。 |
| `popoverArrowTop` | &quot;backgroundImage&quot;、&quot;height&quot;、&quot;left&quot;、&quot;right&quot;、&quot;top&quot;、&quot;width&quot; | ランチャーアイコンを含むDOM要素をポイントする、ポップオーバー上のトップ矢印要素。 |
| `replyAvatar` | &quot;height&quot;、&quot;width&quot; | 返信レベルのメモの左側にアバター画像。 |
| `streamPoweredBy` | backgroundColor、&#39;borderColor&#39;、&#39;lineHeight&#39; | ポップオーバーの&quot;Powered by&quot;フッター。 |
| `streamQueueButton` | backgroundColor、&#39;borderColor&#39;、&#39;borderWidth&#39;、&#39;fontColor&#39;、&#39;fontFamily&#39;、&#39;fontSize&#39;、&#39;fontWeight&#39;、&#39;lineHeight&#39; | 新しいメモが開いているポップオーバーにいつストリームを流し込むかを示すボタン。 |
| `userAvatar` | &quot;height&quot;、&quot;width&quot; | 認証済みユーザーのアバター画像（テキスト領域エディターの左側）。 |

