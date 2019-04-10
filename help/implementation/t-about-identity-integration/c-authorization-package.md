---
description: ユーザー認証を有効にするには、認証パッケージをインストールしてユーザーがアプリケーションを操作できるようにします。
seo-description: ユーザー認証を有効にするには、認証パッケージをインストールしてユーザーがアプリケーションを操作できるようにします。
seo-title: 認証パッケージ
solution: Experience Manager
title: 認証パッケージ
uuid: 4eec30cf-66b6-408d-985d-3e23b8b70d01
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# 認証パッケージ{#authentication-package}

ユーザー認証を有効にするには、認証パッケージをインストールしてユーザーがアプリケーションを操作できるようにします。

Livefyreアプリケーションは、グローバル認証パッケージを使用して、ユーザーをアプリアクションに関連付けます。認証パッケージを使用でき `Livefyre.require`ます。

ページの認証を有効にするには、まずWebページ `Livefyre.js` またはWebサイトテンプレートの `<head>` 要素に追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

Livefyreを使用した認証の有効化は、他のパッケージを呼び出すのに必要なのと同様です。認証を必要とする統合コードは次のようになります。

```
Livefyre.require(['auth'], function (auth) {  
// Perform action... 
});
```

## メソッド {#section_ojx_1lz_fz}

上記のように、認証関連イベント `Livefyre.require`に関するページ上で他のアプリケーションに通知するために呼び出すことができるメソッドは、認証モジュールによって公開されます。

| メソッド | 説明 |
|--- |--- |
| `.login(callback)` | 登録されているAuthDelegateによって実装されるログインフローをトリガーします。通常、ホストページ自体ではなく、認証が有効なアプリのみが呼び出されます。 |
| `.logout(callback)` | 一部の外部手段でエンドユーザーがログアウトしたこと、およびすべての依存関係アプリケーションが次のログインまで認証状態をクリアすることを通知します。これにより、Authによって保持される内部セッションがクリアされます。 |
| `.authenticate(credentials)` | ユーザーが一部の外部手段によって認証されていることを通知し、Livefyre認証トークンをエンドユーザー向けに入手しました。これを使用するには、CookieをLivefyreトークンに設定するか、ユーザーのトークンを設定して、ユーザーに明示的にログインします。次に例を示します。 <br>`auth.authenticate({&nbsp;livefyre:&nbsp;`<br>`'<insert&nbsp;lftoken&nbsp;string&nbsp;for&nbsp;newly&nbsp;logged-in&nbsp;user>'&nbsp;});` |
| `.delegate(authDelegate)` | 認証の実装詳細（例えば、カスタム認証フロー）を定義したオブジェクトに委任します。Livefyreアプリケーションのインタラクティブ機能を有効にするには、ホストページから呼び出す必要があります。 |

