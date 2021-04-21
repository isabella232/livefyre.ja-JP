---
description: API呼び出しのSSLをonまたはoffに設定します。
title: setSSLネットワークメソッド
exl-id: 5682b84a-0b4d-479b-af40-60d2c6c38155
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 14%

---

# setSSLネットワークメソッド{#setssl-network-method}

API呼び出しのSSLをonまたはoffに設定します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| ssl | ブール値 | 初期設定は true です。sslを有効にする場合はfalse、それ以外の場合はfalse。<br><ul><li>True - SSLオン </li><li>False - SSLオフ</li></ul> |

## Javaの例{#section_nyl_ycs_rz}

```
network.setSsl(ssl); 
```

## NodeJSの例{#section_xkd_gds_rz}

```
network.ssl = false; 
```

## PHPの例{#section_ghf_gds_rz}

```
$network->setSsl(false); 
```

## Pythonの例{#section_dwg_gds_rz}

```
network.ssl = False 
```

## Rubyの例{#section_enh_gds_rz}

```
network.ssl = false 
```
