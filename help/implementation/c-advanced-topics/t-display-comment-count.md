---
description: 特定のコレクションの投稿数とコメント数を取得して、インデックスページに表示します。
title: コメント数を表示
exl-id: 03c911f0-1fdd-4d5c-9262-9ff7485b7b14
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---

# コメント数を表示{#display-comment-count}

特定のコレクションの投稿数とコメント数を取得して、インデックスページに表示します。

Livefyreの`CommentCount.js`では、サイト上のコレクションのコンテンツ数を取得できます。 アプリでは現在のコレクションのコメント数が表示されますが、サイト全体でこれらのコメント数を同時配分すると便利です。 この機能は、データベース内のコンテンツを保持しない（またはCMSデータベースがLivefyreと同期されない）場合に特に便利です。

1. JavaScriptを読み込みます。

   `CommentCount.js`を使用するには、まず、使用するページまたはテンプレートの`<head>`セクションにJavaScriptファイルを埋め込みます。

   ```
   <script 
      type="text/javascript" 
      data-lf-domain="{network name (domain.fyre.co)}" 
      src="//cdn.livefyre.com/libs/commentcount/v1.0/commentcount.js"> 
   </script>
   ```

1. HTML要素を連結します。

   スクリプトが読み込まれると、`livefyre-commentcount`というクラス名を持つ他の要素がページ上で検索されます。 これらの各エレメントに対して、スクリプトは`data-lf-site-id`と`data-lf-article-id`のHTML属性を探し、それらを使用してLivefyreからコンテンツを取得し、各要素を最新の値に更新します。

   例えば、次の要素は更新されます。

   ```
   <span class="livefyre-commentcount" data-lf-site-id="{site_id}" data-lf-article-id="{article_id}"> 
   0 Comments  
   </span>
   ```

   >[!NOTE]
   >
   >`CommentCount.js`コードは、実際の数で更新する数値を確認します。 タグの間に必ず数値を含めてください。

   **例1** （URLを記事IDとして使用する）:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="https://mikesoldner.com/blog.php">  
   0 Comments  
   </span>
   ```

   **例2** （番号付きのシステムを記事IDとして使用する）:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="25"> 0 Comments </span>
   ```

1. オプションを設定します。

   コンテンツカウントの置き換え方法を制御するには、`LF.CommentCount()`を呼び出して、設定オプションを含むオブジェクトを渡します。 置換する必要のあるすべての要素がDOMに含まれている場合は、必ず関数を呼び出してください。 このメソッドを呼び出すのに最適な場所はフッターです。このメソッドは、DOMが読み込まれるが、ドキュメントおよびウィンドウ対応イベントの前に発生します。

   次の設定オプションを使用できます。

* **replacer:** 各コンテンツカウントのテキストを置き換えるために使用する関数またはRegexです。

* **関数：各要素で置換を行うために** 使用します。関数の引数は次のとおりです。

   **element:** 更新中のHTML要素。
   **count:** この要素のコンテンツ数。

* **regex:** 要素のテキストのどの部分をカウントに置き換えるかを決定するために使用します。

   **例**：

   ```
      <script type="text/javascript"> LF.CommentCount({ 
        replacer: function(element, count) { 
            element.innerHTML = count +' Comment'+ (count === 1 ? '' : 's'); 
        } 
    }); 
   </script>
   ```

   >[!NOTE]
   >
   >置き換え子を使用して、コメント数のメッセージをカスタマイズまたは国際化します。
