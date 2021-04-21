---
description: Livefyreのソーシャルユーザー管理システムの使用
title: Livefyre ID
exl-id: 1e6149b6-dcdb-4e2a-a19d-06b24fe1288a
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Livefyre IDを使用{#livefyre-identity}

カスタムまたはサードパーティのユーザー管理システムを使用する場合は、この節をスキップします。

ユーザーは、ソーシャルメディアアカウントまたはサイト専用に作成された電子メールベースのアカウントを使用して、アプリにログインできます。

Livefyre IDパッケージには、認証の委任に必要な情報が含まれています。 （したがって、Livefyre IDに明示的な認証委任は必要ありません）。

Livefyre統合にソーシャルサインオンを追加するには：

1. ソーシャルアプリを作成します。
1. アプリをLivefyreに接続します。
1. 追加Livefyre.jsをページに追加します。
1. Livefyre IDを初期化します。

>[!NOTE]
>
>このドキュメントリストは、ソーシャルプロバイダーのアプリ作成プロセスに固有の側面をLivefyreに提供します。 Livefyreは、インターフェイスに対する変更を一切責任を負いません。また、Livefyreは、これらのアプリケーションの作成や承認プロセスに関する支援を行うこともできません。 これらのアプリの作成、承認プロセス（必要に応じて）のナビゲーションには、利用可能なTwitter、Facebook、Yahoo!、Googleの開発者情報を使用してください。
