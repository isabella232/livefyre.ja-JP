---
description: InstagramおよびTwitterの投稿の権限をリクエストする設定を定義します。
seo-description: InstagramおよびTwitterの投稿の権限をリクエストする設定を定義します。
seo-title: Rights Managementの設定
solution: Experience Manager
title: Rights Managementの設定
uuid: 3ffcbc95-484f-4eba-b817-658c1d658bf8
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---


# Rights Management{#set-up-rights-management}の設定

InstagramおよびTwitterの投稿の権限をリクエストする設定を定義します。

権限要求の設定を定義する前に、InstagramまたはTwitterの1つ以上のソーシャルアカウントを設定する必要があります。 Socialアカウントの設定方法について詳しくは、「[Socialアカウント追加](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/t-configure-social-accout-instagram.md#t_configure_social_accout_instagram)」を参照してください。

>[!NOTE]
>
>Rights Managementは、Networkレベルでのみ設定できます。 サイト固有の権限管理は設定できません。

1. Livefyre Studio内で、**[!UICONTROL Network]** **[!UICONTROL Settings > Rights Management]**&#x200B;に移動します。

   >[!NOTE]
   >
   >Rights Managementアカウントを設定するには、モデレーターまたは管理者のネットワークレベルの権限が必要です。

1. Rights Managementアカウントを設定していない場合は、**[!UICONTROL +Add New Account]**&#x200B;を選択します。
1. Rights Managementに使用するソーシャルネットワークの下の&#x200B;**[!UICONTROL Create New Setting]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >Instagramアカウントの場合、部分的な自動化を使用して権限をリクエストするには、Instagramのビジネスアカウントが必要です。 様々な種類のInstagramアカウントとその使用方法について詳しくは、[Instagramアカウントについて](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)を参照してください。

1. 表示されたフィールドに入力します。 すべてのフィールドが必須です。

   * **[!UICONTROL Display name:]** 権利要求アカウントに使用するTwitterまたはInstagramアカウントを識別する表示名を入力します。この名前は内部でのみ使用されます。
   * **[!UICONTROL Enabled:]**デフォルトでonに設定されます。 アカウントの権限管理を有効にします。
   * **[!UICONTROL Approval hashtag:]** コンテンツの所有者がコンテンツの使用に同意したことを示すために使用するハッシュタグ。
   * **[!UICONTROL Terms and conditions:]** コンテンツを再利用するためのネットワーク利用規約へのリンク。このフィールドでは大文字と小文字が区別されます。
   * **[!UICONTROL Network and sites:]** このアカウントがコンテンツの再利用権限を要求できるネットワークまたはサイトです。このアカウントをネットワーク全体で使用できるようにするには、リストの最初の項目を選択するか、Command/Ctrlキーを押しながら特定のサイトに制限します。
   * **[!UICONTROL Default message:]** 権限リクエストで表示するメッセージです。権限を要求するときに、このメッセージを上書きできます。

      * モデレーターがコンテンツ作成者にリクエストを発行すると、Livefyreがモデレーターにデフォルトメッセージの1つを表示します。 モデレーターは、別のデフォルトメッセージを生成したり、送信前にメッセージを編集したりできます。 メッセージには、発言者のTwitterまたはInstagramのハンドル({handle})、承認ハッシュタグ({grantTag})、利用条件へのリンク({termsLink})が含まれている必要があります。

         **[!UICONTROL Note:]** {handle}、{grantTag}、{termsLink}はすべて大文字と小文字が区別されます。

         **[!UICONTROL Note:]** 悪意のある使用を防ぐために、Twitterは含まれるURLを [t.](https://t.co/) coformattingでラップします。デフォルトのメッセージが140文字を超えないようにするため、Livefyreでは、デフォルトのメッセージにURLを含めないことをお勧めします。

      * 権利要求メッセージを書き込むためのベストプラクティス：

         * ロボットのように聞こえないように、複数の初期設定のメッセージを作成します。 次のデフォルトメッセージを作成する前に、各デフォルトメッセージを保存します。
         * モデレーターに、送信する前にこのメモをパーソナライズするよう促し、ネットワークの要求がスパムとタグ付けされないようにします。

1. **[!UICONTROL Save Settings]**をクリックして、権限要求アカウントを追加します。
アセットライブラリからの権限要求の送信 アセットライブラリから権限要求を送信する方法について詳しくは、[権限要求の送信](../c-how-requesting-rights-works/t-send-a-rights-request-to-own-a-digital-asset.md#t_send_a_rights_request_to_own_a_digital_asset)を参照してください。