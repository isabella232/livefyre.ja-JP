---
description: ユ追加ーザーをグループに追加するためのユーザータグをアカウントに追加します。
seo-description: ユ追加ーザーをグループに追加するためのユーザータグをアカウントに追加します。
seo-title: グループへのユーザーの追加
solution: Experience Manager
title: グループへのユーザーの追加
uuid: 3633f2df-8d60-4cdd-b9a2-3807218c74a0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---


# グループへのユーザーの追加{#adding-users-to-groups}

ユ追加ーザーをグループに追加するためのユーザータグをアカウントに追加します。

User Tagsは、独自仕様のシステムと企業向けのプロファイルシステムの両方に実装でき、次の方法でアカウントに追加できます。

* Studioを使用して所有者とモデレーターを作成すると、「モデレーター」ユーザータグがアカウントに割り当てられます。
* ユーザーグループを作成し、Studioを使用してユーザーを追加すると、選択したユーザーに、グループ名のユーザータグが自動的に適用されます。
* ユーザータグは、[追加ユーザータグHTTP](https://api.livefyre.com/docs#add-user-tag)呼び出しを使用してアカウントに直接適用するか、Pingでプルを実行します。

>[!NOTE]
>
>HTTP追加ユーザータグの呼び出しとPing for Pullメソッドの両方のAPIメソッドは、他の方法を使用して、以前にアカウントに割り当てられたタグを上書きします。 したがって、1つの方法を選択し、プロセス全体で一貫して使用してください。

## Studio &lt;a0追加/>のユーザーページからグループへのユーザー{#section_qgq_nbw_xz}

* **[!UICONTROL Add Group]**&#x200B;または任意のユーザー名の下のグループラベルをクリックして、グループメニューを開きます。
* リストをスクロールして、ユーザーを追加するグループを探します。 ドロップダウンの上部にある&#x200B;**[!UICONTROL Search]**&#x200B;ボックスにグループ名を入力できます。
* ユーザーを追加するグループの横にあるチェックボックスをクリックし、returnキーを押します。

ユーザーのプロファイルには、グループ名（ユーザーが1つのグループにのみ存在する場合）またはユーザーが属するグループの数が表示されます。

## ユ追加ーザータグの追加呼び出し{#section_kn3_gbw_xz}を使用したグループへのユーザー

POSTリクエストと共に、ユーザーのLFTokenと選択したタグ名を渡します。

例：

```
curl -XPOST -d 'tag_name=tag&lftoken=eyJhbGciOiAiA_TOKENcGlyZXMiOiAxMzU3OTY3NTAxLjIzn0.KoyXUVCavt-rdvkVXm2qzQTyMAOSp-crQA1uL1ht9WU' 'https://labs.quill.fyre.co/api/v3.0/author/system@`labs.fyre.co`/tag/'
```


詳しくは、APIリファレンス/[追加ユーザータグ](https://api.livefyre.com/docs/apis/by-category/user-management#operation=urn:livefyre:apis:quill:operations:api:v3.0:author:tags:method=post)を参照してください。

## Pingを使用し追加たグループへのユーザーの取り込み{#section_kyj_11w_xz}

ユーザーをユーザーグループに割り当てるには、tags配列を使用します。 （タグには、1 ～ 63個の英数字とアンダースコア文字を含めることができます）。

例：

```
"tags": ["moderator", "brand_advocate"],
```

## リモートプロファイル&lt;a0追加/>を使用してグループにアクセスするユーザー{#section_uyn_scv_xz}

リモートプロファイルへ追加のユーザータグ。カスタムプロファイルシステムとLivefyreの間で、特定のユーザーのユーザーデータを同期するために使用されます。
