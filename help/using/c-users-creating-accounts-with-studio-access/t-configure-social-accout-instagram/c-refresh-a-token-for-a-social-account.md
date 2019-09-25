---
description: ソーシャルアカウントの有効期限が切れたら、そのトークンを更新します。
seo-description: ソーシャルアカウントの有効期限が切れたら、そのトークンを更新します。
seo-title: Socialアカウントのトークンの更新
solution: Experience Manager
title: Socialアカウントのトークンの更新
uuid: 8a25305c-aaa3-460f-b782-404a55b491cd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Socialアカウントのトークンの更新{#refresh-a-token-for-a-social-account}

ソーシャルアカウントの有効期限が切れたら、そのトークンを更新します。

Instagramトークンの有効期限は、ほとんど警告を出さないでも、何も警告を出さないでもかまいません。 次のソーシャルネットワークでは、トークンが使用されアクティブであることを確認するために、トークンを更新する必要があります。

* Twitter
* Instagram個人アカウント
* Instagramビジネスアカウント

Instagramのビジネスアカウントは、有効期限が切れるFacebookトークンを使用します。 トークンの有効期限が切れるまでに10日と5日が経過すると、Livefyreネットワークから通知されるので、トークンを更新できます。

トークンの有効期限が切れると、Livefyreは次の方法で通知します。

* Instagramのコンテンツを検索すると、左下に、Instagramトークンの有効期限が切れたことを示すウィンドウが表示されます。 他のInstagramアカウントを設定した場合、Livefyreはリスト内の次のInstagramアカウントを使用してInstagramを自動的に検索します。
* 期限切れの特定のInstagramアカウントを使用して権限を要求すると、エラーが表示されます。別のInstagramアカウントを選択するか、期限切れのアカウントのトークンを更新して、もう一度「要求権限」をクリックする必要があります。
* 期限切れのInstagramアカウントを使用するストリームは機能しません。
* &gt;で期限切れのトークンを持つア **[!UICONTROL Network Settings]** カウントに **[!UICONTROL Social Accounts]** は、エラー警告アイコン( ![](assets/warningError.png)

   と呼ばれていました）のリリース情報も含まれています。

//のアカウントの横にある「トークンを更新」をクリックして、トークンを **[!UICONTROL Network Settings]** 更新 **[!UICONTROL Social Accounts]** できま **[!UICONTROL Instagram Accounts]**&#x200B;す。
