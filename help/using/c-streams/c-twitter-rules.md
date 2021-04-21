---
description: twitterからコンテンツを取り込むストリームルールを作成できます。
title: Twitterルール
exl-id: 3a5081eb-048d-4dcf-80a2-366af2cb2c86
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---

# Twitterルール{#twitter-rules}

twitterからコンテンツを取り込むストリームルールを作成できます。

ハッシュタグ、キーワード、@メンションまたは発言者に基づいて、Twitterルールを作成します。

ルールに&#x200B;**[!UICONTROL Words]**&#x200B;と&#x200B;**[!UICONTROL Username]**&#x200B;を追加すると、両方のエントリを含む内容が返されます。

>[!NOTE]
>
>LivefyreはTwitterの表示ガイドラインに従っており、お客様はこれらのガイドラインを遵守する責任も負います。 詳しくは、Twitterの[ディスプレイ要件](https://dev.twitter.com/terms/display-requirements)に関するドキュメントを参照してください。

twitterフィードからコンテンツをアプリまたはフォルダーに取り込むためのTwitterルールを作成するには、次のフィルターを使用できます。

* **[!UICONTROL Keywords]**
   * **[!UICONTROL Keywords]**&#x200B;を入力して、Twitterストリームに含めるか、除外します。 **[!UICONTROL Contains any of these words]**&#x200B;フィールドと&#x200B;**[!UICONTROL Does not contain any of these words]**&#x200B;フィールドの両方に値を指定すると、最初の値を含み、2番目の値を含まないツイートが返されます。 1つのフィールドに複数の値を入力でき、任意の値を含む結果が返されます。 ブール演算子ANDを使用して、2つ以上の単語を含むツイートを検索するには、2つのアンパサンド(*&amp;*)を使用して2つの単語を区切ります。
   * 例えば、**[!UICONTROL Contains any of these words]**&#x200B;キーワードGiants、Posey、**[!UICONTROL Does not contain any of these words]**&#x200B;キーワードDodgerを入力すると、*Giants*&#x200B;または&#x200B;*Posey*&#x200B;を含み、*Dodger*という語を含まないツイートがすべて返されます。
*Giants*&#x200B;と&#x200B;*Posey*&#x200B;の両方の単語を含むツイートを検索するには、&quot;Giants &amp;&amp; Posey&quot;と入力します。 この機能は、Twitterルールの&#x200B;**[!UICONTROL Contains any of these words]**&#x200B;フィールドと&#x200B;**[!UICONTROL Does not contain any of these words]**&#x200B;フィールドに対してのみサポートされます。

* **[!UICONTROL Hashtags]** を参照してください。
   * **[!UICONTROL Hashtags]**&#x200B;を入力して、Twitterストリームに含めるか、除外します。 **[!UICONTROL Contains any of these words]**&#x200B;フィールドと&#x200B;**[!UICONTROL Does not contain any of these words]**&#x200B;フィールドの両方に値を指定すると、最初のフィールドにハッシュタグを含み、2番目のフィールドにハッシュタグを含まないツイートが返されます。 1つのフィールドに複数の値を入力できます。 ストリームは、任意の値を含む結果を返します。

* **[!UICONTROL Usernames]**
   * **[!UICONTROL @mentions]**&#x200B;または&#x200B;**[!UICONTROL authors]**&#x200B;を入力して、ストリームに取り込むか、ストリームから除外します。 選択した作成者の&#x200B;**[!UICONTROL Retweets]**&#x200B;と&#x200B;**[!UICONTROL replies]**&#x200B;のどちらを含めるかは、チェックボックスを使用して定義します。

   >[!NOTE]
   >
   >発言者を含めたり除外したりできます。これらの2つのフィールドを1つのTwitterルールに結合することはできません。

* **[!UICONTROL Minimum number of followers.]** ユーザーが投稿から情報を取り込む必要がある最小限のフォロワー数を選択します。
* **[!UICONTROL Location]**

   * 場所(市、郵便番号、住所、または地域コードを、共通の緯度/経度形式(+/- 90、+/- 180)で入力します)。 場所を入力し始めると、ドロップダウンメニューが表示され、提案が表示されます。 ドロップダウンから場所を選択します。 マップにその位置のピンが表示されます。 スライダを調整して、各位置の半径を1マイルから25マイルに選択します。 半径を選択しない場合、Livefyreは自動的に8マイルのデフォルトを選択します。
   >[!NOTE]
   >
   >両方のフィールドについて、入力位置の中心から距離が計算されます。

   * 複数の位置と半径を追加できます。 場所を削除するには、ボックスで場所の名前の横のXをクリックします。
   * **[!UICONTROL Is near this location]**&#x200B;と&#x200B;**[!UICONTROL Is not near this location]**&#x200B;フィールドを組み合わせて、**[!UICONTROL Is near this location]**&#x200B;フィールド内の場所内のコンテンツを取り込み、**[!UICONTROL Is not near this location]**&#x200B;フィールド内の場所の近くには入れません。


* **[!UICONTROL Additional Filters]**
   * 「追加のフィルター」を使用して、Twitterルールをさらに絞り込みます。 次のいずれを行うかを定義します。
      * ターゲット設定したツイートに&#x200B;**[!UICONTROL Replies]**&#x200B;を含めます（ストリームの速度が速くなると、この機能は自動的に無効になります）。
      * **[!UICONTROL Verified Twitter accounts only.]**&#x200B;からのツイートを含める
      * **[!UICONTROL All Content]**、**[!UICONTROL Vines Only]**、または&#x200B;**[!UICONTROL Images Only.]**&#x200B;を含めます。
      * 選択した&#x200B;**[!UICONTROL Minimum number of followers]**&#x200B;を持つアカウント（任意、100、500、1000、10,000または100,000）から派生するツイートのみを含めます。

すべてのストリームルールに対する追加のストリームルールオプションについては、[すべてのストリームルールのストリームルールオプション](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)を参照してください。
