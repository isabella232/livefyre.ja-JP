---
description: Instagramは、Livefyreを含むInstagram APIを使用する会社が1時間あたり5,000件のリクエストを行えるリクエスト数を、トークンあたり1時間あたり200件のリクエストに変更しました。 これをレート制限と呼びます。
seo-description: Instagramは、Livefyreを含むInstagram APIを使用する会社が1時間あたり5,000件のリクエストを行えるリクエスト数を、トークンあたり1時間あたり200件のリクエストに変更しました。 これをレート制限と呼びます。
seo-title: Instagramのレート制限
title: Instagramのレート制限
uuid: 98108ddb-5710-4331-891b-7e1bbb106059
translation-type: tm+mt
source-git-commit: e9f672ba6e5f4338c58256e2d46ed023e84f340f

---


# トラブルシューティング：Instagramコンテンツの制限 {#instagram-rate-limiting}

Instagramは、Livefyreを含むINstagram APIを使用している会社が1トークンあたり5,000リクエストから1時間あたり200リクエストに送信できるリクエスト数を変更しました。 これは、レート制限と呼 *ばれます*。

トークンは、Instagramアカウントと同じです。

次の理由から、Instagramでのコンテンツの検索や取得の機能が制限されるエラーが発生する場合があります。

* 複数のストリームに対して1つのアカウントを使用している
* 大量のInstagramストリームがある
* 大量のハッシュタグ(例：や `#cats` )を使用 `#beach`する

Instagramのレート制限の影響を低減するには：

* 複数のInstagramアカウントをネットワークに接続します。 ネットワークにInstagramアカウントを追加する方法について詳しくは、 [](/help/using/c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md)Instagramアカウントについて使用しないInstagramストリームを無効にする適切なキーワードでストリームをターゲット設定し、スマートタグフィルターを使用してクエリをより正確に行うを参照してください。 スマートタグフィルターの使用方法について詳しくは、スマートタグ [](/help/using/c-features-livefyre/c-smart-tags/c-smart-tags.md)Instagramのコンテンツをキュレーションするために、複数のユーザーがネットワーク上で同じInstagramアカウントを使用している場合に、時間を最小限に抑えるを参照してください。