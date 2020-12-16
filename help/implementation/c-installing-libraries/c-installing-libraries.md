---
description: Livefyreサーバー側タスク用ライブラリのインストール
seo-description: Livefyreサーバー側タスク用ライブラリのインストール
seo-title: インストール
solution: Experience Manager
title: インストール
uuid: f60b4cc7-178f-4a16-ba75-f1d0d171c52f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# インストール{#installation}


## Java {#section_yd3_3zk_rz}

Javaライブラリをインストールするには、プロジェクトのPOMに次の依存関係を追加します。

```
<dependency> 
   <groupId>com.livefyre</groupId> 
   <artifactId>livefyre</artifactId> 
   <version>2.0.3</version> 
</dependency>
```

Javaライブラリは、次のモジュールに依存しています。

```
<dependency> 
   <groupId>com.sun.jersey</groupId> 
   <artifactId>jersey-client</artifactId> 
   <version>[1.18.1,)</version> 
</dependency> 
<dependency> 
   <groupId>com.google.code.gson</groupId> 
   <artifactId>gson</artifactId> 
   <version>[2.3,)</version> 
</dependency> 
<dependency> 
   <groupId>com.google.guava</groupId> 
   <artifactId>guava</artifactId> 
   <version>[18.0,)</version> 
</dependency> 
<dependency> 
   <groupId>org.apache.commons</groupId> 
   <artifactId>commons-lang3</artifactId> 
   <version>[3.0.1,)</version> 
</dependency> 
<dependency> 
   <groupId>org.bitbucket.b_c</groupId> 
   <artifactId>jose4j</artifactId> 
   <version>[0.4.1,)</version> 
</dependency> 
```

詳しくは、Javaドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-java-utils)のソースを参照してください。

## NodeJS {#section_swj_pwq_rz}

NodeJSライブラリをインストールするには、次の行を実行します。

`$ npm install livefyre`

NodeJSライブラリは、次のモジュールに依存しています。

```
"restler":">=3.2.0", 
"validator":"=3.5.0", 
"jsonwebtoken": ">=5.0.0" 
```

詳しくは、NodeJsドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-nodejs-utils)のソースを参照してください。

リンク：[Restler](https://github.com/danwrong/restler), [バリデーター](https://www.npmjs.org/package/validator), [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken)。

## PHP {#section_txj_xwq_rz}

ComposerでPHPライブラリをインストールするには、composer.jsonに次を追加します。

```
"require": { 
   "livefyre/livefyre-php-utils": "2.0.4" 
}
```

次に、次を使用してインストールします。

```
composer.phar install 
```

Composerを&#x200B;**使用しない**&#x200B;場合は、次を使用してライブラリの最新バージョンを取得します。

```
git clone https://github.com/Livefyre/livefyre-php-utils 
```

ライブラリを使用するには、PHPスクリプトに次を追加します。

```
require_once("/path/to/livefyre-php-utils/src/Livefyre.php"); 
```

PHPライブラリは、次のモジュールと依存関係があります。

```
"ext-json": "*", 
"rmccue/requests": ">=1.0" 
"firebase/php-jwt": ">=2.0" 
```

詳しくは、PHPドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-php-utils)のソースを参照してください。

リンク：[ext-json](https://php.net/manual/en/book.json.php), [リクエスト](https://github.com/rmccue/Requests/), [PHP-JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)

## Python {#section_irk_fxq_rz}

Pythonライブラリをインストールするには、次の行を実行します。

`$ pip install livefyre`

Pythonライブラリは、次のモジュールに依存しています。

```
PyJWT >= 1.0.1  
requests >= 2.2.1  
python-dateutil >= 2.2  
enum34 == 1.0  
ordereddict == 1.1 if sys.version_info[:2] < 2.7 
```

詳しくは、Pythonドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-python-utils)のソースを参照してください。

リンク：[PyJWT](https://github.com/progrium/pyjwt), [リクエスト](https://github.com/kennethreitz/requests), [Python-Dateutil](https://pypi.python.org/pypi/python-dateutil), [Enum34](https://pypi.python.org/pypi/enum34), [OrderedDict](https://pypi.python.org/pypi/ordereddict)

## Ruby {#section_fv2_tzq_rz}

Rubyライブラリをインストールするには、次の行をアプリケーションのGemfileに追加します。

```
gem 'livefyre' 
```

または、自分でインストールします。

`$ gem install livefyre`

Rubyライブラリは、次のモジュールに依存しています。

```
"jwt", '~> 1.4', ">= 1.4.1"  
"rest-client", '~> 1.8', ">= 1.8.0"  
"addressable", '~> 2.3', ">= 2.3.6" 
```

詳しくは、Rubyドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-ruby-utils)のソースを参照してください。

リンク：[Ruby JWT](https://github.com/firebase/php-jwt/tree/v2.0.0), [RESTクライアント](https://github.com/rest-client/rest-client/), [アドレス指定可能](https://github.com/sporkmonger/addressable)
