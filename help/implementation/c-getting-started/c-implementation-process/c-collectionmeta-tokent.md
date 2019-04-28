---
description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上で作成します。
seo-description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上で作成します。
seo-title: CollectionMetaトークン
solution: Experience Manager
title: CollectionMetaトークン
uuid: d5db0b0f-2807-4392-874a-94ac3c1e7550
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# CollectionMetaトークン{#collectionmeta-token}

作成するすべてのコレクションを識別する一意のトークンをサーバー上で作成します。

Livefyreは、作成するすべてのコレクションに一意の識別子を割り当てます。Livefyreは、次のようなタイトル、URLおよびその他のパラメーターを割り当てます。

## CollectionMetaトークンのパラメーター

| パラメータ | タイプ | 説明 |
|--- |--- |--- |
| NetworkName | 文字列（オプション） | Livefyreネットワークの名前（{!UACROL Studio/設定/統合設定/秘密鍵証明書]）。これは、ライブラリを使用してCollectionMetaトークンを作成する場合にオプションです。 |
| NetworkKey | 文字列（オプション） | 特定のネットワークの秘密鍵（Studio/設定/統合設定/秘密鍵証明書から利用可能）。これは、ライブラリを使用してCollectionMetaトークンを作成する場合にオプションです。 |
| siteID | 文字列（オプション） | サイトのID（使用可能なサイト [!UICONTROL Studio > Settings > Integration Settings > Credentials] ）。ライブラリを使用してCollectionMetaトークンを作成する場合はオプションです。 |
| siteKey | 文字列（オプション） | サイトの秘密鍵（{!UACROL Studio/設定/統合設定/秘密鍵証明書]）。 |
| articleId | 文字列（オプション） | コレクションの一意のID。 |
| title | 文字列（オプション） | コレクションに適用するタイトル。通常、これはアプリを表示するページのタイトルに対応します。<br>次に例を示します。「統合は非常に楽しい!&quot;<br>注意:タイトルの最大文字長は255文字です。タイトルフィールドはHTMLエンティティをサポートしていません。UTF-8を使用して特殊文字をエンコードしてください。 |
| url | 文字列（オプション） | このコレクションに付加する正規の絶対URLです。このURLは、FacebookおよびTwitter、電子メール通知およびLivefyre Studioで共有されたコンテンツからアプリに戻るリンクを生成するために使用されます。<br>注意:ローカルでテストする場合、有効なベースURLドメインを使用します（例:有効: `https://customer.com`;;無効: `https://localhost:5995`）を参照してください。 |
| タグ | 文字列（オプション） | 単一のキーワードまたはフレーズのコンマ区切りリスト。Studioを使用してコレクションをタグで検索します。</br>注意:タグにスペースを含めることはできません。UIにスペースを表示する場合は、アンダースコアを使用します。 |
| 拡張子 | JSON（オプション） | コレクションに渡されるJSON形式のパラメーターセットです。 |

## Java {#section_orz_m4n_sz}

```
import com.livefyre.Livefyre; 
import com.livefyre.core.Network; 
import com.livefyre.core.Site; 
import com.livefyre.core.Collection; 
  
Network network = Livefyre.getNetwork("networkName", "networkKey"); 
Site site = network.getSite("siteId", "siteKey"); 
Collection collection = site.buildCommentsCollection("title", "articleId", "https://www.example.com"); 
collection.getData().setTags("tags"); 
  
String collectionMetaToken = collection.buildCollectionMetaToken();
```

## NodeJS {#section_kpk_44n_sz}

```
var livefyre = require('livefyre'); 
  
var network = livefyre.getNetwork('networkName', 'networkKey'); 
var site = network.getSite('siteId', 'siteKey'); 
var collection = site.buildCommentsCollection('title', 'articleId', 'https://www.example.com'); 
collection.data.tags = 'tags'; 
  
var collectionMetaToken = collection.buildCollectionMetaToken(); 
```

## PHP {#section_zmd_zbj_tz}

```
$network = Livefyre::getNetwork("networkName", "networkKey"); 
$site = $network->getSite("siteId", "siteKey"); 
$collection = $site->buildCommentsCollection("title", "articleId", "https://www.example.com"); 
$collection->getData()->setTags("tags"); 
  
$collectionMetaToken = $collection->buildCollectionMetaToken();
```

## Python {#section_rdm_prj_tz}

```
from livefyre import Livefyre 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token()
```

## ルビ {#section_l5n_qrj_tz}

```
require 'livefyre' 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token 
```

>[!NOTE] {importance=&quot;high&quot;}
>
>Livefyreは、作成したCollectionMetaトークンを受け取り、SiteID（Livefyre提供）とArticleID（顧客指定）を組み合わせて一意性を決定します。

