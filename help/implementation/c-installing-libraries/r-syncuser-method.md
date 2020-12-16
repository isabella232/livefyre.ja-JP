---
description: 以前に設定したユーザー同期URLからユーザー情報を取り込むようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
seo-description: 以前に設定したユーザー同期URLからユーザー情報を取り込むようにLivefyreに通知します。 ブール型( Boolean )の値を返します。
seo-title: syncUserネットワークメソッド
solution: Experience Manager
title: syncUserネットワークメソッド
uuid: 2affb03d-3907-4b01-9a64-02ba1b06da14
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '103'
ht-degree: 4%

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
