---
description: URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。
title: エンドポイントのStudioへの登録
exl-id: 2910a13a-ae88-41d7-ba7c-88d7a1dbe445
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---

# エンドポイントをStudioに登録{#register-the-endpoint-with-studio}

URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。

プルURLに対するPingの登録は、ネットワークごとに1回のみ行います。 設定した後は、ユーザー管理システムからユーザープロファイルデータを取得するエンドポイントが変更されない限り、この値を変更しないでください。

1. Studioを使用して、このURLエンドポイントをLivefyreに登録します。
1. Livefyreが更新されたユーザープロファイル情報の取得元となるURLを登録し、**[!UICONTROL Studio > Settings > Integration Settings > Remote Profiles]**&#x200B;に移動して&#x200B;**[!UICONTROL Ping for Pull URL]**&#x200B;フィールドに入力します。

   例えば、URLは次のようになります。`https://example.yoursite.com/some_path/?id={id}`
