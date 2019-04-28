---
description: URLエンドポイントを登録すると、LivefyreはURLを使用して更新されたプロファイル情報を取り込むことができます。
seo-description: URLエンドポイントを登録すると、LivefyreはURLを使用して更新されたプロファイル情報を取り込むことができます。
seo-title: エンドポイントのStudioへの登録
solution: Experience Manager
title: エンドポイントのStudioへの登録
uuid: 4eb816ee- d743-43bf- bid- d9b9fd98b482
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# エンドポイントのStudioへの登録{#register-the-endpoint-with-studio}

URLエンドポイントを登録すると、LivefyreはURLを使用して更新されたプロファイル情報を取り込むことができます。

Ping for Pull URLはネットワークごとに1回のみ登録してください。設定後、ユーザー管理システムのユーザープロファイルデータを取得するエンドポイントがない限り、この値は変更しないでください。

1. Studioを使用して、このURLエンドポイントをLivefyreに登録します。
1. Livefyreが更新したユーザープロファイル情報を取得するURLを登録し、先 **[!UICONTROL Studio > Settings > Integration Settings > Remote Profiles]** に移動して **[!UICONTROL Ping for Pull URL]** フィールドに入力します。

   例えば、URLは次のようになります。 `https://example.yoursite.com/some_path/?id={id}`

