---
description: 呼び出されたネットワークの暗号化されたユーザー認証トークンを返します。
seo-description: 呼び出されたネットワークの暗号化されたユーザー認証トークンを返します。
seo-title: BuildUserAuthTokenネットワークメソッド
solution: Experience Manager
title: BuildUserAuthTokenネットワークメソッド
uuid: 8828d356- c3c6-46a6-91bf-83bd59e35050
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# BuildUserAuthTokenネットワークメソッド{#builduserauthtoken-network-method}

呼び出されたネットワークの暗号化されたユーザー認証トークンを返します。

| 変数 | タイプ | 説明 |
|--- |--- |--- |
| userId | 文字列 | このトークンが属するユーザーのユーザーID。 |
| displayName | 文字列 | ユーザーの表示名。 |
| expires | Double | トークンの有効期限が秒単位である場合。 |

## Javaの例 {#section_nyl_ycs_rz}

```
network.buildUserAuthToken(userId, displayName, expires); 
```

サンプル出力:

```
eyJhbGciOiJIUzI1NiJ9.eyJkb21haW4iOiJ0ZXN0LmZ5cmUuY29tIiwidXNlcl9pZCI6InN5c3RlbSIsImRpc3BsYXlfbmFtZSI6InN5c3RlbSIsImV4cGlyZXMiOjEzOTY2NTUwODN9.33GuJF_ou2O6CCV22Y3PlLUgP2Igy9vAXfmLONkt-Yo 
```

## NodeJSの例 {#section_xkd_gds_rz}

```
network.buildUserAuthToken(userId, displayName, expires); 
```

サンプル出力:

```
eyJhbGciOiJIUzI1NiJ9.eyJkb21haW4iOiJ0ZXN0LmZ5cmUuY29tIiwidXNlcl9pZCI6InN5c3RlbSIsImRpc3BsYXlfbmFtZSI6InN5c3RlbSIsImV4cGlyZXMiOjEzOTY2NTUwODN9.33GuJF_ou2O6CCV22Y3PlLUgP2Igy9vAXfmLONkt-Yo 
```

## PHPの例 {#section_ghf_gds_rz}

```
$network->buildUserAuthToken(userId, displayName, expires); 
```

サンプル出力:

```
eyJhbGciOiJIUzI1NiJ9.eyJkb21haW4iOiJ0ZXN0LmZ5cmUuY29tIiwidXNlcl9pZCI6InN5c3RlbSIsImRpc3BsYXlfbmFtZSI6InN5c3RlbSIsImV4cGlyZXMiOjEzOTY2NTUwODN9.33GuJF_ou2O6CCV22Y3PlLUgP2Igy9vAXfmLONkt-Yo
```

## Pythonの例 {#section_dwg_gds_rz}

```
network.build_user_auth_token(userId, displayName, expires) 
```

サンプル出力:

```
eyJhbGciOiJIUzI1NiJ9.eyJkb21haW4iOiJ0ZXN0LmZ5cmUuY29tIiwidXNlcl9pZCI6InN5c3RlbSIsImRpc3BsYXlfbmFtZSI6InN5c3RlbSIsImV4cGlyZXMiOjEzOTY2NTUwODN9.33GuJF_ou2O6CCV22Y3PlLUgP2Igy9vAXfmLONkt-Yo
```

## ルビの例 {#section_enh_gds_rz}

```
network.build_user_auth_token(userId, displayName, expires) 
```

サンプル出力:

```
eyJhbGciOiJIUzI1NiJ9.eyJkb21haW4iOiJ0ZXN0LmZ5cmUuY29tIiwidXNlcl9pZCI6InN5c3RlbSIsImRpc3BsYXlfbmFtZSI6InN5c3RlbSIsImV4cGlyZXMiOjEzOTY2NTUwODN9.33GuJF_ou2O6CCV22Y3PlLUgP2Igy9vAXfmLONkt-Yo
```
