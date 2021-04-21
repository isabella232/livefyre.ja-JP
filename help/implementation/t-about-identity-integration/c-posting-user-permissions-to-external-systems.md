---
description: LivefyreはPUSHインターフェイスを使用して、ユーザー権限への変更に関する外部システム情報を送信します。
title: 外部システムへのユーザー権限の投稿（オプション）
exl-id: 335c9ff2-e392-4310-aad2-7890c8e82eba
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---

# 外部システムへのユーザー権限の送信（オプション）{#posting-user-permissions-to-external-systems-optional}

LivefyreはPUSHインターフェイスを使用して、ユーザー権限への変更に関する外部システム情報を送信します。

## Livefyre Studioのユーザーのタイプ

| ユーザータイプ | 説明 |
|--- |--- |
| owner | このユーザーは所有者で、コンテンツのモデレートと、新しいモデレーターの割り当ての両方を行うことができます。 |
| admin | このユーザーはモデレーターで、コンテンツをモデレートできます。 |
| menver | このユーザーは許可一覧に表示されます。 投稿されたコンテンツはスパムや不敬な言葉遣いのフィルターを通過せず、モデレート前のストリームでの承認も必要ありません。 |
| なし | このユーザーは標準ユーザーで、特別な権限はありません。 |
| 追放 | このユーザーは、会話への参加を禁止されています。 |

ユーザー権限を外部システムにPOSTするには、権限データを受け取るURLをPOST要求として登録する必要があります。

例：

```
POST https://{networkName}.quill.fyre.co/?actor_token={token}&push_affiliation_url={url}
```

| パラメーター | 説明 |
|--- |--- |
| networkName | Livefyreから提供されたネットワーク名。 |
| token | 有効なシステムトークン。 |
| url | 登録するURL。 |

登録されたURLは、次のデータを持つPOSTをコンテンツタイプとして受け取る必要があります。application/x-www-form-urlencoded

| パラメーター | 説明 |
|--- |--- |
| jid | 所属を変更したユーザーのJID。 JIDは`user_id@network`の形式の文字列です。 |
| 所属 | 割り当てられる権限の名前。次のいずれかである必要があります。 `{admin | member | none | outcast | owner}` |

ユーザー所属設定の更新について詳しくは、[追加ユーザー所属APIリファレンス](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:affiliation:add:method=post)を参照してください。
