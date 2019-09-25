---
description: 'null'
seo-description: 'null'
seo-title: 不敬な言葉のフィルターの使用
solution: Experience Manager
title: 不敬な言葉のフィルターの使用
uuid: b0b1fbae-c88c-403c-9b91-df6620675f39
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 不敬な言葉のフィルターの使用{#using-the-profanity-filter}

Livefyreアプリに投稿されたすべてのコンテンツに不敬な言葉が含まれていないか確認されます。 不敬な言葉遣いのリストに含まれる単語がコンテンツまたはユーザーの表示名に含まれている場合、そのコンテンツに「不敬な態度」というフラグが付けられ、アプリコンテンツでのプリモデレート、ルール、ModQまたは一般検索をフィルターできます。

>[!NOTE]
>
>Studio管理者とマネージャーのコンテンツは、「不敬なルール」チェックの対象とはならず、モデレーターが投稿したコンテンツにはフラグが付きません。

Livefyreには、デフォルトの不敬な言葉のリストが用意されています。 このリストは、ネットワークレベルで適用するか、独自のリストを指定するか、またはこれら2つの集計を使用するかを選択できます。 ネットワーク内の個々のサイトは、ネットワークの不敬事項リストを継承するか、サイト固有にカスタマイズされたリストを使用する場合があります。

To provide your own custom profanity list as your network default, please send it to your Livefyre account manager.

## Enabling Profanity Filtering {#section_yqc_qsk_f1b}

Enable and configure the profanity filter at both the network and site level. Disable the profanity filter at the network level to automatically disable the profanity filter for all sites that inherit from the network.

>[!NOTE]
>
>All content passing through Livefyre is checked for profanity. If content is found which includes words contained on the default SAFE profanity list or in your custom Profanity list, it is flagged “Profanity.” To set Livefyre to automatically take action on these items, turn  to .**[!UICONTROL Enable Profanity Checking]****[!UICONTROL ON]**

## Enable the Profanity Filter for a Network {#section_twd_ssk_f1b}

1. Select  from the network pulldown menu.**[!UICONTROL Network]**
1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**.
1. Scroll down to the , and set  to .**[!UICONTROL Profanity List]****[!UICONTROL Enable Profanity Checking]****[!UICONTROL ON]**

1. Use the  field to add words to the list, or click a word to remove it from the list.**[!UICONTROL Update Network Profanity List]**

>[!NOTE]
>
>ネットワークレベルの不敬な言葉のリストを編集しても、既に設定されているサイトレベルのリストには影響しません。 To ensure that changes from the network are made to the site, select  for the site after the changes have been made.**[!UICONTROL Restore Network List]**

## Enable the Profanity Filter for a Site {#section_fld_wsk_f1b}

1. Select the site from the network pulldown menu.
1. 移動 **[!UICONTROL Settings > Site Settings > Moderation]**.
1. をスクロールし、を **[!UICONTROL Profanity List]** 設定し **[!UICONTROL Enable Profanity Checking]** ます **[!UICONTROL ON]**。

1. 次のいずれかのオプションを選択します。

   * ネットワークから不敬な言葉のリストを継承するには（一般的ではありません）、に設 **[!UICONTROL Use Site Profanity List]** 定しま **[!UICONTROL OFF]**&#x200B;す。

   * To edit the Profanity List specifically for the site, set  to  to open the  field, where you can edit the list:**[!UICONTROL Use Site Profanity List]****[!UICONTROL On]****[!UICONTROL Update Profanity List]**

      * 単語を削除するには、その単語をクリックします。
      * 単語を追加するには、ボックスに単語を入力し、 **[!UICONTROL Add new word]** ヒットしま **[!UICONTROL Return]**&#x200B;す。

      * 単語がリストに含まれているかどうかを確認するには、ボックスにその単語を入力 **[!UICONTROL Test profanity filter]** します。
   * ネットワークの不敬な言葉のリストを再度読み込んでサイトに適用するには、をクリックしま **[!UICONTROL Restore Network List]**&#x200B;す。
   * リストからすべてのコンテンツを消去し、最初から開始するには、をクリックしま **[!UICONTROL Clear List]**&#x200B;す。


## 不敬な言葉を含むコンテンツの操作 {#section_epy_dtk_f1b}

不敬な言葉のリストを使用して、コンテンツ検索のフィルタリングやModQのモデレート前のルールの作成に役立てます。

不敬な言葉を含むコンテンツを検索するには、に移動し、チェ **[!UICONTROL Library > App Content]**&#x200B;ックボ **[!UICONTROL Filter by Flags]** ックスをオンに **[!UICONTROL Profanity]** します。 選択したサイトまたはネットワークに対して不敬な言葉のフィルターによって取り込まれたコンテンツがすべて表示されます。 このリストには、SocialSyncとStreamsを使用してアプリに取り込まれたコンテンツが含まれます。

プリモデレートルールを作成するには、Studioからを選択しま **[!UICONTROL Settings > Network Settings > Moderation]**&#x200B;す。 不敬な言葉のフィルターが有効になると、新しいルールが表示され、不敬な言葉を含むコンテンツにフラグを付けたりモデレート前のコンテンツを設定したりできます。 デフォルトでは、このルールはプロファ **[!UICONTROL Premoderate]** イルコンテンツを自動的に有効にし、これをまたはに変更 **[!UICONTROL Trash it]** できま **[!UICONTROL Bozo it]**&#x200B;す。

>[!NOTE]
>
>1つのコンテンツに複数のルールタイプが適用される場合（SAFEルールとフラグルールの両方など）は、より厳密に適用されます。 例：プリモデレートルールで「コンテンツの一部をプレモデレート」と表示され、「セーフルール」で「ごみ箱」と表示される場合は、「トラッシュ」されます。

## ネットワークの不敬な言葉のリストの表示と更新 {#section_qdb_btk_f1b}

1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**.
1. セクションまで下にスクロ **[!UICONTROL Profanity List]** ールします。
1. Set  to  to display the List enabled for your network (Livefyre default, or your uploaded custom list) and edit it. **[!UICONTROL Enable Profanity Checking]****[!UICONTROL On]** You can edit the list in the following ways:
   * 単語を削除するには、その単語をクリックします。
   * 単語を追加するには、ボックスに単語を入力し、 **[!UICONTROL Add new word]** ヒットしま **[!UICONTROL Return]**&#x200B;す。
   * 単語がリストに含まれているかどうかを確認するには、ボックスにその単語を入力 **[!UICONTROL Test profanity filter]** します。

>[!NOTE]
>
>Studio管理者とモデレーターのみが、不敬な言葉のリストを編集できます。

