---
description: Ping for Pull応答を作成して、更新されたユーザー情報をLivefyreに送信します。
title: プル応答用のPingの構築
exl-id: 81c398fd-2acb-4e39-a2b3-c96921b1192b
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 2%

---

# プル応答用のPingの構築{#build-the-ping-for-pull-response}

Ping for Pull応答を作成して、更新されたユーザー情報をLivefyreに送信します。

| タイプ | プロパティ | 説明 |
|--- |--- |--- |
| 文字列&#x200B;*必須* | ID | プロファイルシステム内のユーザーのユーザーID。 この値は、ネットワーク内のすべてのユーザーに対して一意である必要があり、変更しないでください。 |
| 文字列&#x200B;*必須* | display_name | ユーザーの表示名。 これは、ユーザーがLivefyreコンテンツを投稿してレンダリングされます。 |
| オブジェクト&#x200B;*はオプションですが、推奨* | name | ユーザーの形式設定済みの名前、名、中間、名を定義する文字列です。 |
| 文字列&#x200B;*オプション、推奨* | 電子メール | ユーザーの電子メールアドレス。 電子メール通知の送信に使用します。 |
| 文字列&#x200B;*オプション、推奨* | image_url | ユーザーに表示するアバターへのURL。 アップロードした画像は、必要に応じて100×100、75×75または50×50ピクセルに拡大・縮小されます。 最良の結果を得るには、100×100ピクセルの正方形の画像をアップロードする必要があります。 Livefyreでアバター画像が更新されるようにするには、各画像の更新時にimage_urlを変更し、Ping for Pullで画像が変更されたことが検出されるようにします。 例えば、ファイル名にタイムスタンプを付加したり、画像の変更を増やしたりします。 注意： すべてのURLは、完全修飾され、アクセス可能である必要があります。 |
| 文字列&#x200B;*オプション、推奨* | プロファイル_url | サイト上のユーザーのプロファイルページへのURL。 |
| 文字列&#x200B;*オプション、推奨* | settings_url | ユーザーがサイトのプロファイル設定を行うことのできるページのURL。 |
| 配列&#x200B;*オプション、推奨* | タグ | ユーザーをユーザーグループに割り当てるために使用します。 タグには、1 ～ 63個の英数字とアンダースコア文字を含めることができます。 |
| ブール値&#x200B;*オプション、推奨* | autofollow_conversations | コレクションに投稿した後、コレクションを自動的にフォローするかどうかを定義します。 コレクションをフォローする場合、他のユーザーが参加すると、ユーザーに電子メール通知が送信されます。 trueまたはfalseの場合があります。 デフォルトはtrueです。 |
| オブジェクト&#x200B;*はオプションですが、推奨* | email_notifications | 使用可能なLivefyre電子メール通知の頻度を定義します。 通知タイプごとに異なる頻度を設定できます。 デフォルトでは、通知は送信されません。<br><ul><li> 一覧表示されたイベントにすぐに通知を発行します。 </li><li>多くの場合、通知をバッチで発行します。 </li><li> アクティビティの電子メール通知は送信されません。 </li><li>*コメント*:他のユーザーが、このユーザーがフォローしているコレクションにコンテンツを投稿する場合に通知を送信するタイミングを定義します。 </li><li>*返信*:別のユーザーがこのユーザーのコンテンツに返信したときに通知を送信するタイミングを定義します。</li><li>*いいね！*:別のユーザーがこのユーザーのコンテンツに「いいね！」した場合に通知を送信するタイミングを定義します。</li><li>*moderator_comments*:ユーザーがネットワーク内の任意のコレクションにコンテンツを投稿する際に、モデレーターに通知を送信するタイミングを定義します。</li><li>*moderator_flags*:他のユーザーがネットワーク内の任意のコレクションのコンテンツにフラグを付けた場合に、通知をモデレーターに送信するタイミングを定義します。</li></ul> |
| 文字列&#x200B;*オプション* | ロケーション | ユーザーが送信した場所。 |
| 文字列&#x200B;*オプション* | 生物学 | ユーザーが提出した自伝。 |
| 配列&#x200B;*オプション* | Webサイト | ユーザーが送信したサイトの配列。 最大= 2。 |
| オブジェクト&#x200B;*オプション* | display_rules | 他のユーザーに対して公開表示するプロファイルプロパティを定義します。 使用可能な各パラメーターは、ブール値の入力をtrueまたはfalseにします。 使用可能なパラメーター： <br><ul><li>生物学 </li><li> ロケーション</li><li>  性別 </li><li>nameimage </li><li> remote_プロファイル_url</li></ul> |
| ブール値&#x200B;*オプション* | 司会者 | ユーザーがネットワーク全体でモデレーター権限を持つかどうかを定義します。 |
| ブール値&#x200B;*オプション* | gravatar_disabled | image_urlが指定されていない場合にLivefyreの重力の使用を無効にするかどうかを定義します。 |

## 応答の例 {#section_uxt_3dd_mz}

```
{
 "id": "1234567890",
 "display_name": "Bob Dole",
 "name": {
   "formatted": "Bob Joseph Dole",
   "first": "Bob",
   "middle": "Joseph",
   "last": "Dole"
 },
   "email": "bob@dole.com",
   "image_url": "https://dole.com/images/bob.jpg",
   "profile_url": "https://site.com/bobdole",
   "settings_url":"https://site.com/settings",
   "tags": ["bob", "dole"],
   "autofollow_conversations": "true",
   "email_notifications": {
      "comments": "never",
      "replies": "immediately",
      "likes": "often",
      "moderator_comments": "immediately",
      "moderator_flags": "immediately" 
 },
  "location": "Washington D.C., USA",
  "bio": "Bob Dole speaks in the third person",
  "websites": ["https://dole.com/blog/", "https://bobdolerocks.com"],
  "display_rules": {
      "bio": "false",
      "location": "false",
      "gender": "false",
      "name": "false",
      "image": "false",
      "remote_profile_url": "false"
  },
  "moderator": "true",
  "gravatar_disabled": "false"
}
```
