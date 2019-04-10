---
description: Livefyreサーバー側タスクのライブラリのインストール
seo-description: Livefyreサーバー側タスクのライブラリのインストール
seo-title: インストール
solution: Experience Manager
title: インストール
uuid: f60b4cc7-178f-4a16- ba75- f1d0d171c52f
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# インストール{#installation}


## Java {#section_yd3_3zk_rz}

Javaライブラリをインストールするには、プロジェクトのPOMに次の依存性を追加します。

```
<dependency> 
   <groupId>com.livefyre</groupId> 
   <artifactId>livefyre</artifactId> 
   <version>2.0.3</version> 
</dependency>
```

Javaライブラリには、次のモジュールに依存性があります。

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

詳しくは、Javaドキュメントを読むか、GitHub上の [ソースを参照](https://github.com/Livefyre/livefyre-java-utils)してください。

## NodeJS {#section_swj_pwq_rz}

NodeJSライブラリをインストールするには、次の行を実行します。

`$ npm install livefyre`

NodeJSライブラリには、次のモジュールに依存性があります。

```
"restler":">=3.2.0", 
"validator":"=3.5.0", 
"jsonwebtoken": ">=5.0.0" 
```

詳しくは、NodeJSドキュメントを読むか、GitHubの [ソースを参照](https://github.com/Livefyre/livefyre-nodejs-utils)してください。

リンク: [Restler](https://github.com/danwrong/restler)， [Validator](https://www.npmjs.org/package/validator)， [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken).

## PHP {#section_txj_xwq_rz}

Composerを使用してPHPライブラリをインストールするには、composer. jsonに追加します。

```
"require": { 
   "livefyre/livefyre-php-utils": "2.0.4" 
}
```

次に、次を使用してインストールします。

```
composer.phar install 
```

Composerを使用 **しない** 場合は、以下を使用して最新バージョンのライブラリを入手してください。

```
git clone https://github.com/Livefyre/livefyre-php-utils 
```

ライブラリを使用するには、PHPスクリプトに以下を追加します。

```
require_once("/path/to/livefyre-php-utils/src/Livefyre.php"); 
```

PHPライブラリには、次のモジュールに依存性があります。

```
"ext-json": "*", 
"rmccue/requests": ">=1.0" 
"firebase/php-jwt": ">=2.0" 
```

詳しくは、PHPドキュメントを読むか、GitHub上の [ソースを参照](https://github.com/Livefyre/livefyre-php-utils)してください。

リンク: [ext- json](https://php.net/manual/en/book.json.php)， [リクエスト](https://github.com/rmccue/Requests/)， [PHP- JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)

## Python {#section_irk_fxq_rz}

Pythonライブラリをインストールするには、次の行を実行します。

`$ pip install livefyre`

Pythonライブラリには、次のモジュールに依存性があります。

```
PyJWT >= 1.0.1  
requests >= 2.2.1  
python-dateutil >= 2.2  
enum34 == 1.0  
ordereddict == 1.1 if sys.version_info[:2] < 2.7 
```

詳しくは、Pythonドキュメントを読むか、GitHub上の [ソースを参照](https://github.com/Livefyre/livefyre-python-utils)してください。

リンク: [PyJWT](https://github.com/progrium/pyjwt)、 [Requests](https://github.com/kennethreitz/requests)、 [Python- Dateutil](https://pypi.python.org/pypi/python-dateutil)、 [Enum34](https://pypi.python.org/pypi/enum34)、 [OrderedDict](https://pypi.python.org/pypi/ordereddict)

## ルビ {#section_fv2_tzq_rz}

Rubyライブラリをインストールするには、アプリケーションのGemfileに次の行を追加します。

```
gem 'livefyre' 
```

または、自分でインストールします。

`$ gem install livefyre`

Rubyライブラリには、次のモジュールに依存性があります。

```
"jwt", '~> 1.4', ">= 1.4.1"  
"rest-client", '~> 1.8', ">= 1.8.0"  
"addressable", '~> 2.3', ">= 2.3.6" 
```

詳しくは、Ruby docsを読むか、GitHubの [ソースを参照](https://github.com/Livefyre/livefyre-ruby-utils)してください。

リンク: [Ruby JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)、 [RESTクライアント](https://github.com/rest-client/rest-client/)、 [アドレス可能](https://github.com/sporkmonger/addressable)
