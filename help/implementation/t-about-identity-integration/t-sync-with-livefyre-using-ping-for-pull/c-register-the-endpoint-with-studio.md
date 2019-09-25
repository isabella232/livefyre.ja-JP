---
description: URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。
seo-description: URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。
seo-title: エンドポイントのStudioへの登録
solution: Experience Manager
title: エンドポイントのStudioへの登録
uuid: 4eb816ee-d743-43bf-bfee-d9b9fd98b482
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# エンドポイントのStudioへの登録{#register-the-endpoint-with-studio}

URLエンドポイントを登録して、LivefyreがURLを使用して更新されたプロファイル情報を取り込めるようにします。

プルURLに対するpingをネットワークごとに1回だけ登録します。 設定した後は、ユーザー管理システムからユーザープロファイルデータを取得するエンドポイントが変更されない限り、この値は変更しないでください。

1. Studioを使用して、このURLエンドポイントをLivefyreに登録します。
1. Livefyreが更新されたユーザープロファイル情報の取得元となるURLを登録し、に移動し **[!UICONTROL Studio > Settings > Integration Settings > Remote Profiles]**&#x200B;て、フィールドに入力 **[!UICONTROL Ping for Pull URL]** します。

   例えば、URLは次のようになります。 `https://example.yoursite.com/some_path/?id={id}`

