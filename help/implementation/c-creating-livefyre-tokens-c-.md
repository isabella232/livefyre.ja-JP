---
description: "C#"言語を使用してLivefyreトークンを生成する方法について説明します。
seo-description: "C#"言語を使用してLivefyreトークンを生成する方法について説明します。
seo-title: Livefyreトークン"C#"を作成
solution: Experience Manager
title: Livefyreトークン"C#"を作成
uuid: c5e05625-8550-4b51-9211-134600e20ec7
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyre Tokens C\#の作成 {#creating-livefyre-tokens-c}

C 系言語の ``C#`` 言語を使用して Livefyre トークンを生成する方法について説明します。

既存のドキュメントおよびサンプルコードを活用して、トークンを作成 `C#.NET` するためのメソッドを作成できます。

Livefyreの公式ライブラリを参照するには、Javaライブラリを [開発者](https://github.com/Livefyre/livefyre-java-utils) の `C#` 基礎として使用してください。

また、コマンドラインから [Node. jsライブラリ](https://github.com/Livefyre/livefyre-nodejs-utils) を使用して、自分自身の参照トークンを生成し、メソッド構造を理解することもできます。

* [コレクションメタトークンにジャンプ](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-collectionMeta-token)
* [認証トークンへのジャンプ](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-auth-token)

## 依存関係 {#section_c15_fnh_xz}

* トークンを生成するには、プロジェクトで [JWT ngetパッケージ](https://www.nuget.org/packages/JWT) が必要です。
* このページのコードサンプルは [、Newtonsoft JSON](https://www.nuget.org/packages/newtonsoft.json/) パッケージを使用します。

## CollectionMetaトークン {#section_dzt_4mh_xz}

このCollectionMetaトークンは、ページにコメントを埋め込むときにLivefyreに渡され、新しいコレクションに必要なメタデータをシステムに提供します。さらに、このデータのMD5 `checksum` を作成し、Livefyreはメタデータが変更されたかどうかを確認します。（記事のタイトルまたはURLが編集された場合など）。

このトークンは、 `Site Key`Livefyreの担当コンサルタントによってあなたに提供されたトークンで署名されます。

関連トピック:

* 公式CollectionMetaトークンドキュメント
* [サンプルの例](https://gist.github.com/pcolombo/dbbea020618c521a2bd5)

1. コレクションのメタデータを含む辞書を構築します。この手順で必要なフィールドの一部を追加します。ここで、ArticleIDを追加する前に、このオブジェクトのチェックサムを作成してください。

   ```
       // Site Key provided by Livefyre 
       string siteSecret = "ABCDE1234"; 
   
       var meta = new Dictionary<string, object>() { 
           {"title", "Kings win the Stanley Cup"}, 
           {"url", "https://www.website.com/kings-win-stanley-cup"}, 
           {"tags", "sports, hockey, stanley_cup"}, 
           {"type", "livecomments"} 
       };
   ```

   * **title** *required*:コレクションのタイトル。通常は記事のタイトルです。最大長は255文字です。htmlエンティティはサポートしません。UTF-8を使用して特殊文字をエンコードしてください。
   * **URL***が必要*:記事の正規URL。これは、コメント共有およびソーシャル同期機能によって使用され、管理ダッシュボードから記事へのリンクです。ローカルでテストする場合、Livefyreはドメインとして"localhost"を受け入れません。
   * **タグ** の *オプション*:Livefyreダッシュボードでコレクションに追加するタグのコンマ区切りリストです。タグにスペースを含めることはできません。管理ダッシュボードにスペースを表示するには、アンダースコアを使用します。
   * **type***オプション*:作成するコレクションのタイプを示す文字列。有効な値は次のとおりです。

      * `reviews`
      * `sidenotes`
      * `ratings`
      * `counting`
      * `livecomments`
      * `liveblog`
      * `livechat`
      指定しなかった場合、デフォルトでLiveCommentsコレクションが作成されます。


1. JSONはこの辞書をエンコードし、md5チェックサムを生成します。

   ```
          var metaStr = JsonConvert.SerializeObject(meta); 
       byte[] hash; 
   
       using (var md5 = MD5.Create()) 
       { 
           hash = md5.ComputeHash(Encoding.UTF8.GetBytes(metaStr)); 
       } 
   
       StringBuilder sBuilder = new StringBuilder(); 
   
       // Loop through each byte of the hashed data  
       // and format each one as a hexadecimal string  
       for (int i = 0; i < hash.Length; i++) 
       { 
           sBuilder.Append(hash[i].ToString("x2")); 
       } 
   ```

1. **ArticleID** を辞書に追加します。**チェックサム** はCollectionMetaトークンには含まれませんが、sendConfig jsオブジェクトのseaprateパラメーターとして送信する必要があります。

   ```
       meta.Add("articleId", "article-abcde00001"); 
   ```

   * **articleID***が必要*:Livefyreサイト内のコレクションの一意の識別子。通常、CMSで使用される一意のarticleIDです。（例: WordPress投稿ID）この値は変更しないでください。Livefyreは、SiteIDとArticleIDの組み合わせによって一意のコレクションを識別します。

1. Livefyreが提供するSite Keyを使用して、辞書の署名付きJWTトークンを生成します。JWTパッケージはデフォルトでHS256を使用しないので、正しいハッシュアルゴリズムを指定する必要があります。

   ```
       string token = JWT.JsonWebToken.Encode(meta, siteSecret, JWT.JwtHashAlgorithm.HS256);
   ```

## User Authトークン {#section_g1d_43h_xz}

ユーザー認証トークンは、Livefyreへのユーザーへの署名に使用されます。ユーザーがサイトにサインインすると、そのページ上のLivefyreウィジェットに渡されるUser Authトークンが生成されます。（認証プロセスについて詳しくは、リモートプロファイルを参照してください）。

このトークンにはネットワーク名（network. fyre. co）が必要で、Livefyreのテクニカルアカウントマネージャーから提供されるネットワークキーで署名されています。

関連トピック:

* 公的認証トークンドキュメント
* [サンプルの例](https://gist.github.com/pcolombo/7d7403172c28734c87e2)

1. 必要な情報を含むディコトーンを作成します。

   ```
       string networkKey = "ABCDEF1234"; 
   
       var payload = new Dictionary<string, object>() {  
               { "domain", "mynetwork.fyre.co" }, 
               { "user_id", "user-00001" }, 
               { "expires", DateTime.Now.AddDays(7).Ticks }, 
               { "display_name", "johndoe" } 
           }; 
   ```

   * **domain:** ネットワークの名前（Livefyreが提供します）例mynetwork. fyre. co
   * **user_ id:** サイトのプロファイルシステムにおけるユーザーの一意のユーザーID。英数字のみ（A~ Z、a~ z、0~9）にする必要があります。システムユーザーIDに無効なCharaactersが含まれている場合は、ユーザーIDのmd5ハッシュまたはbase64エンコードバージョンのLivefyreを送信することを検討してください。（アカウントマネージャーにお問い合わせください。）
   * **有効期限:** トークンが期限切れになる日付（エポック時間）。これは、サイト上のログインのセッション時間と一致する必要があります。これにより、Livefyreのログイン状態がサイトのサインイン状態と同期し続けるようになります。
   * **display_ name:** プロファイルシステムに表示されるユーザーの表示名。コメントストリームに表示する必要があります。

1. Livefyreが提供するネットワークキーを使用して、辞書の署名付きJWTトークンを生成します。JWTパッケージはデフォルトでHS256を使用しないので、正しいハッシュアルゴリズムを指定する必要があります。

   ```
          string token = JWT.JsonWebToken.Encode(payload, networkKey, JWT.JwtHashAlgorithm.HS256);
   ```
