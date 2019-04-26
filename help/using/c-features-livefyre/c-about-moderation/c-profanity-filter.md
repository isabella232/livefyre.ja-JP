---
description: null
seo-description: null
seo-title: 不敬フィルタの使用
solution: Experience Manager
title: 不敬フィルタの使用
uuid: b0b1fbae- c88c-403c-9b91- df6620675f39
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 不敬フィルタの使用{#using-the-profanity-filter}

Livefyreアプリケーションに投稿されたすべてのコンテンツに不敬の有無がチェックされます。違反のリストに含まれている単語がコンテンツまたはユーザーの表示名に含まれている場合、そのコンテンツには「浪費」というフラグが付けられ、事前モデレート、ルール、MOQまたはアプリのコンテンツの一般検索でフィルターできます。

>[!NOTE]
>
>Studio管理者およびマネージャーのコンテンツには違反ルールのチェックが適用されず、モデレーターによって投稿されたコンテンツはフラグ付けされません。

Livefyreにはデフォルトの浪費的なリストが用意されています。このリストをネットワークレベルで適用したり、独自のリストを提供したり、2つの集計を使用したりできます。ネットワーク内の個々のサイトはネットワーク違反リストを継承することも、サイト固有のリストを使用することもできます。

ネットワークデフォルトの独自の違反リストを提供するには、Livefyreアカウントマネージャーにお送りください。

## 悪意のあるフィルタリングの有効化 {#section_yqc_qsk_f1b}

ネットワークレベルとサイトレベルの両方で不当なフィルターを有効化および設定します。ネットワークレベルで違反フィルターを無効にすると、ネットワークから継承されるすべてのサイトに対して悪意のあるフィルターが自動的に無効になります。

>[!NOTE]
>
>Livefyre経由で渡されるコンテンツは、不敬のためにチェックされます。デフォルトの安全な不敬リストまたはカスタムの不敬リストに含まれている単語を含むコンテンツが見つかった場合、「浪費」フラグが付けられます。Livefyreを自動的にこれらの項目に対してアクションに設定するには **[!UICONTROL Enable Profanity Checking]** 、に移動 **[!UICONTROL ON]**します。

## ネットワークの悪意のあるフィルタの有効化 {#section_twd_ssk_f1b}

1. ネットワークのプルダウンメニュー **[!UICONTROL Network]** から選択します。
1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**先
1. 下 **[!UICONTROL Profanity List]**にスクロールして、に設定 **[!UICONTROL Enable Profanity Checking]****[!UICONTROL ON]**します。

1. フィールドを **[!UICONTROL Update Network Profanity List]** 使用してリストに単語を追加するか、または単語をクリックしてリストから削除します。

>[!NOTE]
>
>ネットワークレベルのアドホックリストを編集しても、既に配置されているサイトレベルのリストには影響しません。ネットワークからの変更を確実にサイトに反映させるには、変更が行われた後にサイト **[!UICONTROL Restore Network List]** を選択します。

## サイトの違反フィルターの有効化 {#section_fld_wsk_f1b}

1. ネットワークのプルダウンメニューからサイトを選択します。
1. 移動 **[!UICONTROL Settings > Site Settings > Moderation]**先
1. 下にスクロールして、 **[!UICONTROL Profanity List]****[!UICONTROL Enable Profanity Checking]** に設定 **[!UICONTROL ON]**します。

1. 次のいずれかのオプションを選択します。

   * ネットワークから不敬リストを継承するには（これは一般的ではありません）、に設定 **[!UICONTROL Use Site Profanity List]****[!UICONTROL OFF]**します。

   * サイト用に特別なリストを編集するには、目的のフィールドを開くように設定 **[!UICONTROL Use Site Profanity List]****[!UICONTROL On]** します。 **[!UICONTROL Update Profanity List]** ここで、リストを編集できます。

      * 単語を削除するには、その単語をクリックします。
      * 単語を追加するには **[!UICONTROL Add new word]** 、ボックスとヒットに単語を入力 **[!UICONTROL Return]**します。

      * 単語がリストに含まれているかどうかを確認するには、ボックスに **[!UICONTROL Test profanity filter]** 単語を入力します。
   * ネットワーク違反リストを再読み込みしてサイトに適用するには、をクリック **[!UICONTROL Restore Network List]**します。
   * リストからすべてのコンテンツを消去して最初から開始するには、をクリック **[!UICONTROL Clear List]**します。


## 不敬を含むコンテンツの操作 {#section_epy_dtk_f1b}

悪意のあるリストを使用して、コンテンツ検索をフィルタリングし、Modq用の事前モデレートルールを作成します。

不敬を含むコンテンツを検索するには、先 **[!UICONTROL Library > App Content]**に移動して **[!UICONTROL Filter by Flags]****[!UICONTROL Profanity]** チェックボックスをオンにします。選択したサイトまたはネットワークの不敬フィルターによってキャプチャされたすべてのコンテンツが表示されます。このリストには、SocialSyncとストリームを使用してアプリに取り込まれたコンテンツが含まれます。

事前モデレートルールを作成するには、Studioから選択 **[!UICONTROL Settings > Network Settings > Moderation]**します。違反フィルターが有効になると、新しいルールが表示され、フラグを付けたり、不敬を含むコンテンツを事前モデレートしたりできます。デフォルトでは、このルールはコンテンツを自動的に有効にし **[!UICONTROL Premoderate]** 、いずれかまた **[!UICONTROL Trash it]** は **[!UICONTROL Bozo it]**いずれかに変更できます。

>[!NOTE]
>
>単一のコンテンツの一部が、複数のルールタイプ（セーフルールやフラグルールの両方）の対象となる場合、より厳密に適用されます。次に例を示します。事前モデレートルールでコンテンツの一部を事前モデレートするように指示している場合、セーフルールではごみ箱が表示されます。

## ネットワークの不敬リストの表示と更新 {#section_qdb_btk_f1b}

1. 移動 **[!UICONTROL Settings > Network Settings > Moderation]**先
1. **[!UICONTROL Profanity List]** 下にスクロールします。
1. **[!UICONTROL Enable Profanity Checking]** ネットワーク **[!UICONTROL On]** に対して有効になっているList（Livefyreデフォルトまたはアップロードしたカスタムリスト）を表示し、編集するには、に設定します。リストは次の方法で編集できます。
   * 単語を削除するには、その単語をクリックします。
   * 単語を追加するには **[!UICONTROL Add new word]** 、ボックスとヒットに単語を入力 **[!UICONTROL Return]**します。
   * 単語がリストに含まれているかどうかを確認するには、ボックスに **[!UICONTROL Test profanity filter]** 単語を入力します。

>[!NOTE]
>
>Studio管理者およびモデレーターのみが、不敬リストを編集できます。

