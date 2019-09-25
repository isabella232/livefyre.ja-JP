---
description: ユーザーがアプリを操作できるように、認証パッケージをインストールしてユーザー認証を有効にします。
seo-description: ユーザーがアプリを操作できるように、認証パッケージをインストールしてユーザー認証を有効にします。
seo-title: 認証パッケージ
solution: Experience Manager
title: 認証パッケージ
uuid: 4eec30cf-66b6-408d-985d-3e23b8b70d01
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# 認証パッケージ{#authentication-package}

ユーザーがアプリを操作できるように、認証パッケージをインストールしてユーザー認証を有効にします。

Livefyreアプリは、グローバル認証パッケージを使用して、ユーザーをアプリのアクションに関連付けます。 認証パッケージは、を通じて入手できま `Livefyre.require`す。

ページで認証を有効にするには、まずWebページまたはWebサ `Livefyre.js` イトのテン `<head>` プレートの要素に追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

Livefyre.requireを使用した認証の有効化は、他のパッケージを呼び出す際に必要となる機能と似ています。 認証を必要とする統合コードは次のようになります。

```
Livefyre.require(['auth'], function (auth) {  
// Perform action... 
});
```

## メソッド {#section_ojx_1lz_fz}

上記の使用方法を使用して追加さ `Livefyre.require`れると、認証モジュールは次のメソッドを公開し、認証関連のイベントに関して他のアプリに通知するために呼び出すことができます。

| メソッド | 説明 |
|--- |--- |
| `.login(callback)` | 登録されたAuthDelegateによって実装されたログインフローをトリガします。 通常、認証が有効なアプリのみがこれを呼び出し、ホストページ自体は呼び出しません。 |
| `.logout(callback)` | エンドユーザーが外部の手段でログアウトしたこと、および次回のログインまですべての証明書利用アプリケーションが認証状態をクリアする必要があることを認証に通知します。 これにより、Authが保持する内部セッションがクリアされます。 |
| `.authenticate(credentials)` | ユーザーが何らかの外部手段で認証され、エンドユーザー用にLivefyre認証トークンが入手されたことをAuthに通知します。 Livefyreトークンを使用してcookieを設定した場合、またはユーザー用のトークンがあり、ユーザーを明示的にログインする場合に、これを使用します。 For example: <br>`auth.authenticate({&nbsp;livefyre:&nbsp;`<br>`'<insert&nbsp;lftoken&nbsp;string&nbsp;for&nbsp;newly&nbsp;logged-in&nbsp;user>'&nbsp;});` |
| `.delegate(authDelegate)` | 認証の実装の詳細（カスタム認証フローなど）を定義したオブジェクトに委任します。 Livefyre Appsのインタラクティブ機能を有効にするには、ホストページで呼び出す必要があります。 |

