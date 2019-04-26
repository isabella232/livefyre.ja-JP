---
description: 提供されたネットワークのユーザー同期URLをLivefyreに更新します。ブール値を返します。
seo-description: 提供されたネットワークのユーザー同期URLをLivefyreに更新します。ブール値を返します。
seo-title: setUserSynccURLネットワークメソッド
solution: Experience Manager
title: setUserSynccURLネットワークメソッド
uuid: cd067e90- a2da-4e3d-8e60-7eabfd86fc7f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# setUserSynccURLネットワークメソッド{#setusersyncurl-network-method}

提供されたネットワークのユーザー同期URLをLivefyreに更新します。ブール値を返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| urlTemplate | 文字列 | ユーザーIDを同期するためのLivefyreに登録するURLです。「`{id}`」が指定されたURL文字列に含まれている必要があります。 |

## Javaの例 {#section_nyl_ycs_rz}

```
network.setUserSyncUrl(urlTemplate); 
```

サンプル出力:

```
true
```

## NodeJSの例 {#section_xkd_gds_rz}

```
network.setUserSyncUrl(urlTemplate); 
```

サンプル出力:

```
true
```

## PHPの例 {#section_ghf_gds_rz}

```
$network->setUserSyncUrl(urlTemplate); 
```

サンプル出力:

```
true
```

## Pythonの例 {#section_dwg_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

サンプル出力:

```
True
```

## ルビの例 {#section_enh_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

サンプル出力:

```
True
```
