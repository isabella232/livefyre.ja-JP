---
description: C 系言語の `C#` 言語を使用して Livefyre トークンを生成する方法について説明します。
seo-description: C 系言語の `C#` 言語を使用して Livefyre トークンを生成する方法について説明します。
seo-title: Livefyreトークン'C#'の作成
solution: Experience Manager
title: Livefyreトークン'C#'の作成
uuid: c5e05625-8550-4b51-9211-134600e20ec7
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Livefyreトークンの作成C\# {#creating-livefyre-tokens-c}

C 系言語の ``C#`` 言語を使用して Livefyre トークンを生成する方法について説明します。

従来のドキュメントとサンプルコードを活用して、トークンを作成す `C#.NET` るメソッドを記述できます。

Livefyreの公式ライブラリを参照するには、開発者の出発点 [として](https://github.com/Livefyre/livefyre-java-utils) Javaライブラリを使用 `C#` します。

コマンドラインから [Node.js Libraryを使用して](https://github.com/Livefyre/livefyre-nodejs-utils) 、参照トークンを自分で生成し、メソッドの構造を理解することもできます。

* [コレクションメタトークンにジャンプ](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-collectionMeta-token)
* [認証トークンに移動](https://gist.github.com/gibron/56cb9c7060bf4816c4c5#the-auth-token)

## 依存関係 {#section_c15_fnh_xz}

* トークンを生成するに [は](https://www.nuget.org/packages/JWT) 、プロジェクトにJWT Nugetパッケージが必要です。
* このページのコードサンプルでは [Newtonsoft JSONパッケージを使用します](https://www.nuget.org/packages/newtonsoft.json/) 。

## CollectionMeta Token {#section_dzt_4mh_xz}

ページにコメントを埋め込むと、CollectionMeta TokenがLivefyreに渡され、新しいコレクションに必要なメタデータがアドビのシステムに提供されます。 また、このデータのMD5を作成し、Livefyre `checksum` がメタデータが変更されたかどうかを確認します。 （例：記事のタイトルやURLが編集された場合）。

このトークンは、Livefyreのテクニカルア `Site Key`カウントマネージャーから提供された、お客様と共に署名されます。

以下のページも参照してください。

* 公式CollectionMeta Token Docs
* [要旨の例](https://gist.github.com/pcolombo/dbbea020618c521a2bd5)

1. コレクションのメタデータを含む辞書を作成します。 この手順では、必要なフィールドの一部のみを追加します。これは、articleIdを追加する前に、このオブジェクトのチェックサムを作成するためです。

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

   * **title** *required*: コレクションのタイトル。通常は記事のタイトルです。 最大長は255文字です。 htmlエンティティをサポートしません。 UTF-8を使用して特殊文字をエンコードしてください。
   * **url** *required*: 記事の正規URL。 これは、コメントの共有機能とソーシャル同期機能、および管理ダッシュボードから記事へのリンクによって使用されます。 ローカルでテストする場合、Livefyreは「localhost」をドメインとして受け入れないことに注意してください。
   * **tags** *optional*: Livefyreダッシュボードでコレクションに追加するタグのコンマ区切りリストです。 タグにスペースを含めることはできません。 アンダースコアは、管理ダッシュボードにスペースを表示する場合に使用します。
   * **type** optional **: 作成するコレクションの種類を示す文字列です。 有効値は次のとおりです。

      * `reviews`
      * `sidenotes`
      * `ratings`
      * `counting`
      * `livecomments`
      * `liveblog`
      * `livechat`
      指定しなかった場合、LiveCommentsコレクションがデフォルトで作成されます。


1. JSONはこのディクショナリをエンコードし、そのmd5チェックサムを生成します。

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

1. articleIdを辞 **書に追** 加します。 checksum **はcollectionMetaトークンに渡されませんが** 、convConfig jsオブジェクト内のseaprateパラメーターとして送信する必要があります。

   ```
       meta.Add("articleId", "article-abcde00001"); 
   ```

   * **articleId** required **: Livefyreサイト内のコレクションの一意の識別子。 通常、CMSで使用される一意のarticleIdです。 （例えば、WordPress投稿ID）この値は変更しないでください。 Livefyreは、siteIdとarticleIdの組み合わせによって一意のコレクションを識別します。

1. Livefyreから提供されたサイトキーを使用して、辞書の署名済みJWTトークンを生成します。 JWTパッケージはデフォルトでHS256を使用しないので、正しいハッシュアルゴリズムを指定する必要があります。

   ```
       string token = JWT.JsonWebToken.Encode(meta, siteSecret, JWT.JwtHashAlgorithm.HS256);
   ```

## ユーザー認証トークン {#section_g1d_43h_xz}

ユーザー認証トークンは、Livefyreへのユーザーの署名に使用されます。 ユーザーがサイトにログインすると、そのサイトで、ページ上のLivefyreウィジェットに渡されるユーザー認証トークンが生成されます。 （認証プロセスについて詳しくは、「リモートプロファイル」を参照してください。）

このトークンは、お客様のネットワーク名(network.fyre.co)が必要で、Livefyreのテクニカルアカウントマネージャーから提供される、お客様のネットワークキーを使用して署名されています。

以下のページも参照してください。

* 公式認証トークンドキュメント
* [要旨の例](https://gist.github.com/pcolombo/7d7403172c28734c87e2)

1. 必要な情報を含む辞書を作成します。

   ```
       string networkKey = "ABCDEF1234"; 
   
       var payload = new Dictionary<string, object>() {  
               { "domain", "mynetwork.fyre.co" }, 
               { "user_id", "user-00001" }, 
               { "expires", DateTime.Now.AddDays(7).Ticks }, 
               { "display_name", "johndoe" } 
           }; 
   ```

   * **** ドメイン：ネットワークの名前（Livefyreから提供）例：mynetwork.fyre.co
   * **** user_id:サイトのプロファイルシステム内のユーザーの一意のユーザーID。 英数字のみ(A ～ Z、a ～ z、0 ～ 9)。 システムのユーザーIDに無効な文字が含まれている場合は、ユーザーIDのmd5ハッシュまたはbase64でエンコードされたバージョンのLivefyreを送信することを検討してください。 （この操作を行う場合は、担当のアカウントマネージャーにお知らせください。）
   * **** expires:トークンが期限切れになる日付（エポック時間）。 Livefyreのログイン状態がサイトのログイン状態と同期するように、これはサイトのログインセッション時間と一致する必要があります。
   * **** display_name:コメントストリームに表示する必要がある、プロファイルシステム内のユーザーの表示名。

1. Livefyreから提供されたネットワークキーを使用して、辞書の署名済みJWTトークンを生成します。 JWTパッケージはデフォルトでHS256を使用しないので、正しいハッシュアルゴリズムを指定する必要があります。

   ```
          string token = JWT.JsonWebToken.Encode(payload, networkKey, JWT.JwtHashAlgorithm.HS256);
   ```
