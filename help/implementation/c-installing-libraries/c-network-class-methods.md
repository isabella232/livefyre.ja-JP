---
description: Networkオブジェクトを作成します。
title: ネットワーククラスメソッド
exl-id: 5a011120-05d0-4768-9038-6a312e8c5dd1
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 11%

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
