---
description: Livefyre サーバー側タスク用のライブラリのインストール
title: インストール
exl-id: d74f85be-14c0-4f6d-8f16-b688282c0eb0
source-git-commit: 3091db9d7b9611e26ad65c1432856c9465694e92
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# インストール{#installation}


## Java {#section_yd3_3zk_rz}

Java ライブラリをインストールするには、次の依存関係をプロジェクトの POM に追加します。

```
<dependency> 
   <groupId>com.livefyre</groupId> 
   <artifactId>livefyre</artifactId> 
   <version>2.0.3</version> 
</dependency>
```

Java ライブラリは、次のモジュールに依存します。

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

詳しくは、Java のドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-java-utils) のソースを参照してください。

## NodeJS {#section_swj_pwq_rz}

NodeJS ライブラリをインストールするには、次の行を実行します。

`$ npm install livefyre`

NodeJS ライブラリは、次のモジュールに依存しています。

```
"restler":">=3.2.0", 
"validator":"=3.5.0", 
"jsonwebtoken": ">=5.0.0" 
```

詳しくは、 NodeJs のドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-nodejs-utils) のソースを参照してください。

リンク：[Restler](https://github.com/danwrong/restler)、[ バリデーター ](https://www.npmjs.org/package/validator)、[jsonwebtoken](https://github.com/auth0/node-jsonwebtoken)。

## PHP {#section_txj_xwq_rz}

Composer で PHP ライブラリをインストールするには、次のコードを composer.json に追加します。

```
"require": { 
   "livefyre/livefyre-php-utils": "2.0.4" 
}
```

次に、以下を使用してをインストールします。

```
composer.phar install 
```

Composer を使用 **しない** 場合は、次を使用して最新バージョンのライブラリを取得します。

```
git clone https://github.com/Livefyre/livefyre-php-utils 
```

ライブラリを使用するには、次の内容を PHP スクリプトに追加します。

```
require_once("/path/to/livefyre-php-utils/src/Livefyre.php"); 
```

PHP ライブラリは、次のモジュールに依存します。

```
"ext-json": "*", 
"rmccue/requests": ">=1.0" 
"firebase/php-jwt": ">=2.0" 
```

詳しくは、PHP のドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-php-utils) のソースを参照してください。

リンク：[ext-json](https://www.php.net/manual/en/book.json.php)、[ リクエスト ](https://github.com/rmccue/Requests/)、[PHP-JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)

## Python {#section_irk_fxq_rz}

Python ライブラリをインストールするには、次の行を実行します。

`$ pip install livefyre`

Python ライブラリは、次のモジュールに依存します。

```
PyJWT >= 1.0.1  
requests >= 2.2.1  
python-dateutil >= 2.2  
enum34 == 1.0  
ordereddict == 1.1 if sys.version_info[:2] < 2.7 
```

詳しくは、Python ドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-python-utils) のソースを参照してください。

リンク：[PyJWT](https://github.com/progrium/pyjwt)、[ リクエスト ](https://github.com/kennethreitz/requests)、[Python-Dateutil](https://pypi.python.org/pypi/python-dateutil)、[Enum34](https://pypi.python.org/pypi/enum34)、[OrderedDict](https://pypi.python.org/pypi/ordereddict)

## Ruby {#section_fv2_tzq_rz}

Ruby ライブラリをインストールするには、次の行をアプリケーションの Gemfile に追加します。

```
gem 'livefyre' 
```

または、自分でインストールします。

`$ gem install livefyre`

Ruby ライブラリは、次のモジュールに依存します。

```
"jwt", '~> 1.4', ">= 1.4.1"  
"rest-client", '~> 1.8', ">= 1.8.0"  
"addressable", '~> 2.3', ">= 2.3.6" 
```

詳しくは、Ruby のドキュメントを読むか、[GitHub](https://github.com/Livefyre/livefyre-ruby-utils) のソースを参照してください。

リンク：[Ruby JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)、[REST クライアント ](https://github.com/rest-client/rest-client/)、[ アドレス可能 ](https://github.com/sporkmonger/addressable)
