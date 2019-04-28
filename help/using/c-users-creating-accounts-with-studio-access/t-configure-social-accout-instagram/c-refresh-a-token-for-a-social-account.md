---
description: ソーシャルアカウントのトークンが期限切れになったときに更新します。
seo-description: ソーシャルアカウントのトークンが期限切れになったときに更新します。
seo-title: Socialアカウント用のトークンの更新
solution: Experience Manager
title: Socialアカウント用のトークンの更新
uuid: 8a25305c- aaa3-460f- b782-404a55b491cd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Socialアカウント用のトークンの更新{#refresh-a-token-for-a-social-account}

ソーシャルアカウントのトークンが期限切れになったときに更新します。

Instagramトークンは期限切れになることがあります。多くの場合、警告はほとんどまたはまったくありません。以下のソーシャルネットワークでは、トークンを更新して、それらが使用されているかどうかを確認する必要があります。

* Twitter
* Instagram個人アカウント
* Instagramビジネスアカウント

Instagramのビジネスアカウントでは、有効期限が切れるFacebookトークンが使用されます。トークンの期限が切れる前に10日と5日経過すると、Livefyreネットワークが自動的に通知され、更新できます。

トークンの有効期限が切れると、Livefyreに次の方法で通知されます。

* Instagramコンテンツを検索すると、Instagramトークンが期限切れになったことを示すウィンドウが左下に表示されます。他のInstagramアカウントを設定した場合、Livefyreはリスト内の次のInstagramアカウントを使用してInstagramを自動的に検索します。
* 特定の期限切れのInstagramアカウントを使用して権限をリクエストする場合、エラーが表示されます。別のInstagramアカウントを選択するか、期限切れのアカウントのトークンを更新して、再度リクエストをクリックする必要があります。
* 期限切れのInstagramアカウントを使用してストリームが機能しない。
* 有効期限切れのトークンが含まれているアカウント **[!UICONTROL Network Settings]** &gt; **[!UICONTROL Social Accounts]** エラー警告アイコン（ ![](assets/warningError.png)

   ).

トークンを更新するには **[!UICONTROL Network Settings]**、/ **[!UICONTROL Social Accounts]** &gt;のアカウントの横にある「更新トークン」をクリック **[!UICONTROL Instagram Accounts]** します。
