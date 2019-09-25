---
description: InstagramおよびTwitter投稿の権限をリクエストするための設定を定義します。
seo-description: InstagramおよびTwitter投稿の権限をリクエストするための設定を定義します。
seo-title: Rights Managementの設定
solution: Experience Manager
title: Rights Managementの設定
uuid: 3ffcbc95-484f-4eba-b817-658c1d658bf8
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# Rights Managementの設定{#set-up-rights-management}

InstagramおよびTwitter投稿の権限を要求するための設定を定義します。

権限リクエストの設定を定義する前に、InstagramまたはTwitter用に1つ以上のソーシャルアカウントを設定する必要があります。 Socialアカウントの設定方法について詳しくは、「Socialアカウントの追加」 [を参照してください](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/t-configure-social-accout-instagram.md#t_configure_social_accout_instagram)。

>[!NOTE]
>
>Rights Managementは、Networkレベルでのみ設定できます。 サイト固有の権限管理は設定できません。

1. Livefyre studio内で、に移動します **[!UICONTROL Network]****[!UICONTROL Settings > Rights Management]**。

   >[!NOTE]
   >
   >Rights Managementアカウントを設定するには、モデレーターまたは管理者のネットワークレベルの権限が必要です。

1. Rights Managementア **[!UICONTROL +Add New Account]** カウントを設定していない場合に選択します。
1. Rights Managementで **[!UICONTROL Create New Setting]** 使用するソーシャルネットワークの下のをクリックします。

   >[!NOTE]
   >
   >Instagramアカウントの場合、部分的な自動化を使用して権限を要求するには、Instagramビジネスアカウントが必要です。 様々な種類のInstagramアカウントとその使用方法について詳しくは、Instagramアカウントについてを参照 [してください](../c-users-creating-accounts-with-studio-access/t-configure-social-accout-instagram/c-about-instagram-accounts.md#c_about_instagram_accounts)。

1. 表示されたフィールドに入力します。 すべてのフィールドが必須です。

   * **[!UICONTROL Display name:]** 権利要求アカウントに使用するTwitterまたはInstagramアカウントを識別する表示名を入力します。 この名前は内部でのみ使用されます。
   * **[!UICONTROL Enabled:]**デフォルトでonに設定されます。 アカウントの権限管理を有効にします。
   * **[!UICONTROL Approval hashtag:]** コンテンツの所有者がコンテンツの使用に同意したことを示すために使用するハッシュタグ。
   * **[!UICONTROL Terms and conditions:]** コンテンツを再利用するための、お使いのネットワークの利用条件へのリンクです。 このフィールドでは大文字と小文字が区別されます。
   * **[!UICONTROL Network and sites:]** このアカウントがコンテンツの再利用権限を要求できるネットワークまたはサイトです。 このアカウントをネットワーク全体で使用できるようにするには、リストの最初の項目を選択するか、Command/Ctrlキーを押して特定のサイトに制限します。
   * **[!UICONTROL Default message:]** 権限リクエストと共に表示するメッセージ。 権限を要求するときに、このメッセージを上書きできます。

      * モデレーターがコンテンツ作成者にリクエストを発行すると、Livefyreがモデレーターにデフォルトのメッセージの1つを表示します。 モデレーターは、別のデフォルトメッセージを生成したり、送信前にメッセージを編集したりできます。 メッセージには、発言者のTwitterハンドル({handle})、承認ハッシュタグ({grantTag})、利用条件へのリンク({termsLink})が含まれている必要があります。

         **[!UICONTROL Note:]** {handle}、{grantTag}、{termsLink}はすべて大文字と小文字が区別されます。

         **[!UICONTROL Note:]** 悪意のある使用を防ぐため、Twitterは含まれるURLを [t.co形式でラップします](https://t.co/) 。 デフォルトのメッセージが140文字を超えないように、デフォルトのメッセージにURLを含めないことをお勧めします。

      * 権利要求メッセージを書き込むためのベストプラクティス：

         * 複数の初期設定のメッセージを作成して、ロボットのように聞こえないようにします。 次のデフォルトメッセージを作成する前に、各デフォルトメッセージを保存します。
         * 送信する前にモデレーターにこのメモをパーソナライズしてもらい、ネットワークの要求がスパムとタグ付けされないようにします。

1. をクリック **[!UICONTROL Save Settings]** して、権限リクエストアカウントを追加します。
アセットライブラリから権限要求を送信します。 アセッ [トライブラリから権限要求を送信する方法について詳しくは、「権限要求の送信](../c-how-requesting-rights-works/t-send-a-rights-request-to-own-a-digital-asset.md#t_send_a_rights_request_to_own_a_digital_asset) 」を参照してください。