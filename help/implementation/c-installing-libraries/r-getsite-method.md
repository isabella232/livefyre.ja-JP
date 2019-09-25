---
description: 新しいSiteオブジェクトを返します。
seo-description: 新しいSiteオブジェクトを返します。
seo-title: getSiteネットワークメソッド
solution: Experience Manager
title: getSiteネットワークメソッド
uuid: 67de781e-5240-4be5-9e93-c614828e0bb5
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# getSiteネットワークメソッド{#getsite-network-method}

新しいSiteオブジェクトを返します。
|変数|型|説明||—|—|—||siteId|String|コレクションが属するWebサイトまたはアプリケーションのLivefyreが提供するID。 例：303617。  ||siteKey|String|Livefyreが提供するsiteIdの秘密キー。  |

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

## Rubyの例 {#section_enh_gds_rz}

```
site = network.get_site(siteId, siteKey) 
```

