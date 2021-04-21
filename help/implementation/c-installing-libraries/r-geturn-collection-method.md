---
description: このメソッドは、このコレクションのURNを返します。 このメソッドを実行する前に、createOrUpdate()を実行する必要があります。
title: getUrnコレクションメソッド
exl-id: bea04805-8f02-4c06-9a1a-6b057de831ab
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 0%

---

# getUrn収集メソッド{#geturn-collection-method}

このメソッドは、このコレクションのURNを返します。 このメソッドを実行する前に、createOrUpdate()を実行する必要があります。

## Javaの例{#section_nyl_ycs_rz}

```
collection.getUrn(); 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## NodeJSの例{#section_xkd_gds_rz}

```
collection.getUrn(); 
```

出力例：

```
<span class="str">"urn:livefyre:network=`example.fyre.co`:site=1:collection=1"</span>
```

## PHPの例{#section_ghf_gds_rz}

```
$collection->getUrn(); 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## Pythonの例{#section_dwg_gds_rz}

```
collection.urn() 
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```

## Rubyの例{#section_enh_gds_rz}

```
collection.urn
```

出力例：

```
"urn:livefyre:network=`example.fyre.co`:site=1:collection=1" 
```
