---
description: URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。
seo-description: URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。
seo-title: エンドポイントのStudioへの登録
solution: Experience Manager
title: エンドポイントのStudioへの登録
uuid: 4eb816ee-d743-43bf-bfee-d9b9fd98b482
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# エンドポイントをStudioに登録{#register-the-endpoint-with-studio}

URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。

プルURLに対するPingの登録は、ネットワークごとに1回のみ行います。 設定した後は、ユーザー管理システムからユーザープロファイルデータを取得するエンドポイントが変更されない限り、この値を変更しないでください。

1. Studioを使用して、このURLエンドポイントをLivefyreに登録します。
1. Livefyreが更新されたユーザープロファイル情報の取得元となるURLを登録し、**[!UICONTROL Studio > Settings > Integration Settings > Remote Profiles]**&#x200B;に移動して&#x200B;**[!UICONTROL Ping for Pull URL]**&#x200B;フィールドに入力します。

   例えば、URLは次のようになります。`https://example.yoursite.com/some_path/?id={id}`

