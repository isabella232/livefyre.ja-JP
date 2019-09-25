---
description: Livefyreのソーシャルユーザー管理システムの使用
seo-description: Livefyreのソーシャルユーザー管理システムの使用
seo-title: Livefyre ID
solution: Experience Manager
title: Livefyre ID
uuid: 5e9219b4-fbd7-40c6-9d57-129bb0649714
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# Livefyre IDの使用{#livefyre-identity}

カスタムまたはサードパーティのユーザー管理システムを使用する場合は、この節をスキップしてください。

ユーザーは、ソーシャルメディアアカウントまたはサイト専用に作成された電子メールベースのアカウントを使用して、アプリにログインできます。

Livefyre IDパッケージには、認証の委任に必要な情報が含まれています。 （したがって、Livefyre IDに対して明示的な認証委任は必要ありません）。

Livefyre統合にSocialサインオンを追加するには：

1. ソーシャルアプリを作成します。
1. アプリをLivefyreに接続します。
1. ページにLivefyre.jsを追加します。
1. Livefyre IDを初期化します。

>[!NOTE]
>
>このドキュメントでは、ソーシャルプロバイダーのアプリ作成プロセスに関するLivefyre固有の側面を示します。 Livefyreは、インターフェイスに対する変更を一切責任を負いません。また、Livefyreは、これらのアプリの作成や承認プロセスに関する支援を行うこともできません。 Twitter、Facebook、Yahoo!、Googleの開発者情報を使用してこれらのアプリを作成し、必要に応じてその承認プロセスに移動してください。

