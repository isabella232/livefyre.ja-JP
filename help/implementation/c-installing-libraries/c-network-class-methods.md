---
description: Networkオブジェクトを作成します。
seo-description: Networkオブジェクトを作成します。
seo-title: ネットワーククラスメソッド
solution: Experience Manager
title: ネットワーククラスメソッド
uuid: 4130beda-dd09-49ae-aafb-f6b956e30b51
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 10%

---


# ネットワーククラスメソッド{#network-class-methods}

Networkオブジェクトを作成します。

ネットワークオブジェクトを作成すると、残りのページでは、セッション内にインスタンス化されたNetworkオブジェクトがあると想定されます。

## Networkオブジェクト

| パラメーター | タイプ | 説明 |
|---|---|---|
| *`network`* | 文字列 | Livefyreネットワーク。 次に例を示します。&quot;`labs.fyre.co`&quot;に置き換えます。 |
| *`networkKey`* | 文字列 | ネットワーク用にLivefyreが提供する秘密キー。 |

## Java {#section_myk_dzs_kbb}

```
import com.livefyre.Livefyre; 
  
Network network = Livefyre.getNetwork(network, networkKey); 
```

## NodeJS {#section_nyk_dzs_kbb}

```
var livefyre = require('livefyre'); 
  
var network = livefyre.getNetwork(network, networkKey); 
```

## PHP {#section_oyk_dzs_kbb}

```
use Livefyre\Livefyre; 
  
$network = Livefyre::getNetwork(network, networkKey); 
```

## Python {#section_pyk_dzs_kbb}

```
from livefyre import Livefyre 
  
network = Livefyre.get_network(network, networkKey) 
```

## Ruby {#section_qyk_dzs_kbb}

```
require 'livefyre' 
  
network = Livefyre.get_network(network, networkKey) 
```
