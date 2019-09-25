---
description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。
seo-description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。
seo-title: CollectionMeta Token
solution: Experience Manager
title: CollectionMeta Token
uuid: d5db0b0f-2807-4392-874a-94ac3c1e7550
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# CollectionMeta Token{#collectionmeta-token}

作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。

Livefyreは、作成するすべてのコレクションに一意の識別子を割り当てます。 Livefyreは、タイトル、URLおよび次のような他のパラメーターを割り当てます。

## collectionMetaトークンのパラメーター

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| networkName | 文字列（オプション） | Livefyreネットワークの名前（{!UICONTROL Studio/設定/統合設定/資格情報]から入手できます）。 ライブラリを使用してcollectionMetaトークンを作成する場合は、このオプションです。 |
| networkKey | 文字列（オプション） | 特定のネットワークの秘密キー（Studio/設定/統合設定/秘密鍵証明書から使用可能）。 ライブラリを使用してcollectionMetaトークンを作成する場合は、このオプションです。 |
| siteId | 文字列（オプション） | サイトのID(から利用でき [!UICONTROL Studio > Settings > Integration Settings > Credentials] ます)。 ライブラリを使用してcollectionMetaトークンを作成する場合はオプションです。 |
| siteKey | 文字列（オプション） | サイトの秘密キー（{!UICONTROL Studio/設定/統合設定/資格情報]から利用できます）。 |
| articleId | 文字列（オプション） | コレクションの一意のID。 |
| title | 文字列（オプション） | コレクションに適用するタイトル。 通常、これはアプリを表示するページのタイトルに対応します。 <br>例：「統合はとても楽しい！」<br>注意： タイトルの最大文字長は255文字です。 タイトルフィールドはHTMLエンティティをサポートしていません。 UTF-8を使用して特殊文字をエンコードしてください。 |
| url | 文字列 (オプション) | このコレクションに添付する正規の絶対URLです。 このURLは、FacebookやTwitterで共有されたコンテンツ、電子メール通知およびLivefyre studioからアプリへのリンクを生成するために使用されます。 <br>注意： ローカルでテストする場合は、有効なベースURLドメインを使用します(例：有効： `https://customer.com`;無効： `https://localhost:5995`)。 |
| タグ | 文字列（オプション） | 単一のキーワードまたはフレーズのコンマ区切りリスト。 Studioを使用してタグでコレクションを検索します。  </br>注意：タグにスペースを含めることはできません。 UIにスペースを表示する場合は、アンダースコアを使用します。 |
| extensions | JSON（オプション） | コレクションに渡すJSON形式のパラメーターのセットです。 |

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

## Ruby {#section_l5n_qrj_tz}

```
require 'livefyre' 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token 
```

>[!NOTE] {importance="high"}
>
>Livefyreは、構築したcollectionMetaトークンを受け取り、siteId（Livefyreが提供）とarticleId（顧客が指定）を組み合わせて一意性を判定します。

