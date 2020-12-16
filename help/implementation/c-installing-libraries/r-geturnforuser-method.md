---
description: このメソッドは、このネットワークのユーザーのURNを返します。
seo-description: このメソッドは、このネットワークのユーザーのURNを返します。
seo-title: getUrnForUserネットワークメソッド
solution: Experience Manager
title: getUrnForUserネットワークメソッド
uuid: b70b8b0f-2b3a-4a1d-90d0-93a97a137ad4
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

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
