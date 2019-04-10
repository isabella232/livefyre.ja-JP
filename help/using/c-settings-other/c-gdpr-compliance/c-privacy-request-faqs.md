---
description: GGPR対応プライバシーリクエストに関するよくある質問（FAQ）への回答。
seo-description: GGPR対応プライバシーリクエストに関するよくある質問（FAQ）への回答。
seo-title: プライバシーリクエストFAQ
solution: Experience Manager
title: プライバシーリクエストFAQ
uuid: 0cd6f0d2-504d-46e9- ac46-070536cda086
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# プライバシーリクエストFAQ{#privacy-request-faqs}

GGPR対応プライバシーリクエストに関するよくある質問（FAQ）への回答。

* **Livefyreアプリを使用しているサイトでサイト訪問者がどのように追跡していないか。** サイト訪問者がオプトアウトすると、ユーザーの実装は、ユーザーがアプリケーションをインスタンス化する前にオプトアウトしているLivefyreを示す必要があります。Livefyreでは、JavaScriptオプションを使用してこれを行うこと `userPrivacyOptOut`ができます。使用 `userPrivacyOptOut`方法について詳しくは [、UserPrivacyOptOut](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)を参照してください。

   フラグが `userPrivacyOptOut` trueに設定されている場合、ページ上のすべてのアプリケーションはcookieまたは別の方法を使用してLivefyreサーバーにデータを送信しません。Livefyreは、サイト訪問者の追跡に使用できるデータを含むローカルストレージを更新しません。ソースがプロキシをサポートしていない場合、ユーザーがビデオをクリックし、そのソースからの潜在的なトラッキングを承認しない限り、コンテンツにはLivefyreがマスクを表示します。

   Livefyre IDを使用する場合、ユーザーはプロファイルを削除するか、ユーザーアカウント用に追跡されたデータのレポートを作成できます。

* **オプトアウトしたサイト訪問者から将来のコンテンツ収集を防ぐにはどうしますか。** Livefyreアプリケーションを使用するWebページ `userPrivacyOptOut` で `livefyre.js` 使用します。詳しく `userPrivacyOptOut`は [、UserPrivacyOptOut](/help/using/c-settings-other/c-gdpr-compliance/c-userprivacyoptout.md)を参照してください。

* **レポートを生成し、アプリユーザーまたはソーシャルアカウントの所有者のデータを削除する方法を教えてください。**[プライバシー要求](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) を参照してください。

* **訪問者のすべてのコンテンツを削除する方法を教えてください。** Livefyreは、Livecount機能で一意に識別するために、サイト訪問者に関する永続的な情報を保持しません。Livecountは、サイトの訪問者の一時的でリアルタイムのカウントです。訪問者がcookieを離れたりクリアした後、履歴は保持されません。

   アカウントを削除する [ためのプライバシーリクエスト](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) を作成します。ユーザープロファイルを削除するか、または関連付けられたレコードを匿名で削除します。

* **登録ユーザーのコンテンツを削除する方法を教えてください。** アカウントを削除する [ためのプライバシーリクエスト](../../c-settings-other/c-gdpr-compliance/c-privacy-requests.md#c_privacy_requests) を作成します。ユーザープロファイルと関連レコードは完全に破棄されます。

   >[!NOTE]
   >
   >このアクションは元に戻すことができません。

* **現在の従業員または以前の従業員のデータのレポートを作成するにはどうしますか。**[プライバシーレポート](../../c-settings-other/c-gdpr-compliance/c-view-a-privacy-report.md#c_view_a_privacy_report) を表示して、ユーザーアカウント用に追跡されたデータのレポートを生成します。

* **Livefyre Socialストリームは互換性があるか。** ユーザーがソーシャルネットワークから投稿またはツイートを削除すると、24時間以内に、コンテンツがLivefyreのすべてのソースからも削除されます。これは、TwitterおよびFacebookに適用されます。

