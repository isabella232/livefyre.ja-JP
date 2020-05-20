---
product: livefyre
audience: end-user
user-guide-title: Livefyre導入ガイド
translation-type: tm+mt
source-git-commit: 3664bc1c51d2b372c358385127a1ca9c2f0cfef8
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 4%

---


# Livefyre導入ガイド {#implementation}

+ [Livefyre導入ガイド](home.md)
+ はじめに {#getting-started}
   + [Livefyre統合の概要](c-getting-started/c-getting-started.md)
   + 実装プロセス {#implementation-process}
      + [実装プロセス](c-getting-started/c-implementation-process/c-implementation-process.md)
      + [アプリの統合タイプ](c-getting-started/c-implementation-process/c-app-integration-types.md)
      + [アプリの実装](c-getting-started/designer-app-implementation.md)
      + [Livefyreのサードパーティとの統合の実装](c-app-integrations/implement-livefyre-3rd-party.md)
      + [アーキテクチャ](c-getting-started/c-implementation-process/c-architecture.md)
      + [アプリを埋め込む](c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)
      + [追加Livefyre.jsを使用したアプリの認証](c-getting-started/c-implementation-process/c-add-authetication-to-an-app-using-livefyre.js.md)
      + [サーバー側トークンの構築](c-getting-started/c-implementation-process/c-build-server-side-tokens.md)
      + [CollectionMeta Token](c-getting-started/c-implementation-process/c-collectionmeta-tokent.md)
      + [ユーザー認証トークン](c-getting-started/c-implementation-process/c-user-auth-token.md)
      + [CollectionMetaトークンを使用したコレクションの作成](t-create-a-collectionmeta-token.md)
      + [チェックサムの作成](c-creating-a-checksum.md)
+ IDの統合 {#identity-integration}
   + [IDの統合](t-about-identity-integration/t-about-identity-integration.md)
   + [認証パッケージ](t-about-identity-integration/c-authorization-package.md)
   + [AuthDelegateオブジェクト](t-about-identity-integration/c-building-an-auth-delegate.md)
   + [外部システムへのユーザー権限の投稿（オプション）](t-about-identity-integration/c-posting-user-permissions-to-external-systems.md)
   + SSOの実装 {#implementing-sso}
      + [SSOの実装](t-about-identity-integration/c-implementing-sso/c-implementing-sso.md)
      + [認証委任のデバッグ](t-about-identity-integration/c-implementing-sso/c-debugging-auth.md)
   + Livefyreと同期 {#sync-ping-for-pull}
      + [Pingを使用したLivefyreとの同期（取り込み用）](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-sync-with-livefyre-using-ping-for-pull.md)
      + [プルエンドポイントの構築](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-build-the-pull-endpoint.md)
      + [エンドポイントのStudioへの登録](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/c-register-the-endpoint-with-studio.md)
      + [Pingの構築](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-build-the-ping.md)
      + [プル要求構造](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/t-pull-request-structure.md)
      + [プル応答用のPingの構築](t-about-identity-integration/t-sync-with-livefyre-using-ping-for-pull/c-build-the-ping-for-pull-response.md)
+ Livefyre ID {#livefyre-identity}
   + [Livefyre ID](c-livefyre-identity-comp/c-livefyre-identity-comp.md)
   + [Livefyre IDを有効にする](c-livefyre-identity-comp/t-enable-livefyre-identity.md)
   + Livefyre IDでのソーシャルアプリの使用 {#use-social-apps-with-livefyre-identity}
      + [Socialアプリの作成](c-livefyre-identity-comp/t-create-your-social-apps.md)
      + [Livefyre IDと共に使用するFacebookアプリを作成する](c-livefyre-identity-comp/t-create-a-facebook-app-for-use-with-livefyre-identity.md)
      + [Livefyre IDと共に使用するTwitterアプリを作成する](c-livefyre-identity-comp/t-create-a-twitter-app-for-use-with-livefyre-identity.md)
      + [Yahoo！の作成 Livefyre IDで使用するアプリ](c-livefyre-identity-comp/t-create-a-yahoo-app-for-use-with-livefyre-identity.md)
      + [Livefyre Idで使用するMicrosoft Live Identityアプリケーションの作成](c-livefyre-identity-comp/t-create-a-microsoft-live-id-app-for-use-with-livefyre-identity.md)
      + [Livefyre IDで使用するLinkedInアプリの作成](c-livefyre-identity-comp/t-create-a-linkedin-app-for-use-with-livefyre-identity.md)
      + [Livefyre IDで使用するGitHub IDアプリを作成する](c-livefyre-identity-comp/c-create-a-github-identity.md)
      + [Studioを使用したSocialアプリケーションのLivefyre実装への接続](c-livefyre-identity-comp/t-using-studio-to-connect-your-social-apps-to-your-livefyre-implementation.md)
   + [追加Livefyre.jsのページへの追加](c-livefyre-identity-comp/t-add-livefyre.js-to-the-page.md)
   + [Livefyre IDの初期化](c-livefyre-identity-comp/t-initialize-livefyre-identity.md)
   + [Livefyre ID用電子メール](c-livefyre-identity-comp/c-emails-for-livefyre-identity.md)
   + [ジャンレインキャプチャ/バックプレーン](c-livefyre-identity-comp/c-janrain-capture-backplane-comp.md)
   + インストール {#installation}
      + [ライブラリのインストール](c-installing-libraries/c-installing-libraries.md)
      + [クラスとメソッド](c-installing-libraries/c-methods-livefyre.md)
      + [ネットワークメソッド](c-installing-libraries/c-network-methods.md)
      + [setSSLネットワークメソッド](c-installing-libraries/r-setssl-method.md)
      + [buildLivefyreTokenネットワークメソッド](c-installing-libraries/r-buildlivefyretoken-method.md)
      + [buildUserAuthTokenネットワークメソッド](c-installing-libraries/r-builduserauthtoken-method.md)
      + [validateLivefyreTokenネットワークメソッド](c-installing-libraries/c-validatelivefyretoken-network-method.md)
      + [setUserSyncUrlネットワークメソッド](c-installing-libraries/r-setusersyncurl-method.md)
      + [syncUserネットワークメソッド](c-installing-libraries/r-syncuser-method.md)
      + [getUrnネットワークメソッド](c-installing-libraries/r-geturn-method.md)
      + [getUrnForUserネットワークメソッド](c-installing-libraries/r-geturnforuser-method.md)
      + [getNetworkNameネットワークメソッド](c-installing-libraries/r-getnetworkname-method.md)
      + [getSiteネットワークメソッド](c-installing-libraries/r-getsite-method.md)
      + [ネットワーククラスメソッド](c-installing-libraries/c-network-class-methods.md)
      + [コレクションクラスのメソッド](c-installing-libraries/c-collection-methods.md)
      + [createOrUpdateコレクションメソッド](c-installing-libraries/r-createorupdate-collection-method.md)
      + [buildCollectionMetaTokenコレクションメソッド](c-installing-libraries/r-buildcollectionmetatoken-collection-method.md)
      + [buildChecksumコレクションメソッド](c-installing-libraries/r-buildchecksum-collection-method.md)
      + [getCollectionContentコレクションメソッド](c-installing-libraries/t-getcollectioncontent-collection-method.md)
      + [getUrnコレクションメソッド](c-installing-libraries/r-geturn-collection-method.md)
      + [サイトクラスメソッド](c-installing-libraries/c-site-methods.md)
      + [buildBlogCollectionサイトメソッド](c-installing-libraries/r-buildblogcollection-site-method.md)
      + [buildChatCollectionサイトメソッド](c-installing-libraries/r-buildchatcollection-site-method.md)
      + [buildCommentsCollectionサイトメソッド](c-installing-libraries/r-buildcommentscollection-site-method.md)
      + [buildCountingCollectionサイトメソッド](c-installing-libraries/r-buildcountingcollection-site-method.md)
      + [buildRatingsCollectionサイトメソッド](c-installing-libraries/r-buildratingscollection-site-method.md)
      + [buildReviewsCollectionサイトメソッド](c-installing-libraries/r-buildreviewscollection-site-method.md)
      + [buildSitenotesCollectionサイトメソッド](c-installing-libraries/r-buildsitenotescollection-site-method.md)
      + [buildCollectionサイトメソッド](c-installing-libraries/r-buildcollection-site-method.md)
      + [getUrnサイトメソッド](c-installing-libraries/r-geturn-site-method.md)
      + [例](c-installing-libraries/c-libraries-examples.md)
   + モバイル SDK {#mobile-sdks}
      + [モバイル SDK](c-mobile-sdks/c-mobile-sdks.md)
      + [Livefyre iOS SDK](c-mobile-sdks/c-livefyre-ios-sdk.md)
      + [Android SDK](c-mobile-sdks/c-android-sdk.md)
+ [Livefyre.js](c-livefyre.js.md)
+ [LivefyreトークンC#の作成](c-creating-livefyre-tokens-c-.md)
+ アプリの統合 {#app-integrations}
   + [チャット](c-app-integrations/c-app-integratios-chat.md)
   + コメント {#comments}
      + [Comments](c-app-integrations/c-comments-integration/c-comments-integration.md)
   + [ライブブログ](c-app-integrations/c-live-blog-integration.md)
   + [レビュー](c-app-integrations/c-reviews-integration.md)
   + Sidenots {#sidenotes}
      + [Sidents統合](c-app-integrations/c-sidenotes-integration/r-sidenotes-integration.md)
      + [ページへのサイトの追加](c-app-integrations/c-sidenotes-integration/r-adding-sidenotes-to-a-page.md)
      + [Sidents Appイベント](c-app-integrations/c-sidenotes-integration/r-app-events.md)
      + [サイトの設定オプション](c-app-integrations/c-sidenotes-integration/r-configuration-options.md)
      + [カスタムスタイルを示す](c-app-integrations/c-sidenotes-integration/r-custom-styles.md)
      + [カスタム文字列を示す](c-app-integrations/c-sidenotes-integration/r-custom-strings.md)
      + [Sidentsの実装](c-app-integrations/c-sidenotes-integration/r-sidenotes-implementation.md)
      + [updateAnchorsメソッド](c-app-integrations/c-sidenotes-integration/update-anchors-method.md)
   + [マップ](c-app-integrations/c-map-integration.md)
   + [メディアウォール](c-app-integrations/c-media-wall-integration.md)
   + [トレンド](c-app-integrations/c-trending-integration.md)
+ アプリのカスタマイズ {#app-customizations}
   + [アプリのカスタマイズ](c-app-customizations/c-app-customizations.md)
   + [表示オプションの変更](c-app-customizations/c-change-display-options.md)
   + [CSSクラス](c-app-customizations/c-css-classes.md)
   + [CSSクラスの保存](c-app-customizations/c-storify-css-classes.md)
   + [翻訳セット](c-app-customizations/c-translation-sets.md)
   + [Livefyreロゴを移動する](c-app-customizations/c-move-the-livefyre-logo.md)
   + [メディアの制限](c-app-customizations/c-restrict-media.md)
   + [アプリ要素を非表示](c-app-customizations/c-hide-app-elements.md)
   + [アイコンを変更（@mention）](c-app-customizations/c-change-mention-icon.md)
   + [コンテンツをハイライト](c-app-customizations/c-highlight-content.md)
   + [日付と時間スタンプのカスタマイズ](c-app-customizations/c-date-time-stamp.md)
   + 機能の内容 {#feature-content}
      + [機能の内容](c-app-customizations/t-feature-content.md)
      + [Studioでフィーチャーコンテンツを有効にする](c-app-customizations/t-enable-featuring-content-in-studio.md)
      + [アプリから機能するコンテンツを選択](c-app-customizations/t-select-content-to-feature.md)
      + [Studioからフィーチャのコンテンツを選択](c-app-customizations/t-select-content-to-feature-from-studio.md)
      + [CSSを使用して重点コンテンツのスタイルを設定](c-app-customizations/c-use-css-to-style-featured-content.md)
      + [機能API](c-app-customizations/c-feature-apis.md)
   + [AuthDelegateを使用したJanrainのLivefyreへの接続](c-app-customizations/c-connecting-janrain-to-livefyre-using-authdelegate.md)
   + [特集APIを使用した集計された特集コンテンツ](c-app-customizations/c-aggregated-featured-content-using-the-featured-apis.md)
   + スタイルコンテンツ {#style-content}
      + [スタイルユーザーグループのコンテンツ](c-app-customizations/c-style-user-group-content.md)
      + [グループへのユーザーの追加](c-app-customizations/c-adding-users-to-groups.md)
   + カスタムスタイルの適用 {#apply-custom-styles}
      + [カスタムスタイルの適用](c-app-customizations/c-applying-custom-styles-.md)
      + [追加カスタムボタン](c-app-customizations/t-add-custom-buttons.md)
   + Javascript Events {#javascript-events}
      + [JavaScriptイベントの定義と例](c-app-customizations/c-javascript-events.md)
      + [ビジュアライゼーションアプリのJavaScriptイベント](c-app-customizations/c-javascript-events-for-visualization-apps.md)
      + [メディアウォールのJavaScriptイベント](c-app-customizations/c-javascript-events-media-wall.md)
      + [会話アプリ用のJavaScriptイベント](c-app-customizations/c-javascript-events-for-conversation-apps.md)
   + [コメントアプリの埋め込み](c-app-customizations/c-embed-a-comments-app.md)
   + [照会の追跡](c-app-customizations/c-referral-tracking.md)
   + [デバイスとブラウザーのサポート](c-app-customizations/c-device-and-browser-support.md)
   + [Twitterの表示要件](c-app-customizations/c-twitter-display-requirements.md)
+ [ストレステストポリシー](c-stress-test-policy.md)
+ Analytics {#analytics}
   + [Analytics](livefyre-analytics/livefyre-analytics.md)
   + [Adobe AnalyticsおよびDynamic Tag Manager(DTM)とLivefyreを使用する](livefyre-analytics/c-use-livefyre-with-adobe-analytics.md)
   + [他のAnalyticsツールとLivefyreを使用する](livefyre-analytics/c-livefyre-analytics.md)
   + [Livefyre Analyticsのイベント](livefyre-analytics/c-livefyre-analytics-events.md)
+ [LivefyreとAEMの統合](c-livefyre-aem-integration.md)
+ 高度なトピック {#advanced-topics}
   + [コメント数を表示](c-advanced-topics/t-display-comment-count.md)
   + [ソーシャルシェアを有効にする](c-advanced-topics/c-enabling-social-sharing.md)
   + [アクティビティストリーム](c-advanced-topics/c-activity-stream.md)
   + [Bootstrap HTML](c-advanced-topics/c-bootstrap-html.md)
   + [コレクションの変更](c-advanced-topics/c-change-collection.md)
   + [複数のコレクション](c-advanced-topics/c-multiple-collections.md)
   + [コアアプリの種類の切り替え](c-advanced-topics/c-switch-core-app-types.md)
   + [ソーシャルカウンター](c-advanced-topics/c-social-counter.md)
   + [LivefyreアプリでのBootsrapおよびStream APIの使用](c-advanced-topics/bootstrap-stream-api.md)
