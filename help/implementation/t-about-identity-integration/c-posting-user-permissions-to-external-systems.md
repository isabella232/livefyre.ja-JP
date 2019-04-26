---
description: Livefyreは、プッシュインターフェイスを使用して、ユーザー権限に関する変更に関する外部システム情報を送信します。
seo-description: Livefyreは、プッシュインターフェイスを使用して、ユーザー権限に関する変更に関する外部システム情報を送信します。
seo-title: 外部システムへのユーザー権限の投稿（オプション）
solution: Experience Manager
title: 外部システムへのユーザー権限の投稿（オプション）
uuid: 9c18b20d-3b93-4666- b7de-1ec60318cf88
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 外部システムへのユーザー権限の投稿（オプション）{#posting-user-permissions-to-external-systems-optional}

Livefyreは、プッシュインターフェイスを使用して、ユーザー権限に関する変更に関する外部システム情報を送信します。

## Livefyre Studioのユーザーのタイプ

| ユーザータイプ | 説明 |
|--- |--- |
| owner | このユーザーは所有者であり、コンテンツをモデレートして、新しいモデレーターを割り当てることができます。 |
| admin | このユーザーはモデレーターで、コンテンツをモデレートできます。 |
| member | このユーザーはホワイトリスト登録されています。投稿されたコンテンツはスパムまたは違反フィルターを通過せず、モデレート済みストリームの承認を必要としません。 |
| none | このユーザーは標準ユーザーで、特別な権限はありません。 |
| アウトキャスト | このユーザーは、どの会話にも参加できません。 |

外部システムにユーザー権限を投稿するには、権限データをPOSTリクエストとして受け取るURLを登録する必要があります。

次に例を示します。

```
POST https://{networkName}.quill.fyre.co/?actor_token={token}&push_affiliation_url={url}
```

| パラメータ | 説明 |
|--- |--- |
| NetworkName | Livefyreが提供するネットワーク名。 |
| トークン | 有効なシステムトークン。 |
| url | 登録するURL。 |

登録されたURLは、content- typeとして次のデータを持つ投稿を受け入れる必要があります。application/x- www- form- urlencoded.

| パラメータ | 説明 |
|--- |--- |
| jid | アフィリネーションが変更されたユーザーのJID。JIDはフォームの文字列 `user_id@network`です。 |
| アフィリエイト | 割り当てられた権限の名前。次のいずれかになります。 `{admin | member | none | outcast | owner}` |

ユーザーアフィリエイトの設定の更新について詳しくは、「ユーザーアフィリエイトAPIリファレンス [の追加](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:affiliation:add:method=post)」を参照してください。
