---
description: Livefyreのソーシャルユーザー管理システムの操作を参照してください。
seo-description: Livefyreのソーシャルユーザー管理システムの操作を参照してください。
seo-title: Livefyre ID
solution: Experience Manager
title: Livefyre ID
uuid: 5e9219b4- fbd7-40c6-9d57-129bb0649714
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Livefyre IDの使用{#livefyre-identity}

カスタムまたはサードパーティのユーザー管理システムを使用する場合は、このセクションをスキップしてください。

ユーザーは、ソーシャルメディアアカウントまたは自分のサイト専用に作成された電子メールベースのアカウントを使用して、アプリにログインできます。

Livefyre Identityパッケージには、認証の委任に必要な情報が含まれています。（したがって、LivefyreのIDには明示的な認証委任は必要ありません）。

Livefyre統合にソーシャルサインオンを追加するには:

1. ソーシャルアプリを作成します。
1. アプリケーションをLivefyreに接続します。
1. ページにLivefyre. jsを追加します。
1. Livefyre IDを初期化します。

>[!NOTE]
>
>このドキュメントは、ソーシャルプロバイダーのアプリ作成プロセスに関するLivefyre固有の側面をリストしています。Livefyreはインターフェイスに対する変更を一切担当しません。また、これらのアプリケーションの作成またはその承認プロセスについてLivefyreもご不明です。利用可能なTwitter、Facebook、Yahoo!を使用してください。およびGoogle開発者情報を参照してください。

