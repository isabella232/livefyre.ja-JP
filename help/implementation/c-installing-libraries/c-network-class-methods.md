---
description: Networkオブジェクトを作成します。
seo-description: Networkオブジェクトを作成します。
seo-title: ネットワーククラスメソッド
solution: Experience Manager
title: ネットワーククラスメソッド
uuid: 4130beda- dd09-49ae- aafb- f6b956e30b51
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# ネットワーククラスメソッド{#network-class-methods}

Networkオブジェクトを作成します。

ネットワークオブジェクトを作成すると、残りのページは、セッションにネットワークオブジェクトがインスタンス化されていると想定します。

## ネットワークオブジェクト

| パラメータ | タイプ | 説明 |
|---|---|---|
| *`network`* | 文字列 | Livefyreネットワーク。次に例を示します。「`labs.fyre.co`」. |
| *`networkKey`* | 文字列 | ネットワークのLivefyreが提供する秘密鍵。 |

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

## ルビ {#section_qyk_dzs_kbb}

```
require 'livefyre' 
  
network = Livefyre.get_network(network, networkKey) 
```
