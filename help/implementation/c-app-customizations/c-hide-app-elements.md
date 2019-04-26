---
description: アプリケーションから標準のLivefyreアプリコンポーネントを削除します。
seo-description: アプリケーションから標準のLivefyreアプリコンポーネントを削除します。
seo-title: アプリ要素を非表示にする
solution: Experience Manager
title: アプリ要素を非表示にする
uuid: ea090b6e-99f5-4bd7- aa9e- d39a4dff1543
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# アプリ要素を非表示にする{#hide-app-elements}

アプリケーションから標準のLivefyreアプリコンポーネントを削除します。

CSSを使用して、ページからデフォルトのLivefyreアプリ要素を非表示にし、ニーズに合わせてユーザーエクスペリエンスをカスタマイズできます。

アプリから要素を非表示にするには、表示を「なし」に設定します。

例：

```
/* Hide the 'reply' button */ 
.fyre-comment-reply { 
    display: none !important; 
} 
  
/* Hide all user avatars */ 
.fyre-comment-user .fyre-mention-item-avatar .fyre-listener-avatars .fyre-avatar fyre-user-avatar-25 { 
    display: none !important; 
} 
.fyre-comment-head .fyre-comment-body .fyre-comment-footer .fyre-comment-divider { 
    margin-left: 0; 
} 
  
/* Hide 'Edit Profile' link */ 
.fyre-edit-profile-link { 
    display: none !important; 
} 
  
/* Hide 'Logout' link */ 
.fyre-logout-link { 
    display: none; 
} 
  
/* Hide 'Comment Notifier' */ 
.fyre-notifier-message { 
    display:none; 
}
```

