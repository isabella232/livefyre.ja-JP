---
description: LivefyreはPUSHインターフェイスを使用して、ユーザー権限の変更に関する外部システム情報を送信します。
seo-description: LivefyreはPUSHインターフェイスを使用して、ユーザー権限の変更に関する外部システム情報を送信します。
seo-title: 外部システムへのユーザー権限の投稿（オプション）
solution: Experience Manager
title: 外部システムへのユーザー権限の投稿（オプション）
uuid: 9c18b20d-3b93-4666-b7de-1ec60318cf88
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 外部システムへのユーザー権限の投稿（オプション）{#posting-user-permissions-to-external-systems-optional}

LivefyreはPUSHインターフェイスを使用して、ユーザー権限の変更に関する外部システム情報を送信します。

## Livefyre studioのユーザーのタイプ

| ユーザータイプ | 説明 |
|--- |--- |
| 所有者 | このユーザーは所有者で、コンテンツのモデレートと新しいモデレーターの割り当ての両方を行うことができます。 |
| admin | このユーザーはモデレーターで、コンテンツをモデレートできます。 |
| 会員 | このユーザーはホワイトリストに登録されています。 投稿されたコンテンツはスパムや不敬な言葉遣いのフィルターを通過せず、モデレート前のストリームで承認を必要としません。 |
| なし | このユーザーは標準ユーザーで、特別な権限はありません。 |
| 追放する | このユーザーは、会話への参加を禁止されています。 |

外部システムにユーザー権限をPOSTするには、権限データを受け取るURLをPOST要求として登録する必要があります。

次に例を示します。

```
POST https://{networkName}.quill.fyre.co/?actor_token={token}&push_affiliation_url={url}
```

| パラメーター | 説明 |
|--- |--- |
| networkName |  Livefyreが提供するネットワーク名。 |
| token | 有効なシステムトークン。 |
| url | 登録するURL。 |

登録されたURLは、次のデータを持つPOSTをコンテンツタイプとして受け入れる必要があります。application/x-www-form-urlencoded。

| パラメーター | 説明 |
|--- |--- |
| jid | 所属を変更したユーザーのJID。 JIDはフォームの文字列です `user_id@network`。 |
| 所属 | 割り当てられた権限の名前。次のいずれかである必要があります。  `{admin | member | none | outcast | owner}` |

ユーザーの所属設定の更新について詳しくは、『 [Add User Affiliation API Reference』を参照してください](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:affiliation:add:method=post)。
