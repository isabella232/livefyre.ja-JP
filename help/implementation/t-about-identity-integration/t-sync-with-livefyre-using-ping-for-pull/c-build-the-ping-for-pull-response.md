---
description: Pingをビルドして、更新されたユーザー情報をLivefyreに送信します。
seo-description: Pingをビルドして、更新されたユーザー情報をLivefyreに送信します。
seo-title: Ping for Pull Responseの構築
solution: Experience Manager
title: Ping for Pull Responseの構築
uuid: f90871d5-601f-40dc- b3d2- ab78635e4a88
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# Ping for Pull Responseの構築{#build-the-ping-for-pull-response}

Pingをビルドして、更新されたユーザー情報をLivefyreに送信します。

| タイプ | プロパティ | 説明 |
|--- |--- |--- |
| 文字列 *が必要です* | id | プロファイルシステム内のユーザーのユーザーID。これは、ネットワーク内のすべてのユーザーに対して一意である必要があり、変更しないでください。 |
| 文字列 *が必要です* | display_ name | ユーザーの表示名。これは、ユーザーが投稿したLivefyreコンテンツでレンダリングされます。 |
| オブジェクト *オプションですが、推奨されます* | name | ユーザーの形式設定、最初、中央および姓を定義する文字列。 |
| 文字列 *オプション（オプション）* | email | ユーザーの電子メールアドレス。電子メール通知を送信するために使用します。 |
| 文字列 *オプション（オプション）* | image_ url | ユーザーに表示するアバターへのURL。アップロードされた画像を必要に応じて100×100、75x75または50x50ピクセルに拡大縮小します。最良の結果を得るには、ユーザは100x100ピクセルの正方形の画像をアップロードする必要があります。Livefyreでアバター画像を更新するために、各画像更新のimage_ urlを変更し、Ping for Pullで画像が変更されたことを検出します。例えば、ファイル名にタイムスタンプを付加したり、画像の変更を増分したりします。注意:すべてのURLは完全修飾でアクセス可能である必要があります。 |
| 文字列 *オプション（オプション）* | profile_ url | サイト上のユーザーのプロファイルページへのURL。 |
| 文字列 *オプション（オプション）* | settings_ url | ユーザーがサイトのプロファイル設定を設定できるページへのURL。 |
| 配列 *はオプションですが、推奨されます* | タグ | ユーザーをユーザーグループに割り当てるために使用します。タグには、1~63の英数字とアンダースコア文字を含めることができます。 |
| ブール *オプション（オプション）ですが、推奨されます* | autocollow_ mentions | ユーザーが投稿後にコレクションに自動的に従うかどうかを定義します。コレクションの後に、ユーザーは他のユーザーが参加したときに電子メール通知を受信します。trueまたはfalseのいずれかです。デフォルトはtrueです。 |
| オブジェクト *オプションですが、推奨されます* | email_ notifications | 利用可能なLivefyre電子メール通知の頻度を定義します。通知タイプごとに異なる頻度を設定できます。デフォルトでは、通知は送信されません。 <br><ul><li> を設定すると、一覧表示されたイベントの直後に通知が直ちに発行されます。 </li><li>は、頻繁に通知をバッチで送信します。 </li><li> は、アクティビティの電子メール通知を送信しません。 </li><li>*コメント*:他のユーザーがこのユーザーをフォローしているコレクションにコンテンツを投稿したときに通知を送信するタイミングを定義します。 </li><li>*返信*:別のユーザーがこのユーザーのコンテンツに返信したときに通知を送信するタイミングを定義します。</li><li>*いい*ね!:他のユーザーがこのユーザーのコンテンツを「いいね!"した場合に通知を送信するタイミングを定義します。</li><li>*moderator_ comments*:ネットワーク内のコレクションにユーザーがコンテンツを投稿したときに、通知をモデレーターに送信するタイミングを定義します。</li><li>*moderator_ flags*:他のユーザーがネットワーク内のコレクションのコンテンツにフラグを付けたときに、通知がモデレーターに送信されるタイミングを定義します。</li></ul> |
| 文字列 *オプション* | location | ユーザーが送信した場所。 |
| 文字列 *オプション* | bio | ユーザーが提出した自動ロゴ。 |
| 配列 *オプション* | ウェブサイト | ユーザーが送信したサイトの配列。Max=2. |
| オブジェクト *オプション* | display_ rules | 他のユーザーに公開されるプロファイルプロパティを定義します。使用可能な各パラメーターは、Boolean入力trueまたはfalseを取ります。使用可能なパラメーター: <br><ul><li>bio </li><li> location</li><li>  gender </li><li>nameimage </li><li> remote_ profile_ url</li></ul> |
| ブール *オプション（オプション）* | モデレーター | ユーザーにネットワーク全体のモデレーター権限があるかどうかを定義します。 |
| ブール *オプション（オプション）* | gragatar_ disabled | image_ urlが提供されていない場合にLivefyreの使用を無効にするかどうかを定義します。 |

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
