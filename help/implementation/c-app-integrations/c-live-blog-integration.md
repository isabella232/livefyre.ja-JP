---
description: ライブブログでは、ライブイベントをカバーする際に、サイトの編集者からリアルタイムの更新や画像を特集できます。
seo-description: ライブブログでは、ライブイベントをカバーする際に、サイトの編集者からリアルタイムの更新や画像を特集できます。
seo-title: ライブブログ
solution: Experience Manager
title: ライブブログ
uuid: 5ca373f1-2008-45ab-9ec2-1e295af4e368
translation-type: tm+mt
source-git-commit: 987e682f9c7cd94543fd269f386fd2a971ee9934

---


# ライブブログ{#live-blog}

ライブブログでは、ライブイベントをカバーする際に、サイトの編集者からリアルタイムの更新や画像を特集できます。

## ライブブログ {#topic_574DEE2125A94B85BFB5C3D2C57C337E}

ライブブログでは、ライブイベントをカバーする際に、サイトの編集者からリアルタイムの更新や画像を特集できます。

## 統合 {#c_live_blog_integration}

ライブブログでは、ライブイベントをカバーする際に、サイトの編集者からリアルタイムの更新や画像を特集できます。

ライブブログアプリを埋め込むには、「アプリを埋め込む」の手順に従います。 詳しくは、ア [プリの埋め込みを参照してください](/help/implementation/c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md)。 次に、埋め込まれたLive Blog appの例を示します。

### 例

```
<html> 
  <head> 
    <script src="//cdn.livefyre.com/Livefyre.js"> 
    </script> 
  </head> 
<body> 
    <script type="text/javascript"> 
    var networkConfig = { 
      network: "client-solutions.fyre.co" 
    }; 
    var convConfig = { 
      siteId: '347674', 
      articleId: '1', 
      el: 'livefyre', 
      collectionMeta: 'eyJ0eXAiOiJqd3QiLCJhbGciOiJIUzI1NiJ9.eyJ0aXRsZSI6IlRpdGxlIDEiLCJ1cmwiOiJodHRwOlwvXC9kZXYubGl2ZWZ5cmUuY29tIiwidGFncyI6InRhZzEsdGFnMiIsImNoZWNrc3VtIjoiY2Q0YTJjYWJkMTIxOTkyM2FjZGJhMjExOWY2NmYwNTUiLCJhcnRpY2xlSWQiOiIxIn0.Dq-ghi9KYmEPmagvCS1NPyYDRMGBujm735QaTRb7E7k', 
      checksum: '6e2e4faf7b95f896260fe695eafb34ba' 
    }; 
    
    Livefyre.require(['fyre.conv#3'], function(Conv) { 
        new Conv(networkConfig, [convConfig], function(blogWidget) {}); 
        auth.delegate({ 
          login: function (callback) { 
            callback(null,{livefyre:'<userauthtoken>'}); 
          }, 
        }); 
    }); 
  
    </script> 
    <div id="livefyre"> 
    </div> 
   </body> 
</html>
```

CollectionMetaはエンコードされたJSONオブジェクトです。 上の例では、JSONオブジェクトはJWTエンコードされる前に次の形式をとります。

```
{ 
"url": "https://dev.livefyre.com/articles/test.html",  
"articleId": "1",  
"type": "liveblog",  
"title": "Title 1" 
}
```

## NetworkConfigオブジェクト {#c-networkconfig-object}

このオ `NetworkConfig` ブジェクトは、ネットワークユーザーの認証システムをカスタマイズするJSONオブジェクトです。

オブジェクト `NetworkConfig` は、次のパラメーターを含むJSONオブジェクトです。

