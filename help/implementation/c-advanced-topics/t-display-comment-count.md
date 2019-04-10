---
description: 特定のコレクションの投稿数とコメント数を取得して、索引ページに表示します。
seo-description: 特定のコレクションの投稿数とコメント数を取得して、索引ページに表示します。
seo-title: コメント数を表示
solution: Experience Manager
title: コメント数を表示
uuid: 0f39b25e-11e0-4945- be71-55fb4798b6c7
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# コメント数を表示{#display-comment-count}

特定のコレクションの投稿数とコメント数を取得して、索引ページに表示します。

Livefyreでは `CommentCount.js` 、サイト上のコレクションのコンテンツカウントを取得できます。アプリには現在のコレクションのコメント数が表示されますが、これらのカウントはサイト全体で同期されるので便利です。この機能は、データベースにコンテンツを永続化しない（またはCMSデータベースがLivefyreと同期されていない場合）場合に特に便利です。

1. JavaScriptをロードします。

   使用 `CommentCount.js`するには、まず、使用したいページまたはテンプレートの `<head>` セクションにJavaScriptファイルを埋め込みます。

   ```
   <script 
      type="text/javascript" 
      data-lf-domain="{network name (domain.fyre.co)}" 
      src="//cdn.livefyre.com/libs/commentcount/v1.0/commentcount.js"> 
   </script>
   ```

1. HTML要素の連結を参照してください。

   スクリプトがロードされると、そのページにはクラス名のある他の要素が検索され `livefyre-commentcount`ます。これらの要素ごとに、スクリプトはHTML属性 `data-lf-site-id` を探し `data-lf-article-id` 、HTML属性を使用して、Livefyreからコンテンツを取得し、各要素を最新の値で更新します。

   例えば、次の要素が更新されます。

   ```
   <span class="livefyre-commentcount" data-lf-site-id="{site_id}" data-lf-article-id="{article_id}"> 
   0 Comments  
   </span>
   ```

   >[!NOTE] {importance="high"}
   >
   >`CommentCount.js` コードは、実際の数で更新する数値をチェックします。タグ間に数値を含めることもできます。

   **例1** （記事IDとしてURLを使用）

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="https://mikesoldner.com/blog.php">  
   0 Comments  
   </span>
   ```

   **例2** （番号付けされたシステムを記事IDとして使用）:

   ```
   <span class="livefyre-commentcount" data-lf-site-id="311458" data-lf-article-id="25"> 0 Comments </span>
   ```

1. オプションの設定を参照してください。

   コンテンツのカウントがどのように置換されるかを制御するには、設定オプションを含むオブジェクトを呼び出し `LF.CommentCount()` て渡します。置き換える必要のあるすべての要素がDOMに含まれている場合は、関数を必ず呼び出してください。このメソッドを呼び出す最適な場所はフッターであり、DOMが読み込まれたとき、ドキュメントおよびウィンドウの準備完了イベントの前に発生します。

   以下の設定オプションを使用できます。

* **replacer:** 各コンテンツカウントのテキストを置き換える関数または正規表現。

* **関数:** 各要素の置換の実行に使用します。関数の引数は次のとおりです。

   **エレメント:** 更新されているHTML要素です。
   **カウント:** この要素のコンテンツカウント。

* **regex:** 要素のテキストのどの部分をカウントに置き換えるかを指定するために使用します。

   **例**:

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
   >replacerを使用して、コメントカウントメッセージをカスタマイズまたは国際化します。
