---
description: Janrain Captureや独自のIDサービスを含む、Livefyreアプリにユーザー認証を追加するためのオプションについて説明します。
seo-description: Janrain Captureや独自のIDサービスを含む、Livefyreアプリにユーザー認証を追加するためのオプションについて説明します。
seo-title: ID統合
solution: Experience Manager
title: ID統合
uuid: 079dc9c7-656a-49d0-920d-9e5a421a319c
translation-type: tm+mt
source-git-commit: 0c5420fcb3ba2e12375e92d4574d0a6dff310869

---


# ID統合{#identity-integration}

Janrain Captureや独自のIDサービスを含む、Livefyreアプリにユーザー認証を追加するためのオプションについて説明します。

## ID統合 {#t_about_identity_integration}

Janrain Captureや独自のIDサービスを含む、Livefyreアプリにユーザー認証を追加するためのオプションについて説明します。

Livefyreアプリには、コメントの投稿、レビューの作成、コンテンツに対する「いいね！」などのリッチインタラクティブ機能が含まれています。 ユーザーがLivefyre Appsとやり取りするには、Livefyre.js Authを使用してLivefyreをIDサービスと統合する必要があります。

Livefyre.js authは、サイト全体のすべてのLivefyreアプリに対して一元的な認証を提供し、ユーザーがログインして登録する必要のある正確な方法を管理します。 認証をサイトのテンプレートにグローバルに追加して、すべてのページで使用するか、1ページに1回追加します。また、Livefyre JS Authでユーザーがサインインすると、ページ上のすべてのアプリにユーザーの情報が自動的にブロードキャストされます。

カスタムIDサービスを構築した場合でも、Janrain CaptureなどのサードパーティIDサービスを使用している場合でも、この節では、統合に必要な情報をすべて取り上げます。
