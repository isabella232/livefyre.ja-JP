---
description: ユーザーグループのカスタムスタイルコンテンツを作成するには、最初にユーザータグをアカウントに追加し、次にCSSを使用してコンテンツのスタイルを設定する必要があります。
title: カスタムスタイルの適用
exl-id: 54692525-32ce-487a-b3c3-da1261b58da1
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# カスタムスタイルの適用{#applying-custom-styles}

ユーザーグループのカスタムスタイルコンテンツを作成するには、最初にユーザータグをアカウントに追加し、次にCSSを使用してコンテンツのスタイルを設定する必要があります。

StudioまたはPingでPull用に追加された各ユーザータグに対して、Livefyreは2つのCSSクラスを作成します。両方のCSSクラスを使用して、グループのコンテンツのスタイルを設定できます。

ユーザタグをCSSクラスに変換する場合：

* Livefyreは2つのクラスを作成します。fyre-author-tag-**&lt;your_group>***およびfyre-tag-author-**&lt;your_group>***. 両方を使用して、コンテンツのスタイルを設定できます。

* タグに含まれるスペースはすべてアンダースコアに変換されます。 次に例を示します。「お気に入りユーザー」がfavorite_userになります。
* グループ名に含まれるUnicode文字は変換されず、クラス名にUnicodeとして表示されます。 次に例を示します。ユーザーグループ「modérature」がfyre-comment-author-tag-moderaturになります。

ユーザーグループを作成したら、LivefyreのCSSクラスを使用して、コンテンツのカスタムスタイル設定を適用します。

## モデレーター（および所有者）のスタイルコンテンツ{#section_vjv_2cv_xz}

* CSSクラス.fyre-moderatorを使用します。

   >[!NOTE]
   >
   >所有者もモデレーターなので、このクラスはストリーム内のコンテンツにも適用されます。

* CSSルールを作成して、グループのバッジを表示またはスタイル設定します。

   ```
   .fyre-moderator { 
       font: 13px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
       text-decoration: none; 
       color: #404040; 
       padding-left: 28px; 
       padding-top: 4px; 
   }
   ```

## ユーザーグループのスタイル内容{#section_ghn_s1v_xz}

CSSルールを作成して、グループのバッジを表示またはスタイル設定します。

```
<span class="fyre-comment-author-tag fyre-comment-author-tag-writer fyre-comment-plus" data-fyre-author-tag="staff">Staff Writer</span>
```

```
.livechat-comments-container .fyre .fyre-comment-wrapper .fyre-comment-author-tag, .comments-container .fyre .fyre-comment-wrapper .fyre-comment-author-tag { 
    display: inline-block !important; 
    background: #603url('/etc/designs/site/images/comments-icon-staff.8db5be91.png?1438807177') no-repeat left center !important; 
    padding-right: 3px !important; 
    padding-left: 20px !important; 
    text-transform: uppercase !important; 
    font-weight: bold !important; 
    font-size: 11px !important; 
    border-radius: 0 !important; 
    color: #ffffff !important; 
}
```

CSSクラスfyre-author-tag-**&lt;your_group>***またはfyre-tag-author-**&lt;your_group>***を使用して、選択したタグに関連付けられたアカウントから投稿された各項目のフォントと背景のスタイルを設定します。

```
.fyre-comment-author-tag-<your_group> .fyre-comment-author-tag { 
    font: 10px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
    text-decoration: none; 
    color: #404040; 
    padding-left: 28px; 
    padding-top: 4px; 
}
```
