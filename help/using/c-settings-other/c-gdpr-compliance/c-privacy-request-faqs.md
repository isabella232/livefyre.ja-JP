---
description: GDPR対応のプライバシー・リクエストに関するFAQ(Faq)への回答
title: プライバシーリクエストに関するFAQ
exl-id: 6d0add45-589a-46d0-b15a-63a7599aad73
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 1%

---

# プライバシーリクエストFAQ{#privacy-request-faqs}

GDPR対応のプライバシー・リクエストに関するFAQ(Faq)への回答

* **Livefyre Appsを使用するサイトで、サイトの訪問者オプトアウトを追跡する方法を教えてください。** サイトの訪問者がオプトアウトする場合、アプリをインスタンス化する前に、ユーザーがオプトアウトしたことをLivefyreに通知する必要があります。Livefyreは、JavaScriptオプション`userPrivacyOptOut`を使用してこれを行う方法を開発しました。 `userPrivacyOptOut`の使用方法について詳しくは、[userPrivacyOptOut](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)を参照してください。

   `userPrivacyOptOut`フラグをtrueに設定すると、ページ上のアプリはcookieまたは他の方法を使用してLivefyreサーバーにデータを送信しません。 その後、Livefyreは、サイト訪問者の追跡に使用できるデータでローカルストレージを更新しません。 ソースがプロキシをサポートしていない場合、ユーザーがビデオをクリックしてそのソースから考えられるトラッキングを承認しない限り、Livefyreはコンテンツにマスクを表示します。

   Livefyre IDを使用する場合、ユーザーは自分のプロファイルを削除するか、ユーザーアカウント用に追跡されたデータのレポートを作成するかを選択できます。

* **オプトアウトしたサイト訪問者から将来のコンテンツが収集されないようにするにはどうしますか。** Livefyre Apps `userPrivacyOptOut` を使用 `livefyre.js` するWebページでと共に使用します。`userPrivacyOptOut`について詳しくは、[userPrivacyOptOut](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)を参照してください。

* **アプリのユーザーまたはソーシャルアカウントの所有者のレポートを生成し、データを削除する方法を教えてください。** [プライバシー](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) の要求を参照して、レポートを生成し、アプリからユーザーデータを削除します。

* **訪問者のすべてのコンテンツを削除する方法を教えてください。** Livefyreは、サイト訪問者に関する永続的な情報を維持しません。ただし、Livecount機能を一意に識別するためのcookieの形式を除きます。Livecountは、サイト上の訪問者の一時的なリアルタイムカウントです。 訪問者がCookieを離脱またはクリアした後も履歴は保持されません。

   アカウントを削除するには、[プライバシーリクエスト](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests)を作成します。 Livefyreがユーザーと関連するレコードを削除またはプロファイルします。

* **登録ユーザーのコンテンツを削除する方法を教えてください。** アカウントを削除する [ための](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) プライバシー要求を作成します。ユーザープロファイルと関連するレコードは完全に破棄されます。

   >[!NOTE]
   >
   >このアクションを取り消すことはできません。

* **現在の従業員または以前の従業員を追跡したデータのレポートを作成する方法を教えてください。** [プライバシー](../../c-settings-other/c-gdpr-compliance/c-view-a-privacy-report.md#c_view_a_privacy_report) レポートを表示して、ユーザーアカウントに対して追跡されたデータのレポートを生成します。

* **Livefyreのソーシャルストリームは準拠しているか。** ユーザーがソーシャルネットワークから投稿またはツイートを削除すると、24時間以内にLivefyreのすべてのソースからもコンテンツが削除されます。これはTwitterとFacebookに当てはまる。
