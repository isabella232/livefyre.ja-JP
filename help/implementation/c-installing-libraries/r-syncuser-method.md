---
description: 以前に設定したユーザー同期URLからユーザー情報を取り込むようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
title: syncUserネットワークメソッド
exl-id: a21ff487-2ab1-4788-b455-84941f03a98f
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 5%

---

# syncUserネットワークメソッド{#syncuser-network-method}

以前に設定したユーザー同期URLからユーザー情報を取り込むようにLivefyreに通知します。 ブール型( Boolean )の値を返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| userId | 文字列 | Livefyreと同期するユーザーID。 このメソッドを呼び出す前に、Livefyreでユーザー同期URLを設定しておく必要があります。 |

## Javaの例{#section_nyl_ycs_rz}

```
network.syncUser(userId); 
```

出力例：

```
true
```

## NodeJSの例{#section_xkd_gds_rz}

```
network.syncUser(userId); 
```

出力例：

```
true
```

## PHPの例{#section_ghf_gds_rz}

```
$network->syncUser(userId); 
```

出力例：

```
true
```

## Pythonの例{#section_dwg_gds_rz}

```
network.sync_user(userId) 
```

出力例：

```
True
```

## Rubyの例{#section_enh_gds_rz}

```
network.sync_user(userId) 
```

出力例：

```
True
```
