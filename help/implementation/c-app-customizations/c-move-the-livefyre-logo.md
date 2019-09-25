---
description: ページ上のLivefyreロゴの位置を変更します。
seo-description: ページ上のLivefyreロゴの位置を変更します。
seo-title: Livefyreロゴの移動
solution: Experience Manager
title: Livefyreロゴの移動
uuid: 807304ae-6070-4505-87db-169a925f714c
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyreロゴの移動{#move-the-livefyre-logo}

ページ上のLivefyreロゴの位置を変更します。

Livefyreとの契約で許可されている場合は、Livefyreロゴをコンテンツストリームの上部から下部に移動できます。

例えば、Livefyreアプリを含む要素の直後のページに次のHTMLを追加します。

```
<div id="powered_by_livefyre_new"><a href="https://livefyre.com" target="_blank">Powered by Livefyre</a></div>
```

次に、ページのスタイルシートに次を追加します。

```
/* Hide the top logo */ 
.fyre-widget .fyre-logo-drop, .fyre-widget .fyre-logo-help, .fyre-widget .fyre-help { 
    display:none !important; 
} 
  
/* Style the bottom logo */ 
#powered_by_livefyre_new a {    background: url(https://cdn.livefyre.com/libs/fyre.conv/v3.0.0/images/poweredbylivefyre.png) no-repeat left top; 
    display: block; 
    height: 24px; 
    font: 13px "Helvetica Neue", Helvetica, Arial, Geneva, sans-serif; 
    text-decoration: none; 
    color: #404040; 
    padding-left: 28px; 
    padding-top: 4px; 
} 
#powered_by_livefyre_new a:hover { 
    text-decoration: underline; 
}
```

