---
description: ユーザーをグループに追加するためのユーザータグをアカウントに追加します。
seo-description: ユーザーをグループに追加するためのユーザータグをアカウントに追加します。
seo-title: グループへのユーザーの追加
solution: Experience Manager
title: グループへのユーザーの追加
uuid: 3633f2df-8d60-4cdd- b9a2-3807218c74a0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# グループへのユーザーの追加{#adding-users-to-groups}

ユーザーをグループに追加するためのユーザータグをアカウントに追加します。

ユーザータグは、独自のプロファイルシステムとエンタープライズプロファイルシステムの両方に実装でき、いくつかの方法でアカウントに追加できます。

* Studioを使用して所有者およびモデレーターを作成すると、「モデレーター」ユーザータグがアカウントに割り当てられます。
* ユーザーグループを作成し、ユーザーをStudio経由で追加すると、選択したユーザーのグループ名とともにユーザータグが自動的に適用されます。
* ユーザータグは [、Add User Tag HTTP](https://api.livefyre.com/docs#add-user-tag) 呼び出しを使用して、またはPing for Pullを使用して直接アカウントに適用することもできます。

>[!NOTE]
>
>両方のAPIメソッド、HTTP追加のUser Tag呼び出しおよびPingのPingメソッドは、以前にアカウントに割り当てられていたタグを他の手段から上書きします。したがって、1つの方法を選択し、プロセス全体で一貫して使用してください。

## Studioのユーザーページからのユーザーのグループへの追加 {#section_qgq_nbw_xz}

* 任意のユーザー名の下にあるクリック **[!UICONTROL Add Group]** またはグループラベルをクリックして、グループメニューを開きます。
* リストをスクロールし、ユーザーを追加するグループを見つけます。ドロップダウンの上部にある **[!UICONTROL Search]** ボックスにグループ名を入力できます。
* ユーザーを追加するグループの横にあるチェックボックスをクリックし、リターンをクリックします。

ユーザーのプロファイルには、グループ名（ユーザーが1つだけの場合）またはユーザーが所属するグループの数が表示されます。

## Add User Tag呼び出しを使用したグループへのユーザーの追加 {#section_kn3_gbw_xz}

ユーザーのLfTokenと選択したタグ名をPOSTリクエストで渡します

次に例を示します。

```
curl -XPOST -d 'tag_name=tag&lftoken=eyJhbGciOiAiA_TOKENcGlyZXMiOiAxMzU3OTY3NTAxLjIzn0.KoyXUVCavt-rdvkVXm2qzQTyMAOSp-crQA1uL1ht9WU' 'https://labs.quill.fyre.co/api/v3.0/author/system@`labs.fyre.co`/tag/'
```


詳しくは、APIリファレンス/ユーザータグ [の追加](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:author:tags:method=post)を参照してください。

## Ping for Pullを使用したグループへのユーザーの追加 {#section_kyj_11w_xz}

ユーザーグループにユーザーを割り当てるには、タグ配列を使用します。（1~63の英数字とアンダースコア文字を含めることができます）。

次に例を示します。

```
"tags": ["moderator", "brand_advocate"],
```

## リモートプロファイルを使用したグループへのユーザーの追加 {#section_uyn_scv_xz}

ユーザータグをリモートプロファイルに追加し、カスタムプロファイルシステムとLivefyreの間でユーザーのデータを同期するために使用します。
