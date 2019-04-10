---
description: このメソッドは、このコレクションのURNを返します。このメソッドを実行する前に、createOrUpdate（）を実行する必要があります。
seo-description: このメソッドは、このコレクションのURNを返します。このメソッドを実行する前に、createOrUpdate（）を実行する必要があります。
seo-title: getStateコレクションメソッド
solution: Experience Manager
title: getStateコレクションメソッド
uuid: 2f4d7796-2ae5-4b74- a958-40825c6bff16
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# getStateコレクションメソッド{#geturn-collection-method}

このメソッドは、このコレクションのURNを返します。このメソッドを実行する前に、createOrUpdate（）を実行する必要があります。

## Javaの例 {#section_nyl_ycs_rz}

```
collection.getUrn(); 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
collection.getUrn(); 
```

サンプル出力:

```
<span class="str">"urn:livefyre:network=`example.fyre.co`:site=1:collection=1"</span>
```

## PHPの例 {#section_ghf_gds_rz}

```
$collection->getUrn(); 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## Pythonの例 {#section_dwg_gds_rz}

```
collection.urn() 
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## ルビの例 {#section_enh_gds_rz}

```
collection.urn
```

サンプル出力:

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

