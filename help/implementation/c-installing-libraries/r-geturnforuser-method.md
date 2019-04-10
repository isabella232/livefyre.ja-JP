---
description: このメソッドは、このネットワークのユーザーに対してURNを返します。
seo-description: このメソッドは、このネットワークのユーザーに対してURNを返します。
seo-title: getUrnForUserネットワークメソッド
solution: Experience Manager
title: getUrnForUserネットワークメソッド
uuid: b70b8b0f-2b3a-4a1d-90d0-93a97a137ad4
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# getUrnForUserネットワークメソッド{#geturnforuser-network-method}

このメソッドは、このネットワークのユーザーに対してURNを返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| userId | 文字列 | INTERTEで使用するuserIdです。 |

## Javaの例 {#section_nyl_ycs_rz}

```
network.getUrnForUser(userId);
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
network.getUrnForUser(userId);
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## PHPの例 {#section_ghf_gds_rz}

```
$network->getUrnForUser(userId); 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## Pythonの例 {#section_dwg_gds_rz}

```
network.get_urn_for_user(userId) 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## ルビの例 {#section_enh_gds_rz}

```
network.get_urn_for_user(userId) 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```
