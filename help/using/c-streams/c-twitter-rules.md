---
description: Twitterからコンテンツを取り込むストリームルールを作成できます。
seo-description: Twitterからコンテンツを取り込むストリームルールを作成できます。
seo-title: Twitterルール
solution: Experience Manager
title: Twitterルール
uuid: a7fd2398- fd6b-4c24-92b2-7471176d7648
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Twitterルール{#twitter-rules}

Twitterからコンテンツを取り込むストリームルールを作成できます。

ハッシュタグ、キーワード、@メンションまたは発言者に基づいてTwitterルールを作成します。

ルール **[!UICONTROL Words]****[!UICONTROL Username]** を追加すると、両方のエントリを含むコンテンツが返されます。

>[!NOTE]
>
>LivefyreはTwitterの表示ガイドラインに従っており、お客様はこれらのガイドラインに従います。詳しくは [、Twitterの表示要件に関するドキュメント](https://dev.twitter.com/terms/display-requirements)を参照してください。

Twitterのフィードからアプリまたはフォルダーにコンテンツを取り込むためのTwitterルールを作成するには、次のようにフィルタリングします。

* **[!UICONTROL Keywords]**
   * Twitterストリームに含める **[!UICONTROL Keywords]** か、除外するかを指定します。両方 **[!UICONTROL Contains any of these words]** の **[!UICONTROL Does not contain any of these words]** フィールドとフィールドの値を指定すると、最初のフィールドを含むツイートが返され、2つ目のフィールドは含まれません。1つのフィールドに複数の値を入力すると、いずれかの値を含む結果が返されます。ブール演算子ANDを使用して複数の単語を含むツイートを検索するには、2つのアンパサンド（*&&*）を使用して2つの単語を区切ります。
   * For example, entering **[!UICONTROL Contains any of these words]** keywords Giants, Posey, and **[!UICONTROL Does not contain any of these words]** keyword Dodger, will return all Tweets which include the word *Giants* or *Posey* and do not include the word *Dodger*.
*Giants* と *Poey*という単語の両方を含むツイートを検索するには、"Giants&& Poey"と入力します。この機能は、Twitterルールのフィールドおよび **[!UICONTROL Contains any of these words]****[!UICONTROL Does not contain any of these words]** フィールドに対してのみサポートされています。

* **[!UICONTROL Hashtags]**.
   * Twitterストリームに含める **[!UICONTROL Hashtags]** か、除外するかを指定します。両方 **[!UICONTROL Contains any of these words]** のフィールドおよび **[!UICONTROL Does not contain any of these words]** フィールドの値を指定すると、最初のフィールドにハッシュタグを含むツイートが返され、2番目のフィールドにハッシュタグは含まれません。1つのフィールドに複数の値を入力できます。ストリームは、いずれかの値を含む結果を返します。

* **[!UICONTROL Usernames]**
   * ストリーム **[!UICONTROL @mentions]** に入るか **[!UICONTROL authors]** 、ストリームから除外するか、またはストリームから除外します。選択した発言者を含めるか **[!UICONTROL Retweets]****[!UICONTROL replies]** どうかを定義するには、チェックボックスを使用します。
   >[!NOTE]
   >
   >作成者を含めたり除外したりすることもできます。これら2つのフィールドを1つのTwitterルールに組み合わせることはできません。

* **[!UICONTROL Minimum number of followers.]** 投稿から情報を取り込む必要があるフォロワーの最小数を選択します。
* **[!UICONTROL Location]**

   * 共通の緯度/経度形式（+/-90、+/-180）の場所（市区町村、郵便番号、住所または地理コード）を入力します。ドロップダウンメニューを表示する場所を入力して、サーチクエリを表示します。ドロップダウンから場所を選択します。マップにその場所のピンが表示されます。スライダを調整して、場所ごとに半径が25マイルになるようにします。半径を選択しない場合、Livefyreは自動的に8マイルの初期設定を選択します。
   >[!NOTE]
   >
   >どちらのフィールドでも、距離は入力場所の中心から計算されます。

   * 複数の場所と半径を追加できます。場所を削除するには、ボックス内の場所の横にあるXをクリックします。
   * フィールドを結合 **[!UICONTROL Is near this location]****[!UICONTROL Is not near this location]** して **[!UICONTROL Is near this location]** フィールド内の場所内のコンテンツを引き出しますが **[!UICONTROL Is not near this location]** 、フィールド内の場所の近くには配置できません。


* **[!UICONTROL Additional Filters]**
   * 「追加フィルター」を使用して、Twitterルールをさらに絞り込みます。次のいずれかを定義します。
      * ターゲットのツイート **[!UICONTROL Replies]** に含める（ストリームが高速になると、この機能は自動的に無効になります）。
      * 次のツイートを **[!UICONTROL Verified Twitter accounts only.]**
      * 「次を含む **[!UICONTROL All Content]**」または **[!UICONTROL Vines Only]**" **[!UICONTROL Images Only.]**
      * 選択した **[!UICONTROL Minimum number of followers]** （任意の100、500、1000、10,000または100,000）のアカウントから派生するツイートのみを含めます。

すべてのストリームルール用の追加ストリームルールオプションについては、すべてのストリームルールの [ストリームルールオプションを参照](../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)してください。
