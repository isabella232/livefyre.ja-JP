---
description: Ping for Pull応答を作成して、更新されたユーザー情報をLivefyreに送信します。
seo-description: Ping for Pull応答を作成して、更新されたユーザー情報をLivefyreに送信します。
seo-title: プル応答用のPingの構築
solution: Experience Manager
title: プル応答用のPingの構築
uuid: f90871d5-601f-40dc-b3d2-ab78635e4a88
translation-type: tm+mt
source-git-commit: 74a63daa264014af9a8afb6639fa1561a7b83241

---


# プル応答用のPingの構築{#build-the-ping-for-pull-response}

Ping for Pull応答を作成して、更新されたユーザー情報をLivefyreに送信します。

| タイプ | プロパティ | 説明 |
|--- |--- |--- |
| 文字列が必要 *です* | ID | プロファイルシステム内のユーザーのユーザーID。 この値は、ネットワーク内のすべてのユーザーに対して一意である必要があり、変更しないでください。 |
| 文字列が必要 *です* | display_name | ユーザーの表示名。 これは、ユーザーが投稿したLivefyreコンテンツでレンダリングされます。 |
| オブジェクト *はオプションですが、推奨されます* | name | ユーザーの形式設定済み、名、中間、姓を定義する文字列。 |
| 文字列はオ *プションですが、推奨されます* | 電子メール | ユーザーの電子メールアドレス。 電子メール通知の送信に使用します。 |
| 文字列はオ *プションですが、推奨されます* | image_url | ユーザーに表示するアバターへのURL。 Livefyreは、アップロードした画像を必要に応じて100×100、75×75または50×50ピクセルに拡大縮小します。 最良の結果を得るには、正方形の画像を100×100ピクセルでアップロードする必要があります。 Livefyreでアバター画像が更新されるようにするには、画像の更新ごとにimage_urlを変更し、Ping for Pullで画像が変更されたことが検出されるようにします。 例えば、ファイル名にタイムスタンプを付加したり、画像の変更を増分したりします。 注意： すべてのURLは、完全修飾子を持ち、アクセス可能である必要があります。 |
| 文字列はオ *プションですが、推奨されます* | profile_url | サイト上のユーザーのプロファイルページへのURL。 |
| 文字列はオ *プションですが、推奨されます* | settings_url | ユーザーがサイトのユーザーのプロファイル設定を行うページのURL。 |
| アレイはオ *プションですが、推奨* | タグ | ユーザーをユーザーグループに割り当てるために使用します。 タグには、1 ～ 63文字の英数字とアンダースコアを含めることができます。 |
| ブール値( *オプション、推奨)* | autofollow_conversations | ユーザーが投稿後にコレクションを自動的にフォローするかどうかを定義します。 コレクションをフォローすると、他のユーザーが参加したときに、電子メール通知がユーザーに送信されます。 trueまたはfalseの場合があります。 デフォルトはtrueです。 |
| オブジェクト *はオプションですが、推奨されます* | email_notifications | Livefyreの電子メール通知の頻度を定義します。 通知タイプごとに異なる頻度を設定できます。 デフォルトでは、通知は送信されません。 <br><ul><li> は、リストに表示されたイベントに直ちに通知を発行します。 </li><li>通知は、多くの場合、一括で発行されます。 </li><li> アクティビティの電子メール通知は送信されません。 </li><li>*コメント*:他のユーザーがコンテンツをこのユーザーがフォローしているコレクションに投稿した場合に通知を送信するタイミングを定義します。 </li><li>*返信*:別のユーザーがこのユーザーのコンテンツに返信した場合に通知を送信するタイミングを定義します。</li><li>*いいね！*:別のユーザーがこのユーザーのコンテンツに「いいね！」した場合に通知を送信するタイミングを定義します。</li><li>*moderator_comments*:ユーザーがネットワーク内の任意のコレクションにコンテンツを投稿する際に、モデレーターに通知を送信するタイミングを定義します。</li><li>*moderator_flags*:他のユーザーがネットワーク内の任意のコレクションのコンテンツにフラグを付けた場合に、通知をモデレーターに送信するタイミングを定義します。</li></ul> |
| 文字列(オプシ *ョン)* | ロケーション | ユーザーが送信した場所。 |
| 文字列(オプシ *ョン)* | 生物学的 | ユーザーが提出した自伝。 |
| 配列はオプシ *ョン* | Webサイト | ユーザーが送信したサイトの配列。 最大値= 2 |
| オブジェクト(オプ *ション)* | display_rules | 他のユーザーに対して公開表示されるプロファイルプロパティを定義します。 使用可能な各パラメーターは、ブール値の入力をtrueまたはfalseにします。 使用可能なパラメーター：  <br><ul><li>生物学的 </li><li> ロケーション</li><li>  性別 </li><li>nameimage </li><li> remote_profile_url</li></ul> |
| Booleanオプシ *ョン* | 司会者 | ユーザーがネットワーク全体でモデレーター権限を持つかどうかを定義します。 |
| Booleanオプシ *ョン* | gravatar_disabled | image_urlが指定されていない場合にLivefyreの重力の使用を無効にするかどうかを定義します。 |

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
