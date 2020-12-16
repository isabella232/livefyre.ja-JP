---
description: Instagramは、Livefyreを含むInstagram APIを使用する会社が1トークンあたり5,000個のリクエストから200個のリクエストに行えるリクエストの数を変更しました。 これは、レート制限と呼ばれます。
seo-description: Instagramは、Livefyreを含むInstagram APIを使用する会社が1トークンあたり5,000個のリクエストから200個のリクエストに行えるリクエストの数を変更しました。 これは、レート制限と呼ばれます。
seo-title: Instagramのレート制限
title: Instagramのレート制限
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: e9f672ba6e5f4338c58256e2d46ed023e84f340f
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---


# トラブルシューティング：Instagramコンテンツの制限{#instagram-rate-limiting}

Instagramは、INstagram APIを使用する会社（Livefyreを含む）が1トークンあたり5,000個のリクエストから200個のリクエストに変換できるリクエストの数を、トークンあたり1時間に5,000個に変更しました。 これは、*レート制限*&#x200B;と呼ばれます。

トークンは、Instagramアカウントと同じです。

次の理由から、Instagramでのコンテンツの検索や取得の機能が制限されるエラーが発生する場合があります。

* 1つのアカウントを複数のストリームに使用している
* 大量のInstagramストリームがある
* 大量のハッシュタグを使用している可能性がある（例：`#cats`、`#beach`）

Instagramのレート制限の影響を低減するには：

* 複数のInstagramアカウントをネットワークに接続します。 ネットワークにInstagramアカウントを追加する方法については、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。
使用していないInstagramストリームを無効にする
ストリームが適切なキーワードでターゲット設定されていることを確認し、スマートタグフィルターを使用してクエリをより正確にします。 スマートタグフィルターの使用方法について詳しくは、「[スマートタグ](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md)」を参照してください
複数のユーザーがネットワーク上で同じInstagramアカウントを使用してInstagramのコンテンツをキュレーションする場合に、時間を最小限に抑えます。