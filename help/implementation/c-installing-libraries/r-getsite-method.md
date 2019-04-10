---
description: 新しいSiteオブジェクトを返します。
seo-description: 新しいSiteオブジェクトを返します。
seo-title: getSiteネットワーク方法
solution: Experience Manager
title: getSiteネットワーク方法
uuid: 67de781e-5240-4be5-9e93- c614828e0bb5
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# getSiteネットワーク方法{#getsite-network-method}

新しいSiteオブジェクトを返します。
| Variable| Type| Description|
|——|——|——|
| siteID| String| theコレクションが属するWebサイトまたはアプリケーションのLivefyre- provided ID。次に例を示します。303617.|
| siteKey| String| theSiteIDのLivefyreが提供する秘密鍵。|

## Javaの例 {#section_nyl_ycs_rz}

```
Site site = network.getSite(siteId, siteKey); 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
var site = network.getSite(siteId, siteKey); 
```

## PHPの例 {#section_ghf_gds_rz}

```
$site = $network->getSite(siteId, siteKey);
```

## Pythonの例 {#section_dwg_gds_rz}

```
site = network.get_site(siteId, siteKey) 
```

## ルビの例 {#section_enh_gds_rz}

```
site = network.get_site(siteId, siteKey) 
```

