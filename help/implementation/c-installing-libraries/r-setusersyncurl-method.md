---
description: ネットワークのユーザー同期URLを指定されたURLに更新するようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
title: setUserSyncUrlネットワークメソッド
exl-id: 8124ac0f-013f-4943-a33c-6cf8fe696f95
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 6%

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
