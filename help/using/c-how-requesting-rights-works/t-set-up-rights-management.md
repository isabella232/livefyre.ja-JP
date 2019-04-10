---
description: InstagramおよびTwitter投稿の権限をリクエストする設定を定義します。
seo-description: InstagramおよびTwitter投稿の権限をリクエストする設定を定義します。
seo-title: Rights Managementの設定
solution: Experience Manager
title: Rights Managementの設定
uuid: 3ffcbc95-484f-4eem- b817-658c1d658bf8
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Rights Managementの設定{#set-up-rights-management}

InstagramおよびTwitter投稿の権限をリクエストする設定を定義します。

Rights Request Settingsを定義するには、InstagramまたはTwitter用に1つ以上のソーシャルアカウントを設定する必要があります。ソーシャルアカウントの設定方法について詳しくは、Socialアカウント [の追加を](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/t-configure-social-accout-instagram.md#t_configure_social_accout_instagram)参照してください。

>[!NOTE]
>
>Rights Managementはネットワークレベルでのみ設定できます。サイト固有の権限管理を設定することはできません。

1. Livefyre Studio内で、に移動 **[!UICONTROL Network]****[!UICONTROL Settings > Rights Management]**します。

   >[!NOTE]
   >
   >Rights Managementアカウントを設定するには、モデレーターまたは管理者ネットワークレベルの権限が必要です。

1. Rights **[!UICONTROL +Add New Account]** Managementアカウントが設定されていない場合に選択します。
1. Rights **[!UICONTROL Create New Setting]** Managementで使用するソーシャルネットワークの下をクリックします。

   >[!NOTE]
   >
   >Instagramアカウントの場合、部分的な自動化を行う権限をリクエストするには、Instagramのビジネスアカウントが必要です。Instagramアカウントの種類と使用方法について詳しくは、Instagramアカウント [について](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

1. 表示されているフィールドに入力します。すべてのフィールドが必須です。

   * **[!UICONTROL Display name:]** Rights Requestアカウントに使用するTwitterアカウントまたはInstagramアカウントを識別する表示名を入力します。この名前は内部のみです。
   * ****[!UICONTROL Enabled:]デフォルトではオンに設定されています。アカウントの権限管理を有効にします。
   * **[!UICONTROL Approval hashtag:]** コンテンツ所有者がコンテンツの使用に同意することを示すために使用するハッシュタグ。
   * **[!UICONTROL Terms and conditions:]** コンテンツを再利用するためのネットワークの利用条件へのリンク。このフィールドでは大文字と小文字が区別されます。
   * **[!UICONTROL Network and sites:]** このアカウントがコンテンツの再利用権限をリクエストできるネットワークまたはサイト。このアカウントをネットワーク全体で使用できるようにするには、リスト内の最初のアイテムを選択するか、Command/Ctrlキーを使用して特定のサイトに制限します。
   * **[!UICONTROL Default message:]** Rights Requestと共に表示するメッセージです。権限をリクエストするときに、このメッセージを上書きできます。

      * モデレーターがコンテンツ作成者にリクエストを発行すると、デフォルトメッセージの1つがLivefyreに表示されます。モデレーターは、別のデフォルトメッセージを生成するか、送信する前にメッセージを編集することができます。メッセージには、発言者のTwitterまたはInstagramハンドル（{handle}）、承認ハッシュタグ（{grantTag}）および利用条件へのリンク（{TerMSLink}）を含める必要があります。

         **[!UICONTROL Note:]** {handle}、{grantTag}、{terMSLink}はすべて大文字と小文字が区別されます。

         **[!UICONTROL Note:]** 悪意のある使用を防ぐために、Twitterは [、t. co](https://t.co/) 形式のURLを含めます。デフォルトメッセージが140文字を超えないようにするため、LivefyreはデフォルトメッセージにURLを含めないように推奨します。

      * 権限リクエストメッセージを記述するためのベストプラクティス:

         * ロボットのように聞こえないように、複数のデフォルトメッセージを作成します。次のデフォルトメッセージを作成する前に、各デフォルトメッセージを保存します。
         * 送信する前にこのメモをパーソナライズするようモデレーターに促し、ネットワークの要求にスパムがタグ付けされないようにします。

1. をクリック **[!UICONTROL Save Settings]** して、Rights Requestアカウントを追加します。
アセットライブラリから権限リクエストを送信します。アセット [ライブラリからの権限リクエストの送信方法について詳しくは、"Rights Request](../c-how-requesting-rights-works/t-send-a-rights-request-to-own-a-digital-asset.md#t_send_a_rights_request_to_own_a_digital_asset) の送信」を参照してください。