---
description: ソーシャルアカウントの有効期限が切れたら、トークンを更新します。
seo-description: ソーシャルアカウントの有効期限が切れたら、トークンを更新します。
seo-title: Socialアカウントのトークンの更新
solution: Experience Manager
title: Socialアカウントのトークンの更新
uuid: 8a25305c-aaa3-460f-b782-404a55b491cd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---


# ソーシャルアカウントのトークンの更新{#refresh-a-token-for-a-social-account}

ソーシャルアカウントの有効期限が切れたら、トークンを更新します。

Instagramトークンの有効期限が切れる場合があります。たいていの場合、警告はほとんど表示されませんが、何も表示されません。 次のソーシャルネットワークでは、トークンが使用されアクティブであることを確認するために、トークンを更新する必要があります。

* Twitter
* Instagram個人アカウント
* Instagramのビジネスアカウント

Instagramのビジネスアカウントは、有効期限が切れるFacebookトークンを使用します。 トークンの有効期限が切れる10日と5日が経過すると、Livefyreネットワークから通知されるので、トークンを更新できます。

トークンの有効期限が切れると、次の方法で通知されます。

* Instagramのコンテンツを検索すると、Instagramのトークンの有効期限が切れたことを示すウィンドウが左下に表示されます。 他のInstagramアカウントを設定した場合、Livefyreはリストー内の次のInstagramアカウントを使用してInstagramを自動的に検索します。
* 有効期限が切れた特定のInstagramアカウントを使用して権限を要求すると、エラーが表示されます。別のInstagramアカウントを選択するか、期限切れのアカウントのトークンを更新して、もう一度「要求権限」をクリックする必要があります。
* 期限切れのInstagramアカウントを使用するストリームは機能しません。
* 期限切れのトークンが&#x200B;**[!UICONTROL Network Settings]** > **[!UICONTROL Social Accounts]**&#x200B;にあるアカウントには、エラー警告アイコン( ![](assets/warningError.png)

   と呼ばれていました）のリリース情報も含まれています。

**[!UICONTROL Network Settings]**/**[!UICONTROL Social Accounts]**/**[!UICONTROL Instagram Accounts]**&#x200B;で、アカウントの横にある「トークンを更新」をクリックして、トークンを更新できます。
