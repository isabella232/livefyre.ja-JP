---
description: Twitterからコンテンツを取り込むストリームルールを作成できます。
seo-description: Twitterからコンテンツを取り込むストリームルールを作成できます。
seo-title: Twitterルール
solution: Experience Manager
title: Twitterルール
uuid: a7fd2398-fd6b-4c24-92b2-7471176d7648
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# Twitterルール{#twitter-rules}

Twitterからコンテンツを取り込むストリームルールを作成できます。

ハッシュタグ、キーワード、@メンションまたは発言者に基づいてTwitterルールを作成します。

ルールに **[!UICONTROL Words]** とを追加す **[!UICONTROL Username]** ると、両方のエントリを含むコンテンツが返されます。

>[!NOTE]
>
>LivefyreはTwitterの表示ガイドラインに従い、顧客もこれらのガイドラインを遵守する責任を負います。 詳しくは、Twitterの表示要件に関するドキュメントを参照し [てください](https://dev.twitter.com/terms/display-requirements)。

Twitterルールを作成して、Twitterフィードからアプリまたはフォルダーにコンテンツを取り込むには、次のようにフィルターします。

* **[!UICONTROL Keywords]**
   * Twitterスト **[!UICONTROL Keywords]** リームに含めるか、Twitterストリームから除外するかを入力します。 とフィールドの両方に値を指 **[!UICONTROL Contains any of these words]** 定すると、 **[!UICONTROL Does not contain any of these words]** 最初の値を含み、2番目の値を含まないツイートが返されます。 1つのフィールドに複数の値を入力でき、任意の値を含む結果を返します。 ブール演算子ANDを使用して、2つ以上の単語を含むツイートを検索するには、2つのアンパサンド(*&amp;&amp;*)を使用して2つの単語を区切ります。
   * 例えば、キーワードGiants、Poseyおよび **[!UICONTROL Contains any of these words]****[!UICONTROL Does not contain any of these words]** keyword Dodgerを入力すると、DodgerPoseyという語を含み、DodgerPoseyという語を含まないすべてのツイー *トが返さ*****れます。
「 *Giants* 」と「 *Posey」の両方の単語を含むツイートを検索するには*、「Giants &amp;&amp; Posey」と入力します。 この機能は、Twitterルールのフィールドとフ **[!UICONTROL Contains any of these words]** ィールド **[!UICONTROL Does not contain any of these words]** に対してのみサポートされます。

* **[!UICONTROL Hashtags]**.
   * Twitterスト **[!UICONTROL Hashtags]** リームに含めるか、Twitterストリームから除外するかを入力します。 とフィールドの両方に値を指 **[!UICONTROL Contains any of these words]** 定す **[!UICONTROL Does not contain any of these words]** ると、最初のフィールドにハッシュタグを含み、2番目のフィールドにハッシュタグを含まないツイートが返されます。 1つのフィールドに複数の値を入力できます。 ストリームは、任意の値を含む結果を返します。

* **[!UICONTROL Usernames]**
   * ストリーム **[!UICONTROL @mentions]** に取り込む **[!UICONTROL authors]** か、ストリームから除外するかを入力します。 チェックボックスを使用して、選択した作成者 **[!UICONTROL Retweets]** も含め **[!UICONTROL replies]** るか、含めるかを定義します。
   >[!NOTE]
   >
   >作成者を含めたり除外したりできます。これらの2つのフィールドを1つのTwitterルールに組み合わせることはできません。

* **[!UICONTROL Minimum number of followers.]** ユーザーが投稿から情報を取り込む必要がある最低フォロワー数を選択します。
* **[!UICONTROL Location]**

   * 場所(市区町村、郵便番号、住所、または地域コードを、共通の緯度/経度形式(+/- 90、+/- 180)で入力します。) 場所を入力し始め、提案のあるドロップダウンメニューを表示します。 ドロップダウンから場所を選択します。 マップにその場所のピンが表示されます。 スライダを調整して、各位置の半径を1マイルから25マイルに設定します。 半径を選択しない場合、Livefyreは自動的に8マイルのデフォルトを選択します。
   >[!NOTE]
   >
   >両方のフィールドについて、入力位置の中心から距離が計算されます。

   * 複数の位置と半径を追加できます。 場所を削除するには、ボックス内の場所の名前の横にある「X」をクリックします。
   * とのフィールド **[!UICONTROL Is near this location]** を組み合わ **[!UICONTROL Is not near this location]** せて、フィールド内の場所内のコンテンツを引き寄せ **[!UICONTROL Is near this location]** ます。ただし、フィールド内の場所の近くには収め **[!UICONTROL Is not near this location]** ません。


* **[!UICONTROL Additional Filters]**
   * 追加のフィルターを使用して、Twitterルールをさらに絞り込みます。 次のどちらを行うかを定義します。
      * ターゲット **[!UICONTROL Replies]** のツイートに含めます（ストリームが高速になった場合、この機能は自動的に無効になります）。
      * ツイートを含める **[!UICONTROL Verified Twitter accounts only.]**
      * 含める、 **[!UICONTROL All Content]**&#x200B;または、 **[!UICONTROL Vines Only]**&#x200B;または **[!UICONTROL Images Only.]**
      * 選択したアカウント（任意、100、500、1000、10,000または100,000） **[!UICONTROL Minimum number of followers]** から派生するツイートのみを含めます。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。