| パラメーター | タイプ | 説明 |
|---|---|---|
| **authDelegate** | *required* object | カスタムネットワークユーザーの認証システムをカスタマイズするために使用します。 |
| **network** | *必須の* string Livefyreが提供するネットワーク名。 例： *yourname.fyre.co* |
| **attachmentDelegate** | *オプション* ・オブジェクト | アプリストリームに表示されるメディア添付ファイルのタイプを指定するために使用します。 詳しくは、「メディアの制限」を [参照してください](../c-app-customizations/c-restrict-media.md#c_restrict_media)。 |
| **文字列** | *オプション* ・オブジェクト | 任意のLivefyreコアアプリでHTML要素のテキスト文字列をカスタマイズするために使用します。 詳しくは、「文字列のカスタマイズ」を [参照してください](/help/using/c-settings-other/c-translation-sets/c-localize-strings.md)。 |

## ConvConfigオブジェクト {#c-convconfig-object}

このオ `convConfig` ブジェクトは、Livefyre appがページ上でレンダリングするコンテンツを指定するために使用されるJSONオブジェクトです。

>[!NOTE]
>
>ここに示 `convConfig` すオブジェクトパラメーターは、レビューアプリには適用されません。 オブジェクトを使用したReviewsアプリケーションの統合について詳しくは、 `convConfig` 「レビューの統合」を参照してください。

このオブジ `ConvConfig` ェクトには、次の必須パラメーターが含まれます。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| **articleId** | *必須文字* 列 | サイト内のコレクションを一意に識別します。 通常、これはCMS内のデータベースの主キーまたは投稿IDに対応します。 例："42より後" 上限 255 文字.  注意： 記事のURLをarticleIdとして使用する場合は、文字列がMD5またはSHA-1でエンコードされていることを確認します。 |
| **collectionMeta** | *必須文字* 列 | コレクションに関するJWTエンコードされたメタデータ。 詳しくは、CollectionMeta Objectを参照してください。 |
| **el** | *必須文字* 列 | コンテンツストリームがレンダリングされるDOM要素のID。 |
| **siteId** | *必須文字* 列 | コレクションが属するWebサイトまたはアプリケーションのLivefyreが提供するID。 例："303617" |

>[!NOTE]
>
>このパ `app` ラメーターは、Comments appの実装には必要ありません。

また、このオ `ConvConfig` ブジェクトには、次のオプションのパラメーターを含めることもできます。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| **actionButtons** | *任意配列* | 共有ボタンとフラグボタンの横にコンテンツに追加するカスタムアクションボタンの配列です。 詳しくは、「カスタムボタンの追加」を参照してください。 |
| **アニメーション** | *オプション* boolean | Livefyreアプリ内でアニメーションを実行するかどうかを定義します。 アニメーションを無効にするには、falseに設定します。 デフォルトはtrueです。 |
| **anonymousFlaggingEnabled** | ブール型 | ゲストユーザーがコンテンツにフラグを付けるオプションを持つかどうかを定義します。 初期設定は true です。 |
| browserType | *オプション* String | 表示コンテンツを生成するデバイスを定義します。 これにより、CSSおよび一部の機能が、入力デバイスタイプに合わせて変更されます。 オプションは、デスクトップ、モバイル、タブレットです。 （空白の場合、表示形式に対するGoogleエージェントの決定がデフォルトになります）。 |
| **checksum** | *オプション* 文字列（推奨） | CollectionMetaの現在の状態を識別します。 この値を変更すると、Livefyreがサーバー上のデータをCollectionMetaの新しい値で更新します。 |
| **datetimeFormat** | *オプションの* stringオブジェクト関数 | ストリームコンテンツの日時形式を指定します。 詳しくは、日付とタイムスタンプのカスタマイズを参照してください。 |
| disableAvatars | *オプション* boolean | アバターがアプリストリームにレンダリングされるのを防ぎ、ブラウザーに読み込まれるアイテムの数を減らします。 デフォルトは false です。 |
| disableIE8Shim | *オプション* boolean | HTML5要素がサポートされるように、LivefyreがInternet Explorer 8をポリフィルするために使用するデフォルトのshivを無効にします。 Livefyreは次のプロジェクトを使用します。 https://github.com/aFarkas/html5shiv [](https://github.com/aFarkas/html5shiv) . デフォルトは false です。注意： この値がfalseの場合、Internet Explorer 8のサポート用にLivefyre Chatを呼び出す前に、何らかのポリフィルを使用する必要があります。 |
| **disableThirdPartyAnalytics** | *オプション* boolean | Livefyreが内部測定に使用する可能性があるサードパーティの解析システム（QuantserveおよびGoogle Analytics）を無効にします。 デフォルトは false です。 |
| **editorCss** | *オプション* ・オブジェクト | コメントエディターのスタイル設定をカスタマイズするために使用します。 エディターフィールドの背景色と、エディター内に表示されるテキストのフォントの色、サイズ、ファミリーのスタイルを設定できます。  例：{background:‘#ccc’, color:‘red’, font:’30px "Helvetica Neue”, Helvetica, Arial, Geneva, sans-serif’} |
| **initialNumVisible** | *オプション* 整数 | 読み込み時にアプリに表示されるコメントのデフォルト数を設定できます。 1 ～ 50の整数を指定できます。 |
| **initialNumVisibleLegacy** | *オプション* 整数 | 読み込み時にアプリに表示されるレガシーコンテンツ項目のデフォルト数を設定できます。 1 ～ 50の整数を指定できます。 このパラメーターを指定しない場合、デフォルトはinitialNumVisibleです。  例：コレクションに100件のアクティブなコメントと100件のレガシーコメントが含まれる場合は、initalNumVisible:10とinitialNumVisibleLegacy:5を設定して、10件のアクティブなコメント（「詳細を表示」ボタン付き） + 5件のアーカイブコメント（「詳細を表示」ボタン付き）を表示します。 |
| **maxVisible** | *オプション* 整数 | チャットアプリで表示される最上位レベルのコンテンツの最大部分数を設定します。 で新しいコンテンツストリーム部分が生成された場合、ストリームの一番下にあるコンテンツはページから削除されます。 「表示を増やす」ボタンをクリックすると、このパラメーターは無視され、ユーザーは必要なだけコンテンツを自由に表示できます。 （このパラメーターを使用して、高速ストリームでページに表示するアイテム数を制御します）。 |
| **postToButtons** | *任意配列* | Live Blog appを埋め込む際に表示するプロバイダーを設定するために使用します。 使用できるオプションは、2つ(Twitter)、fb(Facebook)およびli(LinkedIn)です。 初期設定は [ tw , fbです ]。 |
| **readOnly** | *オプション* boolean | コレクションのすべてのインタラクティブ機能を無効にします。 trueの場合、ユーザーはストリームにログインできず、投稿、編集、返信または「いいね！」のコンテンツを実行できません。 trueの場合、ユーザーはコンテンツにフラグを付けたり共有したりできます。 デフォルトは false です。 |
| **流れ** | *オプション* ・オブジェクト | アプリのストリーミングを設定するオプションが含まれます。 |
| stream.catchup | *オプション* 整数 | ストリームを読み込むべき現在の時点までの秒数を指定します。 デフォルトでは、Livefyreは50個のコンテンツを読み込み、その後、これらのコンテンツと現在の時間の間に送信されたすべてのコンテンツを読み込みます。 非常に高速な使用例では、コンテンツの投稿が非常に早すぎて、アプリが現在に「追い付く」ことができます。 この設定を使用して、（最初のコンテンツの読み込み後に）コンテンツが投稿されるまでの秒数を定義します。 |
| **stream.delay** | *オプション* 整数 | ストリーミング要求の間隔を秒数で指定します。 このパラメーターを使用すると、コンテンツのフローを制御し、DOMが更新される頻度を遅らせることができます。  注意： 大きすぎると、ストリームが遅れる可能性があります。 |


>[!NOTE]
>
>アプリの初期化中に1つ以上のオブ `convConfig` ジェクトを渡して、同じページに複数のアプリを表示できます。 数が増えると、追加のアプリでブラウザーのリソースが使用され、パフォーマンスが低下する場合があることに注意してください。

## CollectionMetaオブジェクト {#c-collectionmeta-object}

オブジ `CollectionMeta` ェクトは、コレクション内に保存するメタデータを指定するJSONオブジェクトです。

`CollectionMeta` は、セキュリティのためにLivefyreに渡される前に常にエンコードされます。 エンコードされた値は、上に示したオブジ `ConvConfig` ェクトに渡されます。

>[!NOTE]
>
>JSONオブジェクトをエンコードするには、サーバー側コードを追加する `CollectionMeta` 必要があります。 詳しくは、「サーバー側トークンの構築」を参照してください。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| **articleId** | *必須文字* 列 | コレクションの一意のID。 |
| **title** | *必須文字* 列 | コレクションに適用するタイトル。 これは、多くの場合、アプリを表示するページのタイトルに対応します。  例：「統合はとても楽しい！」注意： タイトルの最大文字長は255文字です。 タイトルフィールドはHTMLエンティティをサポートしていません。 UTF-8を使用して特殊文字をエンコードしてください。 |
| **url** | *必須文字* 列 | このコレクションに添付する正規の絶対URLです。 このURLは、FacebookやTwitterで共有されたコンテンツ、電子メール通知およびLivefyre studioからアプリへのリンクを生成するために使用されます。  注意： Livefyreでは、完全修飾ドメイン名の使用が必要です。ローカル設定を解決するためのポート番号またはコールバックは必要ありません。 ローカルでテストする場合は、有効なベースURLドメインを必ず使用してください。 (例：は有 `https://customer.com` 効ですが、 `https://localhost:5995` は無効です)。完全修飾ドメイン名を受け入れるようにローカルWebサーバーを設定した後は、コールバックや解決は不要で、ローカル開発を期待どおりに進めることができます。 |
| **type** | *required* String | コレクションの種類です。 livechatである必要があります。 |

また、このオ `CollectionMeta` ブジェクトには、次のオプションのパラメーターを含めることもできます。

| パラメーター | タイプ | 説明 |
|---|---|---|
| **タグ** | *オプション* 文字列 | 単一のキーワードまたはフレーズのコンマ区切りリスト。 Studio内のタグまたは検索APIを使用してコレクションを検索します。 **** 注意：Studioで追加されたタグにスペースを含めることができますが、APIで入力されたタグは使用できません。 UIにスペースを表示するタグを定義するには、アンダースコアを使用します。 (例：Monday_Quarterbackを使用して、StudioでMonday Quarterbackを表示します。) |

## イベントハンドラーの追加 {#concept_D835C710A7214F6D921571E0770B6BC5}

イベントハンドラーを登録するには、アプリのコールバック関数内でwidget.on呼び出しを使用します。

次に例を示します。

```
Livefyre.require(['fyre.conv#3'], function(Conv) { 
   new Conv(networkConfig, [convConfig], function(widget) { 
      widget.on('<strong><eventName></strong>', function (data) { 
         // Do something, perhaps using data 
      }); 
   }); 
});
```

