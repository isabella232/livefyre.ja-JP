---
description: Instagramは、InstagramAPI（Livefyreを含む）を使用している会社が1トークンあたり1時間あたり5,000リクエストから200リクエストに変更しました。 これは、レート制限と呼ばれます。
title: Instagramレート制限
exl-id: b13db09b-fb5a-4711-a566-d0976172e35e
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# トラブルシューティング：instagramコンテンツの制限{#instagram-rate-limiting}

Instagramは、InstagramAPI（Livefyreを含む）を使用している会社が1トークンあたり1時間あたり5,000リクエストから200リクエストに変更しました。 これは、*レート制限*&#x200B;と呼ばれます。

トークンは、Instagramアカウントと同じです。

次の理由から、検索やInstagramからのコンテンツの取得が制限されるエラーが発生する場合があります。

* 1つのアカウントを複数のストリームに使用している
* instagram川が多い
* 大量のハッシュタグを使用している可能性がある（例：`#cats`、`#beach`）

instagramレート制限の影響を低減するには：

* 複数のInstagramアカウントをネットワークに接続します。 ネットワークにInstagramアカウントを追加する方法については、[Instagramアカウントについて](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)を参照してください。
使用していないInstagramストリームをオフにする
ストリームが適切なキーワードでターゲット設定されていることを確認し、スマートタグフィルターを使用してクエリをより正確にします。 スマートタグフィルターの使用方法について詳しくは、「[スマートタグ](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md)」を参照してください
複数の人がネットワーク上で同じInstagramアカウントを使用してInstagramのコンテンツをキュレーションする際に、時間を最小限に抑えます。
