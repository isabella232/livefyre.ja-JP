---
description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。
seo-description: 作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。
seo-title: CollectionMeta Token
solution: Experience Manager
title: CollectionMeta Token
uuid: d5db0b0f-2807-4392-874a-94ac3c1e7550
translation-type: tm+mt
source-git-commit: acba83da6abd919062025322beeced500a3db662
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---


# CollectionMeta Token{#collectionmeta-token}

作成するすべてのコレクションを識別する一意のトークンをサーバー上に作成します。

Livefyreは、作成するすべてのコレクションに一意の識別子を割り当てます。 Livefyreは、タイトル、URL、その他のパラメーターを割り当てます。次に例を示します。

## collectionMeta Tokenパラメーター

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| networkName | 文字列（オプション） | Livefyreネットワークの名前（{!UICONTROL Studio/設定/統合設定/資格情報]から入手できます）。 ライブラリを使用してcollectionMetaトークンを作成する場合は、このオプションです。 |
| networkKey | 文字列（オプション） | 特定のネットワークの秘密鍵（Studio/設定/統合設定/秘密鍵証明書から選択できます）。 ライブラリを使用してcollectionMetaトークンを作成する場合は、このオプションです。 |
| siteId | 文字列（オプション） | サイトのID(から入手でき [!UICONTROL Studio > Settings > Integration Settings > Credentials] ます)。 ライブラリを使用してcollectionMetaトークンを作成する場合はオプションです。 |
| siteKey | 文字列（オプション） | サイトの秘密キー（{!UICONTROL Studio/設定/統合設定/資格情報]から選択できます）。 |
| articleId | 文字列（オプション） | コレクションの一意のID。 |
| title | 文字列（オプション） | コレクションに適用するタイトル。 通常、これはアプリを表示するページのタイトルに対応します。 <br>次に例を示します。 「Integration is So Fun!」 <br>注意：  タイトルの最大文字長は255文字です。 タイトルフィールドはHTMLエンティティをサポートしていません。 特殊文字はUTF-8を使用してエンコードしてください。 |
| url | 文字列 (オプション) | このコレクションに添付する正規の絶対URLです。 このURLは、FacebookやTwitterで共有されるコンテンツ、電子メール通知およびLivefyre Studioからアプリへ戻るリンクを生成するために使用されます。 <br>注意：  ローカルでテストする場合は、有効なベースURLドメインを使用します(例： 有効： `https://customer.com`; 無効： `https://localhost:5995`)をクリックします。 |
| タグ | 文字列（オプション） | 1つのキーワードまたはフレーズをコンマで区切ったリスト。 Studioを使用してタグでコレクションを検索します。  </br>注意：  タグにスペースを含めることはできません。 UIにスペースを表示する場合は、アンダースコアを使用します。 |
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

>[!NOTE]
>
>Livefyreは、作成したcollectionMetaトークンを受け取り、siteId（Livefyreが提供）とarticleId（お客様が指定）を組み合わせて、一意性を決定します。
