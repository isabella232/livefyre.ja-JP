---
description: Livefyreでプライバシーリクエストを作成します。
seo-description: Livefyreでプライバシーリクエストを作成します。
seo-title: プライバシーリクエストの作成
title: プライバシーリクエストの作成
uuid: 9fdbd564-0cea-4e4f-bdea-d5b8744fe63a
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# Create a Privacy Request{#create-a-privacy-request}

Livefyreでプライバシーリクエストを作成します。

ユーザーのすべてのデータを削除し、ユーザーのすべてのデータのレポートを生成し、このプロセスを使用してオプトインまたはオプトアウトの変更を行います。

ユーザーを検索し、そのコンテンツのレポートを生成するには：

1. に移動し、 **[!UICONTROL Settings > Privacy]**&#x200B;をクリックしま **[!UICONTROL Create Request]**&#x200B;す。

   ![](assets/privacypage1.png)

1. ウィンドウの情報を入力し **[!UICONTROL Submit Request]** ます。

   * **[!UICONTROL Reference Id]**. 将来の参照に使用する識別子を入力します。 例えば、テキスト、チケット番号、URL、電子メールアドレス、または255文字までのその他の文字列を追加できます
   * **[!UICONTROL Type]**

      * **アクセス**. アカウントに関連付けられた使用可能なすべてのデータを収集します。 パスワードやソーシャル秘密鍵証明書など、機密性の高い詳細は不明化または省略されます。

      * **Delete**. アカウントに関連付けられているすべてのデータを有名にするか、不明化します。 **このオプションを選択して「送信」をクリックした場合、この操作を元に戻したり取り消したりするこ&#x200B;*とはできません。また、削除したデータを元に戻すこともできません。*** アカウントがLivefyre studioユーザーに属している場合、ビジネスレコードの整合性を維持するために一部のデータが保持されます。

         >[!IMPORTANT]
         >
         >アカウントのデータを削除すると、そのアカウントに関連付けられたデータが完全に削除または破棄されます。 この操作を元に戻すことはできません。また、削除後にデータを元に戻すこともできません。

      * **オプトアウト**。 LivefyreがStreamsやソーシャル検索を使用してソーシャルアカウントから受動的にデータやコンテンツを収集するのを防ぎます。 オプトインとオプトアウトは登録ユーザーには適用されません
      * **オプトイン**。 以前にStreamsまたはSocial検索でオプトアウトしたソーシャルアカウントから、Livefyreが受動的にデータまたはコンテンツを収集できるようにします。 オプトインとオプトアウトは登録ユーザーには適用されません
      ![](assets/privacypage2.png)

   * **[!UICONTROL Identifier Type]** および **[!UICONTROL Identifier]**

      * **[!UICONTROL User Account]**

         * User Management systemまたはLivefyreのStudioユーザーIDによって生成されたユーザーアカウントIDで、登録済みユーザーのアカウントを識別します。 また、 **Livefyre** User Settingsの「ユーザーの詳細」、またはアセットライブラリやアプリコンテンツのコンテンツの詳細で **********、ユーザーアカウントIDを見つけることもできます**

         * 許可されている値：255文字までの英数字の文字列。 電子メールアドレスが有効な入力ではありません
      * **[!UICONTROL Facebook User]**

         * Facebookから提供される数値IDでアカウントを識別します。 要求者はこれを提供する必要があります。 数値のFacebook IDの検索方法については、こちらを参照してくださ [い。](https://www.facebook.com/help/1397933243846983?helpref=faq_content)
         * 許可されている値：6 ～ 16文字の数値
      * **[!UICONTROL Instagram User]**

         * Instagramが提供する数値IDでアカウントを識別します。 要求者はこれを提供する必要があります。 Instagramアカウントで数値のInstagram IDを検索する方法については、オンラインで検索して説明します
         * 許可されている値：5 ～ 16文字の数値
      * **[!UICONTROL Twitter User]**

         * Twitterから提供される数値IDでアカウントを識別します。 プライバシーの変更を要求する担当者が、この情報を提供する必要があります。 オンライン検索を使用して、Twitterアカウントの数字のTwitter IDを探す方法について説明します
         * 許可されている値：5 ～ 16文字の数値
      * **[!UICONTROL YouTube User]**

         * YouTubeから提供された数値IDでアカウントを識別します。 プライバシーの変更を要求する担当者が、この情報を提供する必要があります。 YouTubeアカウントでの数値のYouTube IDの検索方法については、こちらを参照してくだ [さい](https://support.google.com/youtube/answer/3250431?hl=en)
         * 許可されている値：5 ～ 16文字の数値
      * **[!UICONTROL Generic Author]**

         * Livefyre作成者ID(JID)でアカウントを識別します。 このオプションは、RSS、TumblrまたはURLを使用してコンテンツをソースとする場合に使用します。 このIDを探すには、「アプリコンテンツ」または「アセットライブラリ」で作成者 **に属するコンテ** ンツを検索し ****、アイテムを選択します。 このIDは、「 **App Content** 」の「Info **」または「** Asset Library **」の「Author」の「Details」の「Details」の「** Details」の「App Content」の「 ******** Author」の「Details」の「Details」の各セクションで使用できます。

         * 許可されている値：255文字までの英数字の文字列
         ![](assets/privacypage3.png)








1. Click **[!UICONTROL Finish]**.

   ![](assets/privacypage4.png)

1. （削除リクエストの場合のみ）そのユーザーのすべての情報を削除することを確認します。

   >[!IMPORTANT]
   >
   >アカウントのデータを削除すると、そのアカウントに関連付けられたデータが完全に削除または破棄されます。 この操作を元に戻すことはできません。また、削除後にデータを元に戻すこともできません。

