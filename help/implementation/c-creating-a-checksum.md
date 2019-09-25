---
description: Livefyreライブラリを使用してチェックサムを作成します。
seo-description: Livefyreライブラリを使用してチェックサムを作成します。
seo-title: チェックサムの作成
solution: Livefyre
title: チェックサムの作成
uuid: 2ddedaa-7a6d-434a-8db8-dc179935f810
translation-type: tm+mt
source-git-commit: 6545445016517af1f1bbb071761d773ba5a9a597

---


# チェックサムの作成 {#creating-a-checksum}

Livefyreライブラリを使用してチェックサムを作成します。

## Java {#section_pfr_lqj_tz}

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

## NodeJS {#section_hnx_jqj_tz}

```
var livefyre = require('livefyre'); 
  
var network = livefyre.getNetwork('networkName', 'networkKey'); 
var site = network.getSite('siteId', 'siteKey'); 
var collection = site.buildCommentsCollection('title', 'articleId', 'https://www.example.com'); 
collection.data.tags = 'tags'; 
  
var collectionMetaToken = collection.buildCollectionMetaToken();
```

## PHP {#section_kmt_3qj_tz}

```
$network = Livefyre::getNetwork("networkName", "networkKey"); 
$site = $network->getSite("siteId", "siteKey"); 
$collection = $site->buildCommentsCollection("title", "articleId", "https://www.example.com"); 
$collection->getData()->setTags("tags"); 
  
$collectionMetaToken = $collection->buildCollectionMetaToken(); 
```

## Python {#section_y55_gqj_tz}

```
from livefyre import Livefyre 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token()
```

## Ruby {#section_a3y_ypj_tz}

```
require 'livefyre' 
  
network = Livefyre.get_network('networkName', 'networkKey') 
site = network.get_site('siteId', 'siteKey') 
collection = site.build_comments_collection('title', 'articleId', 'https://www.example.com') 
collection.data.tags = 'tags' 
  
collection_meta_token = collection.build_collection_meta_token 
```
