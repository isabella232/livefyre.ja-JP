---
description: ネットワークのユーザー同期URLを指定されたURLに更新するようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
seo-description: ネットワークのユーザー同期URLを指定されたURLに更新するようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
seo-title: setUserSyncUrlネットワークメソッド
solution: Experience Manager
title: setUserSyncUrlネットワークメソッド
uuid: cd067e90-a2da-4e3d-8e60-7eabfd86fc7f
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

---


# setUserSyncUrlネットワークメソッド{#setusersyncurl-network-method}

ネットワークのユーザー同期URLを指定されたURLに更新するようにLivefyreに通知します。 ブール型( Boolean )の値を返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| urlTemplate | 文字列 | ユーザーIDを同期するためにLivefyreに登録するURL。 指定したURL文字列の一部として「`{id}`」を指定する必要があります。 |

## Javaの例{#section_nyl_ycs_rz}

```
network.setUserSyncUrl(urlTemplate); 
```

出力例：

```
true
```

## NodeJSの例{#section_xkd_gds_rz}

```
network.setUserSyncUrl(urlTemplate); 
```

出力例：

```
true
```

## PHPの例{#section_ghf_gds_rz}

```
$network->setUserSyncUrl(urlTemplate); 
```

出力例：

```
true
```

## Pythonの例{#section_dwg_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

出力例：

```
True
```

## Rubyの例{#section_enh_gds_rz}

```
network.set_user_sync_url(urlTemplate) 
```

出力例：

```
True
```
