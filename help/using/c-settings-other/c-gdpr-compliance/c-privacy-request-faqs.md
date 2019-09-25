---
description: GDPR対応のプライバシー・リクエストに関するFAQ(Faq)への回答を掲載しています。
seo-description: GDPR対応のプライバシー・リクエストに関するFAQ(Faq)への回答を掲載しています。
seo-title: プライバシーリクエストFAQ
solution: Experience Manager
title: プライバシーリクエストFAQ
uuid: 0cd6f0d2-504d-46e9-ac46-070536cda086
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# プライバシーリクエストFAQ{#privacy-request-faqs}

GDPR対応のプライバシー・リクエストに関するFAQ(Faq)への回答を掲載しています。

* **Livefyre Appsを使用するサイトでのサイト訪問者の追跡をどのようにオプトアウトできますか。** サイトの訪問者がオプトアウトした場合、ユーザーがアプリをインスタンス化する前にオプトアウトしたことをLivefyreに示す必要があります。 JavaScriptオプションを使用してLivefyreがこれを行う方法を作成しました `userPrivacyOptOut`。 使用方法について詳しくは、userPrivacyOptOutを参 `userPrivacyOptOut`照してく [ださい](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)。

   このフラグ `userPrivacyOptOut` をtrueに設定すると、ページ上のアプリはcookieまたは他の方法を使用してLivefyreサーバーにデータを送信しません。 その後、Livefyreは、サイト訪問者の追跡に使用できるデータでローカルストレージを更新しません。 ソースがプロキシをサポートしていない場合、ユーザーがビデオをクリックして、そのソースからの潜在的なトラッキングを承認しない限り、Livefyreはコンテンツにマスクを表示します。

   Livefyre IDを使用する場合、ユーザーは自分のプロファイルを削除するか、自分のユーザーアカウントに対して追跡されるデータのレポートを作成するかを選択できます。

* **オプトアウトしたサイト訪問者から将来のコンテンツを収集しないようにする方法を教えてください。** Livefyreアプリ `userPrivacyOptOut` を使用 `livefyre.js` するWebページでを使用します。 詳しくは、userPrivacyOptOutを参照し `userPrivacyOptOut`てく [ださい](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)。

* **アプリのユーザーまたはソーシャルアカウントの所有者用にレポートを生成し、データを削除する方法を教えてください。** プライバ [シーリクエスト](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) 」を参照してください。

* **訪問者のすべてのコンテンツを削除する方法を教えてください。** Livefyreは、サイト訪問者を一意に識別するcookieの形式を除き、サイト訪問者に関する永続的な情報を維持しません。 Livecountは、サイト上の訪問者の一時的でリアルタイムなカウントです。 訪問者がcookieを離れたりクリアしたりした後は、履歴は保持されません。

   「プライバシー [リクエスト](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) 」を作成して、アカウントを削除します。 Livefyreは、ユーザープロファイルと関連するレコードを匿名で削除または作成します。

* **登録ユーザーのコンテンツを削除する方法を教えてください。** アカウントを [削除するには](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) 、プライバシーリクエストを作成します。 ユーザープロファイルと関連するレコードは完全に破棄されます。

   >[!NOTE]
   >
   >このアクションを取り消すことはできません。

* **現在の従業員または以前の従業員のデータを追跡するレポートを作成する方法を教えてください。** プライバ [シーレポートを表示して](../../c-settings-other/c-gdpr-compliance/c-view-a-privacy-report.md#c_view_a_privacy_report) 、ユーザーアカウントに関して追跡されたデータのレポートを生成します。

* **Livefyreのソーシャルストリームは準拠していますか？** ユーザーがソーシャルネットワークから投稿またはツイートを削除すると、24時間以内にLivefyreのすべてのソースからもコンテンツが削除されます。 これはTwitterとFacebookに適用されます。

