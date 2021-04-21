---
description: このメソッドは、このネットワークのユーザーのURNを返します。
title: getUrnForUserネットワークメソッド
exl-id: 272e724e-d09d-4d7d-9967-a229707ff47f
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '56'
ht-degree: 8%

---

# getUrnForUserネットワークメソッド{#geturnforuser-network-method}

このメソッドは、このネットワークのユーザーのURNを返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| userId | 文字列 | URNで使用するuserIdです。 |

## Javaの例{#section_nyl_ycs_rz}

```
network.getUrnForUser(userId);
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## NodeJSの例{#section_xkd_gds_rz}

```
network.getUrnForUser(userId);
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## PHPの例{#section_ghf_gds_rz}

```
$network->getUrnForUser(userId); 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## Pythonの例{#section_dwg_gds_rz}

```
network.get_urn_for_user(userId) 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```

## Rubyの例{#section_enh_gds_rz}

```
network.get_urn_for_user(userId) 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:user=tester" 
```
