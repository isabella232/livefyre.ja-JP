---
description: 特定のコレクションの投稿数とコメント数を取得して、インデックスページに表示します。
seo-description: 特定のコレクションの投稿数とコメント数を取得して、インデックスページに表示します。
seo-title: コメント数を表示
solution: Experience Manager
title: コメント数を表示
uuid: 0f39b25e-11e0-4945-be71-55fb4798b6c7
translation-type: tm+mt
source-git-commit: c287e7a880f956f0444af746adee682571fe5a72

---


# コメント数を表示{#display-comment-count}

特定のコレクションの投稿数とコメント数を取得して、インデックスページに表示します。

Livefyreでは、サイ `CommentCount.js` ト上のコレクションのコンテンツ数を取得できます。 「アプリ」には現在のコレクションのコメント数が表示されますが、サイト全体でこれらの数を同時に表示すると便利です。 この機能は、データベース内のコンテンツを保持しない（またはCMSデータベースがLivefyreと同期されない）場合に特に便利です。

1. JavaScriptを読み込みます。

   使用する `CommentCount.js`には、まず、JavaScriptファイルを使用するペ `<head>` ージまたはテンプレートのセクションに埋め込みます。

   ```
   <script 
      type="text/javascript" 
      data-lf-domain="{network name (domain.fyre.co)}" 
      src="//cdn.livefyre.com/libs/commentcount/v1.0/commentcount.js"> 
   </script>
   ```

1. HTML要素を連結します。

   スクリプトが読み込まれると、クラス名がという他の要素がページ上で検索されます `livefyre-commentcount`。 これらの各要素に対して、スクリプトは `data-lf-site-id``data-lf-article-id` HTML属性とHTML属性を探し、これらを使用してLivefyreからコンテンツを取得し、各要素を最新の値で更新します。

   例えば、次の要素が更新されます。

   ```
   <span class="livefyre-commentcount" data-lf-site-id="{site_id}" data-lf-article-id="{article_id}"> 
   0 Comments  
   </span>
   ```

   >[!NOTE] {importance="high"}
   >
   >コー `CommentCount.js` ドは、実際の数で更新する数値を確認します。 タグの間に必ず数値を含めてください。

   **例1** （URLを記事IDとして使用）:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="https://mikesoldner.com/blog.php">  
   0 Comments  
   </span>
   ```

   **例2** （番号付きシステムを記事IDとして使用する）:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="25"> 0 Comments </span>
   ```

1. オプションを設定します。

   コンテンツ数の置き換え方法をより詳細に制御するには、設定オプシ `LF.CommentCount()` ョンを含むオブジェクトを呼び出して渡します。 置き換える必要があるすべての要素がDOM内にある場合は、必ず関数を呼び出してください。 このメソッドを呼び出すのに最適な場所はフッター内にあるので、DOMが読み込まれるが、ドキュメントおよびウィンドウ準備完了イベントの前に発生します。

   次の設定オプションを許可します。

* **** replacer:各コンテンツカウントのテキストを置き換えるために使用される関数またはRegexです。

* **** 関数：各要素で置換を行うために使用します。 関数の引数は次のとおりです。

   **** element:更新中のHTML要素です。
   **** count:この要素のコンテンツ数。

* **** regex:要素のテキストのどの部分を数で置き換えるかを決定するために使用します。

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
   >置換機能を使用して、コメント数のメッセージをカスタマイズまたは国際化します。
