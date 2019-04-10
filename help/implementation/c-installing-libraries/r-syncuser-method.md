---
description: 以前に設定されたユーザー同期URLからユーザー情報をプルするようLivefyreに指示します。ブール値を返します。
seo-description: 以前に設定されたユーザー同期URLからユーザー情報をプルするようLivefyreに指示します。ブール値を返します。
seo-title: SyncUserネットワークメソッド
solution: Experience Manager
title: SyncUserネットワークメソッド
uuid: 2afb03d-3907-4b01-9a64-02ba1b06da14
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# SyncUserネットワークメソッド{#syncuser-network-method}

以前に設定されたユーザー同期URLからユーザー情報をプルするようLivefyreに指示します。ブール値を返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| userId | 文字列 | Livefyreと同期するユーザーID。このメソッドを呼び出す前に、Livefyreと共にユーザー同期URLを設定する必要があります。 |

## Javaの例 {#section_nyl_ycs_rz}

```
network.syncUser(userId); 
```

サンプル出力:

```
true
```

## NodeJSの例 {#section_xkd_gds_rz}

```
network.syncUser(userId); 
```

サンプル出力:

```
true
```

## PHPの例 {#section_ghf_gds_rz}

```
$network->syncUser(userId); 
```

サンプル出力:

```
true
```

## Pythonの例 {#section_dwg_gds_rz}

```
network.sync_user(userId) 
```

サンプル出力:

```
True
```

## ルビの例 {#section_enh_gds_rz}

```
network.sync_user(userId) 
```

サンプル出力:

```
True
```
