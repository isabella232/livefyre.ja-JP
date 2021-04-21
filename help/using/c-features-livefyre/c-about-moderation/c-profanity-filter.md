---
title: 不敬な言葉のフィルターの使用
description: 不敬な言葉のフィルターの使用
exl-id: 6ea7d913-f562-42a5-a6ea-241aa4e1089a
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 0%

---

# 不敬な言葉のフィルターの使用{#using-the-profanity-filter}

Livefyreアプリに投稿されたすべてのコンテンツに不敬の内容がないかどうかがチェックされます。 不敬なリストに含まれる単語がコンテンツまたはユーザーの表示名で見つかった場合、そのコンテンツには「不敬」というフラグが付けられ、プリモデレート、ルール、ModQまたはアプリコンテンツの一般検索用にフィルターできます。

>[!NOTE]
>
>Studio管理者とマネージャーのコンテンツは、「不敬虔なルール」チェックの対象外であり、モデレーターが投稿したコンテンツにはフラグが付きません。

Livefyreには、デフォルトの不敬な言葉のリストがあります。 このリストをネットワークレベルで適用するか、独自のリストを提供するか、またはこれら2つの集計を使用するかを選択できます。 ネットワーク内の個々のサイトがネットワークの不敬のリストを継承するか、サイトに固有にカスタマイズされたリストを使用する場合があります。

独自の不敬なリストをネットワークのデフォルトとして提供するには、Livefyreアカウントマネージャーにお送りください。

## 不敬なフィルタリングを有効にする{#section_yqc_qsk_f1b}

ネットワークレベルとサイトレベルの両方で不敬虔性フィルターを有効にして設定します。 ネットワークレベルで不敬虔性フィルターを無効にして、ネットワークから継承するすべてのサイトの不敬虔性フィルターを自動的に無効にします。

>[!NOTE]
>
>Livefyreを通過するすべてのコンテンツに不敬の内容がないかどうかがチェックされます。 デフォルトの不敬のリストまたはカスタムの不敬のリストに含まれる単語を含むコンテンツが見つかった場合、「不敬」というフラグが付けられます。 これらの項目に対して自動的にアクションを実行するようにLivefyreを設定するには、**[!UICONTROL Enable Profanity Checking]**&#x200B;を&#x200B;**[!UICONTROL ON]**&#x200B;に設定します。

## ネットワークに対して不敬な言葉のフィルターを有効にする{#section_twd_ssk_f1b}

1. ネットワークのプルダウンメニューから&#x200B;**[!UICONTROL Network]**&#x200B;を選択します。
1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**.
1. **[!UICONTROL Profanity List]**&#x200B;まで下にスクロールし、**[!UICONTROL Enable Profanity Checking]**&#x200B;を&#x200B;**[!UICONTROL ON]**&#x200B;に設定します。

1. **[!UICONTROL Update Network Profanity List]**&#x200B;フィールドを使用してリストに単語を追加するか、単語をクリックしてリストから削除します。

>[!NOTE]
>
>ネットワークレベルの不敬のリストを編集しても、既に設定されているサイトレベルのリストには影響しません。 ネットワークからサイトに変更が行われるようにするには、変更が行われた後でサイトに対して&#x200B;**[!UICONTROL Restore Network List]**&#x200B;を選択します。

## サイトに対して不敬な言葉のフィルターを有効にする{#section_fld_wsk_f1b}

1. ネットワークのプルダウンメニューからサイトを選択します。
1. 移動 **[!UICONTROL Settings > Site Settings > Moderation]**.
1. **[!UICONTROL Profanity List]**&#x200B;まで下にスクロールし、**[!UICONTROL Enable Profanity Checking]**&#x200B;を&#x200B;**[!UICONTROL ON]**&#x200B;に設定します。

1. 次のいずれかのオプションを選択します。

   * ネットワークから不敬なリストを継承するには（一般的ではありません）、**[!UICONTROL Use Site Profanity List]**&#x200B;を&#x200B;**[!UICONTROL OFF]**&#x200B;に設定します。

   * サイト専用の不敬リストを編集するには、**[!UICONTROL Use Site Profanity List]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に設定して&#x200B;**[!UICONTROL Update Profanity List]**&#x200B;フィールドを開き、リストを編集できます。

      * 単語を削除するには、その単語をクリックします。
      * 単語を追加するには、**[!UICONTROL Add new word]**&#x200B;ボックスに単語を入力し、**[!UICONTROL Return]**&#x200B;を押します。

      * リストに単語が含まれているかどうかを確認するには、**[!UICONTROL Test profanity filter]**&#x200B;ボックスに単語を入力します。
   * ネットワークの不敬リストを再度読み込んでサイトに適用するには、**[!UICONTROL Restore Network List]**&#x200B;をクリックします。
   * リストーと開始ーのすべてのコンテンツを最初から消去するには、**[!UICONTROL Clear List]**&#x200B;をクリックします。


## 不敬を含むコンテンツの操作{#section_epy_dtk_f1b}

コンテンツの検索をフィルタリングし、ModQのプリモデレートルールを作成する際に、敬虔なリストを使用します。

不敬な言葉を含むコンテンツを検索するには、**[!UICONTROL Library > App Content]**, **[!UICONTROL Filter by Flags]**&#x200B;に移動し、**[!UICONTROL Profanity]**&#x200B;チェックボックスをオンにします。 選択したサイトまたはネットワークの不敬なフィルターによってキャッチされたコンテンツはすべて表示されます。 このリストには、SocialSyncとStreamsを使用してアプリに取り込まれたコンテンツが含まれます。

プリモデレートルールを作成するには、Studioで&#x200B;**[!UICONTROL Settings > Network Settings > Moderation]**&#x200B;を選択します。 不敬な言葉のフィルターが有効になると、新しいルールが表示され、不敬な言葉を含むコンテンツにフラグを付けたりモデレート前に設定したりできます。 デフォルトでは、このルールによりプロファイルコンテンツの&#x200B;**[!UICONTROL Premoderate]**&#x200B;が自動的に有効になります。**[!UICONTROL Trash it]**&#x200B;または&#x200B;**[!UICONTROL Bozo it]**&#x200B;に変更できます。

>[!NOTE]
>
>1つのコンテンツに複数のルールタイプが適用される場合（SAFEルールとフラグルールの両方）、より厳しい内容が適用されます。 次に例を示します。プリモデレートルールで、コンテンツの一部をプリモデレートと記述され、セーフルールではコンテンツをごみ箱に入れるとトラッシュされます。

## ネットワークの不敬なリストの表示と更新{#section_qdb_btk_f1b}

1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**.
1. **[!UICONTROL Profanity List]**&#x200B;セクションまで下にスクロールします。
1. **[!UICONTROL Enable Profanity Checking]**&#x200B;を&#x200B;**[!UICONTROL On]**&#x200B;に設定して、ネットワークで有効になっているリスト(Livefyreの初期設定、またはアップロードしたカスタムリスト)を表示し、編集します。 リストは、次の方法で編集できます。
   * 単語を削除するには、その単語をクリックします。
   * 単語を追加するには、**[!UICONTROL Add new word]**&#x200B;ボックスに単語を入力し、**[!UICONTROL Return]**&#x200B;を押します。
   * リストに単語が含まれているかどうかを確認するには、**[!UICONTROL Test profanity filter]**&#x200B;ボックスに単語を入力します。

>[!NOTE]
>
>Studio管理者とモデレーターのみが、不敬なリストを編集できます。
