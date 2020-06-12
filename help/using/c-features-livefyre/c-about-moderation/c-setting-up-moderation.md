---
description: 「モデレート」タブを使用して、不敬なリスト、フラグルール、禁止されたIPアドレスなど、受信コンテンツに対するプリモデレートルールを設定します。
seo-description: 「モデレート」タブを使用して、不敬なリスト、フラグルール、禁止されたIPアドレスなど、受信コンテンツに対するプリモデレートルールを設定します。
seo-title: モデレートの設定
solution: Experience Manager
title: モデレートの設定
uuid: 0ec53fdb-08c2-4058-88cb-2f6f4b56a95b
translation-type: tm+mt
source-git-commit: 52f59cd15f315aa93be198f6eb586f008c18a384
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 0%

---


# モデレートの設定{#setting-up-moderation}

「モデレート」タブを使用して、不敬なリスト、フラグルール、禁止されたIPアドレスなど、受信コンテンツに対するプリモデレートルールを設定します。

## モデレートの仕組み {#section_kyf_gvc_t1b}

コンテンツのモデレートは次の方法で行うことができます。

* コンテンツを自動的にプレモデレートし、コンテンツを公開する前に設定したルールに基づいて、不要なコンテンツをフィルターアウトします。
* ライブラリのModQまたはApp Contentを使用した自動プリモデレートを使用してフラグ付けされたコンテンツを手動で削除または承認します。
* 特定のLivefyre訪問者、ソーシャルユーザーまたはIPアドレスを禁止して、攻撃的なコンテンツを繰り返し投稿して投稿から防ぐサイトユーザーを特定します。
* ユーザーを許可リストに登録したり、特定のストリーム、サイト、またはネットワークのフィルターをオフにしたりして、常に表示できる人やコンテンツを識別します。

コンテンツは、次の方法で自動的にプレモデレートできます。

* 特定のタイプのコンテンツに自動的にフラグを付けるルールを設定します。

   * サイト訪問者フラグによってフラグ付けされるコンテンツのフラグルールを設定します。 **[!UICONTROL Settings > Moderation > Rules]**
   * SAFEルールの設定に使用する **[!UICONTROL Settings > Moderation > Rules]**
   * 特定のTwitterユーザーを **[!UICONTROL Settings > Streams]**
   * 次を使用してIPアドレスを禁止する **[!UICONTROL Settings > Bans]**
   * 要求に応じて、国コード別のIP地域を禁止します。 禁止されたコンテンツはスパムとしてマークされます。

* ネットワークまたはサイトの下の不敬な言葉遣いのリストで不敬虔と思われる言葉のリスト **[!UICONTROL Settings > Moderation > Rules]** を作成します。
* 特定のストリーム、サイトまたはネットワークのリストを使用またはオフにすることで、フィルターを許可するユーザー（常にこれらのユーザーのコンテンツの表示を許可する）。

不敬なリスト、安全なフィルター、ルールを設定したら、コンテンツをプレモデレートして、安全なフィルターをストリームに適用するかどうかを選択できます。 詳しくは、「すべてのストリームルールの [ストリームルールオプション](/help/using/c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)」を参照してください。

Livefyreは、コンテンツを **[!UICONTROL Approved]**、 **[!UICONTROL Pending]**、 **[!UICONTROL Junk]**&#x200B;など コンテンツの提供元、公開先、およびシステムで設定したルールに応じて異なります。 次の表に、Livefyreが行うアクション（これらの要因に応じた）を詳しく示します。

## モデレートの仕組み

