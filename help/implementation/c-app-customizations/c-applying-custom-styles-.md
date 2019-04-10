---
description: ユーザーグループのカスタムスタイルコンテンツを作成するには、まずアカウントにユーザータグを追加し、CSSを使用してコンテンツのスタイルを設定する必要があります。
seo-description: ユーザーグループのカスタムスタイルコンテンツを作成するには、まずアカウントにユーザータグを追加し、CSSを使用してコンテンツのスタイルを設定する必要があります。
seo-title: カスタムスタイルの適用
solution: Experience Manager
title: カスタムスタイルの適用
uuid: 0556aa2f-4fcd-4bde- abb5-479ec682f573
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# カスタムスタイルの適用{#applying-custom-styles}

ユーザーグループのカスタムスタイルコンテンツを作成するには、まずアカウントにユーザータグを追加し、CSSを使用してコンテンツのスタイルを設定する必要があります。

Studioによって追加されたユーザータグごとに、Livefyreは2つのCSSクラスを作成します。これらのクラスは共に、グループのコンテンツのスタイル設定に使用できます。

User TagをCSSクラスに変換するとき:

* Livefyreによって2つのクラスが作成されます。fyre- author- tag-***< your_ group>*** and fyre- tag- author-***< your_ group>***.どちらもコンテンツのスタイル設定に使用できます。

* タグに含まれるスペースは、アンダースコアに変換されます。次に例を示します。「お気に入りユーザー」はお気に入り_ userになります。
* グループ名に含まれるUnicode文字は変換されず、クラス名にUnicodeとして表示されます。次に例を示します。ユーザーグループ"modérateur"は、fyre- comment- author- tag- modérateurになります。

ユーザーグループを作成したら、LivefyreのCSSクラスを使用してコンテンツのカスタムスタイル設定を適用します。

## モデレーター（および所有者）のスタイルコンテンツの設定 {#section_vjv_2cv_xz}

* CSSクラス. fyre-モデレーターを使用します。

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

## ユーザーグループのスタイルコンテンツ {#section_ghn_s1v_xz}

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

選択したタグに関連付けられているアカウントから投稿された各項目のフォントと背景のスタイルを設定するには、CSSクラスfyre- author- tag-***< your_ group>***またはfyre- tag- author-***< your_ group>***を使用します。

```
.fyre-comment-author-tag-<your_group> .fyre-comment-author-tag { 
    font: 10px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
    text-decoration: none; 
    color: #404040; 
    padding-left: 28px; 
    padding-top: 4px; 
}
```

