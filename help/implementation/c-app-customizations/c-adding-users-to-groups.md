---
description: アカウントにユーザータグを追加して、ユーザーをグループに追加します。
seo-description: アカウントにユーザータグを追加して、ユーザーをグループに追加します。
seo-title: グループへのユーザーの追加
solution: Experience Manager
title: グループへのユーザーの追加
uuid: 3633f2df-8d60-4cdd-b9a2-3807218c74a0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Adding Users to Groups{#adding-users-to-groups}

アカウントにユーザータグを追加して、ユーザーをグループに追加します。

ユーザータグは、独自仕様のプロファイルシステムとエンタープライズプロファイルシステムの両方に対して実装でき、次の方法でアカウントに追加できます。

* Studioを使用して所有者とモデレーターを作成すると、「モデレーター」ユーザータグがアカウントに割り当てられます。
* ユーザーグループを作成し、Studioを使用してユーザーを追加すると、選択したユーザーに対して、グループ名の付いたユーザータグが自動的に適用されます。
* ユーザータグは、 [Add User Tag HTTP呼び出しを使用してアカウントに直接適用するか](https://api.livefyre.com/docs#add-user-tag) 、Ping for Pullを使用して適用することもできます。

>[!NOTE]
>
>APIメソッド（HTTP Add User Tag呼び出し）とPing for Pullメソッドの両方)は、他の方法を使用してアカウントに以前に割り当てられたタグを上書きします。 したがって、1つの方法を選択し、プロセス全体で一貫して使用してください。

## Studioのユーザーページからグループにユーザーを追加する {#section_qgq_nbw_xz}

* 任意のユ **[!UICONTROL Add Group]** ーザ名の下のグループラベルをクリックして、グループメニューを開きます。
* リストをスクロールし、ユーザーを追加するグループを探します。 ドロップダウンの上部にあるボックスに **[!UICONTROL Search]** グループ名を入力することができます。
* ユーザーを追加するグループの横にあるチェックボックスをクリックし、「return」をクリックします。

ユーザーのプロファイルには、グループの名前（ユーザーが1つのグループにのみ存在する場合）またはユーザーが属するグループの数が表示されます。

## ユーザータグの追加の呼び出しを使用したグループへのユーザーの追加 {#section_kn3_gbw_xz}

POSTリクエストを使用して、ユーザーのLFTokenと選択したタグ名を渡します

次に例を示します。

```
curl -XPOST -d 'tag_name=tag&lftoken=eyJhbGciOiAiA_TOKENcGlyZXMiOiAxMzU3OTY3NTAxLjIzn0.KoyXUVCavt-rdvkVXm2qzQTyMAOSp-crQA1uL1ht9WU' 'https://labs.quill.fyre.co/api/v3.0/author/system@`labs.fyre.co`/tag/'
```


詳しくは、API Reference/ [Add User tagを参照してください](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:author:tags:method=post)。

## Pingを使用した引き出しによるグループへのユーザーの追加 {#section_kyj_11w_xz}

tags配列を使用して、ユーザーをユーザーグループに割り当てます。 （タグには、1 ～ 63文字の英数字とアンダースコアを含めることができます）。

次に例を示します。

```
"tags": ["moderator", "brand_advocate"],
```

## リモートプロファイルを使用したグループへのユーザーの追加 {#section_uyn_scv_xz}

特定のユーザーのカスタムプロファイルシステムとLivefyreの間でユーザーデータを同期するために使用するユーザータグをリモートプロファイルに追加します。