| コンテンツの提供元： | コンテンツの送信先： | 承認ステータス |
|--- |--- |--- |
| ライブラリ | アプリ | 承認されたコンテンツ |
| ソーシャル検索 | アプリ | 承認されたコンテンツ |
| ストリームルール | アプリ | コンテンツは安全なフィルターで迷惑メールとしてマークされていますか？ <br><ul><li>いいえ — ストリームからアプリへのモデレートワークフロー</li><li>はい — コンテンツがトラッシュされました</li></ul> |
| ライブラリ | フォルダー | ステータスなし（フォルダ内、未発行、トラッシュなし） |
| ソーシャル検索 | フォルダー | ステータスなし（フォルダ内、未発行、トラッシュなし） |
| ストリームルール | フォルダー | コンテンツは安全なフィルターで迷惑メールとしてマークされていますか？ <br><ul><li>いいえ — ステータスなし（フォルダ内、未発行、トラッシュなし）</li><li>はい — コンテンツがトラッシュされました</li></ul> |
| アプリ投稿 | アプリ | コンテンツは安全なフィルターで迷惑メールとしてマークされていますか？ <br><ul><li>いいえ — アプリへの投稿のモデレートワークフロー</li><li>はい — コンテンツがトラッシュされました</li></ul> |

## ストリームからアプリへのモデレートワークフロー {#section_z5z_w4d_t1b}

![](assets/stream_to_app_workflow.png)

ストリームのコンテンツがアプリに公開される前に、Livefyreは次のチェックを実行してコンテンツの処理方法を決定します。

1. SAFEがコンテンツに迷惑メールまたはドロップというフラグを付けた場合、Livefyreはコンテンツをトラッシュします。
1. SAFEがコンテンツに迷惑メールのフラグを付けない場合、Livefyreはプリモデレートがオンになっているかどうかを確認します。
1. プリモデレートがオンの場合、Livefyreはコンテンツを保留としてマークします。
1. ModQルールを設定すると、LivefyreはコンテンツをModQに送信します。
1. プリモデレートがオンになっていない場合、LivefyreはSAFEによってコンテンツにフラグが付いているかどうかを確認します。
1. SAFEがコンテンツにフラグを付けた場合、Livefyreはコンテンツを承認し、コンテンツをアプリに公開します。
1. SAFEがコンテンツにフラグを付け、SAFEルールを設定しなかった場合、Livefyreはコンテンツを承認し、アプリにコンテンツを公開します。
1. SAFEがコンテンツにフラグを付け、SAFEルールを設定した場合、LivefyreはストリームにSAFEルールを設定しているかどうかを確認します。
1. ストリームに対してSAFEルールを設定すると、Livefyreがコンテンツを承認し、アプリにコンテンツを公開します。 ストリームにSAFEルールを設定しなかった場合、LivefyreはモデレートSAFEルールを使用して、コンテンツの処理方法（ModQやごみ箱などに送信）を決定します。

## アプリへの投稿のモデレートワークフロー {#section_fwn_w4d_t1b}

![](assets/post_to_app_workflow.png)

アプリの投稿のコンテンツがアプリに公開される前に、Livefyreは次のチェックを実行してコンテンツの処理方法を決定します。

1. SAFEフィルターでコンテンツにフラグが付いてドロップされると、Livefyreはコンテンツをドロップします。
1. SAFEがコンテンツにドロップフラグを付けない場合、Livefyreはプリモデレートがオンになっているかどうかを確認します。 プリモデレートがオンの場合、Livefyreはコンテンツを保留としてマークします。 ModQルールを設定した場合、LivefyreはコンテンツをModQに保留中として送信します。 そうでない場合、コンテンツはライブラリの「アプリコンテンツ」で保留ステータスのままです。
1. プリモデレートがオンになっていない場合、LivefyreはSAFEによってコンテンツにフラグが付いているかどうかを確認します。 そうでない場合、Livefyreはコンテンツを承認し、アプリにコンテンツを公開します。
1. SAFEがコンテンツにフラグを付け、SAFEルールを設定した場合、LivefyreはSAFEルールを使用してコンテンツの処理方法（ModQやごみ箱などに送信）を決定します。 SAFEがコンテンツにフラグを付け、SAFEルールを設定しなかった場合、Livefyreはコンテンツを承認し、アプリにコンテンツを公開します。

## バルクフィルター {#section_lyk_ktx_vy}

