---
description: Livefyre.jsは、サイト上のアプリに認証を提供する小規模なベースライブラリです。
title: 追加Livefyre.jsのページへの追加
exl-id: 4c5dfb31-b7e5-48f7-826c-cddbee06d876
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 1%

---

# 追加Livefyre.jsのページ{#add-livefyre-js-to-the-page}

Livefyre.jsは、サイト上のアプリに認証を提供する小規模なベースライブラリです。

認証を有効にするには：

1. 追加WebページまたはWebサイトテンプレートの`<head>`要素にLivefyre.jsを設定します。
1. ページに追加次のいずれかの操作を行います。

   * `globalwindow.Livefyre` variable
   * `Livefyre.require` 他のLivefyreパッケージを必要に応じて読み込むには

      ```
      <script src="//cdn.livefyre.com/Livefyre.js"></script>
      ```
