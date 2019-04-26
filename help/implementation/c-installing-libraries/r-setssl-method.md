---
description: API呼び出しのオン/オフのためのSSLを設定します。
seo-description: API呼び出しのオン/オフのためのSSLを設定します。
seo-title: setSSLネットワークメソッド
solution: Experience Manager
title: setSSLネットワークメソッド
uuid: 8d989e63- c859-456a-99ca-8d87933913ba
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# setSSLネットワークメソッド{#setssl-network-method}

API呼び出しのオン/オフのためのSSLを設定します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| ssl | ブール値 | 初期設定はtrueです。SSLを使用する場合は、falseを指定します。 <br><ul><li>True- SSL </li><li>false- SSLオフ</li></ul> |

## Javaの例 {#section_nyl_ycs_rz}

```
network.setSsl(ssl); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
network.ssl = false; 
```

## PHPの例 {#section_ghf_gds_rz}

```
$network->setSsl(false); 
```

## Pythonの例 {#section_dwg_gds_rz}

```
network.ssl = False 
```

## ルビの例 {#section_enh_gds_rz}

```
network.ssl = false 
```
