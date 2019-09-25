---
description: YouTubeルールからコンテンツを取り込むストリームルールを作成できます。
seo-description: YouTubeルールからコンテンツを取り込むストリームルールを作成できます。
seo-title: YouTubeルール
solution: Experience Manager
title: YouTubeルール
uuid: ec6a3780-7119-45c3-8ab2-fb0f9803d161
translation-type: tm+mt
source-git-commit: 30aa5cce5e7567208362cc35caeb7b7260c42f3b

---


# YouTubeルール {#youtube-rules}

YouTubeルールからコンテンツを取り込むストリームルールを作成できます。

ユーザー、チャネルまたはプレイリストに基づいてYouTubeルールを作成します。

YouTubeからYouTubeにコンテンツを取り込むためのYouTubeルールを作成するには、次の条件でフィルターできます。

* **[!UICONTROL User]**
   * ユーザーからのビデオをストリー **[!UICONTROL User]** ムに含めるバニティ文字列を入力します。
   * 例えば、入力するユーザーフィードのURLが次の場合は、単に `https://www.youtube.com/user/livefyresupport`と入力します `livefyresupport`。

* **[!UICONTROL Channel]**
   * チャネルからのビデオをストリームに **[!UICONTROL Channel]** 含めるには、のバニティ文字列を入力します。
   * 例えば、入力するチャネルフィードのURLが次の場合は、単に `https://www.youtube.com/channel/UCeNZlh03MyUkjRlLFpVQxsg`と入力します `UCeNZlh03MyUkjRlLFpVQxsg`。

* **[!UICONTROL Playlist]**
   * 再生リストのビデオをストリーム **[!UICONTROL Playlist]** に含めるバニティ文字列を入力します。
   * 例えば、入力するプレイリストフィードのURLが次の場合は、単に `https://www.youtube.com/playlist?list=PLFE5670C92BDAC201`「 `PLFE5670C92BDAC201`

* **[!UICONTROL Include recent items.]** これを次に設定すると、
   * **[!UICONTROL Enabled]**&#x200B;に設定されている場合、Livefyreは、投稿日に関係なく、フィード内の最初の15個のコンテンツ項目をストリームに追加します。
   * **[!UICONTROL Disabled]**&#x200B;に設定されている場合、Livefyreは、ストリームルール作成日以降と同じ発行日を持つストリームに、フィード内の最初の15個のコンテンツ項目を追加します。

すべてのストリームルールに対する追加のストリームルールオプションについては、「すべてのストリ [ームルールのストリームルールオプション」を参照してくださ](../../c-streams/c-stream-rule-options-for-all-stream-rules.md#c_stream_rule_options_for_all_stream_rules)い。
