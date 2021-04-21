---
description: 新しいSiteオブジェクトを返します。
title: getSiteネットワークメソッド
exl-id: 88782da9-88c6-4e60-9a23-e46d68675d59
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 0%

---

# getSiteネットワークメソッド{#getsite-network-method}

新しいSiteオブジェクトを返します。
|変数|型|説明|
|— |— |— |
|siteId|String|コレクションが属するWebサイトまたはアプリケーションのLivefyreが提供するID。 次に例を示します。303617.  |
|siteKey|String|Livefyreが提供するsiteIdの秘密キー。  |

## Javaの例{#section_nyl_ycs_rz}

```
Site site = network.getSite(siteId, siteKey); 
```

## NodeJSの例{#section_xkd_gds_rz}

```
var site = network.getSite(siteId, siteKey); 
```

## PHPの例{#section_ghf_gds_rz}

```
$site = $network->getSite(siteId, siteKey);
```

## Pythonの例{#section_dwg_gds_rz}

```
site = network.get_site(siteId, siteKey) 
```

## Rubyの例{#section_enh_gds_rz}

```
site = network.get_site(siteId, siteKey) 
```