バルクフィルターは、短い期間内にすべてのLivefyreネットワークに投稿された繰り返しコンテンツを探します。 検出された場合、このコンテンツは一括としてフラグ付けされ、デフォルトでトラッシュされます。 バルクコンテンツはユーザー生成が可能です（「Touchdown!」など） 人気のサッカーゲーム中にチャットで繰り返し投稿される)、ほとんどはスパムキャンペーンに由来する。 このフィルターは言語に依存せず、任意の言語で機能します。 バルクフィルターをカスタマイズするには、Livefyreサポートにお問い合わせください。

## ルール {#section_gqz_ksk_f1b}

「ルール」セクションを使用して、SAFEおよびユーザーが適用したフラグに基づいてモデレート前のルールを作成します。 このパネルには、2種類のルールがオファーされます。

* **[!UICONTROL Flag Rules:]** ユーザーがフラグを付けたコメントに対して行う必要のあるアクションを、定義された回数だけ指定します。
* **[!UICONTROL SAFE Rules:]**SAFEフラグとアクションを組み合わせて、フラグ付けされたコンテンツを取ります。

フラグルールを作成するには、フラグ（不快、オフトピック、同意しない、スパム）を選択し、コンテンツの一部に適用する必要のある回数を入力し、実行するアクションを選択します。 フラグのオプション（不快、オフトピック、同意しない、スパム）ごとに1つのフラグの規則を設定できます。

ルールは、ネットワーク、サイト、ストリームの各レベルで作成できます。 サイトレベルのルールは、サイトのルールを異なる方法で構成しない限り、ネットワークルールを継承します。 ストリームルールは、異なる構成を行わない限り、サイトルールを継承します。

使用可能なアクション：

* **[!UICONTROL Trash it:]**フラグ付きのコメントをごみ箱に送ります。
* **[!UICONTROL Bozo it:]** フラグ付きのコメントを、ライターを除くすべてのユーザーから非表示にします。このユーザーに対して、フラグ付きのコメントは表示されたままになります。
* **[!UICONTROL Pending:]** コンテンツを保留に設定します。 PremoderationをONに設定した場合 **[!UICONTROL Settings > ModQ]**&#x200B;は、ModQに含まれます。 それ以外の場合は、アプリのコンテンツのみに表示されます。

>[!NOTE]
>
>Livefyreは、5人のユーザーによってスパムまたは攻撃としてフラグ付けされたBozoコメントにルールを作成することをお勧めします。

## モデレートの推奨 {#section_ec3_vr3_2cb}

You can use moderation recommendations to help you determine how to moderate content posted by site visitors in Livefyre Apps. モデレートの推奨インジケーターでは、コンテンツの一部がトラッシュされる可能性が高い場合に、以前に類似のコンテンツに対して行った操作に基づいて、レコメンデーションを推奨します。 To use Moderation Recommendations:

1. Turn on the Moderation Recommendations functionality by contacting your Adobe Livefyre support professional.
1. Set up moderation recommendations in Network Settings.

   Set up moderation recommendations using the **[!UICONTROL Livefyre Recommends Trash]** setting under **[!UICONTROL Network Settings]**.

   ![](assets/image_mod_reco_trash.png)

1. Set up a SAFE rule to tell Livefyre what to do with content that the moderation recommendation identifies as content that is likely to be trashed. For more information on how to set up a SAFE rule for the **[!UICONTROL Livefyre Recommends Trash]** option, see [Moderation](/help/using/c-features-livefyre/c-about-moderation/c-moderation.md#c_moderation).

   ![](assets/modreco4.png)

1. Use the **[!UICONTROL Moderation Recommendation Indicator]** in the ModQ or in App Content to filter content that the moderation recommendation identifies as likely to be trashed.

   In ModQ, the indicator looks like this:  ![](assets/mod_reco1.png)

   For more information on how to use Moderation Recommendations to moderate content in ModQ, see [ModQ](/help/using/c-features-livefyre/c-about-moderation/c-modq.md#c_modq).

   In App Content, moderation recommendations look like this:  ![](assets/modreco3.png)

   For more information on how to use Moderation Recommendations in App Content, see [Moderate Content Using App Content](/help/using/c-features-livefyre/c-about-moderation/c-moderate-content-using-app-content.md#c_moderate_content_using_app_content).
