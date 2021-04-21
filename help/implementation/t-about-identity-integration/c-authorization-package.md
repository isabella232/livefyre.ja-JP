---
description: ユーザーがアプリを操作できるように、認証パッケージをインストールしてユーザー認証を有効にします。
title: 認証パッケージ
exl-id: 639032ee-ed7d-4cb0-83ba-f11d3dc607b6
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 1%

---

# 認証パッケージ{#authentication-package}

ユーザーがアプリを操作できるように、認証パッケージをインストールしてユーザー認証を有効にします。

Livefyreアプリでは、グローバル認証パッケージを使用して、ユーザーをアプリのアクションに関連付けます。 認証パッケージは`Livefyre.require`から入手できます。

ページで認証を有効にするには、まずWebページまたはWebサイトテンプレートの`<head>`要素に`Livefyre.js`を追加します。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

Livefyre.requireを使用して認証を有効にする方法は、他のパッケージを呼び出すためのrequireを使用する方法と似ています。 認証を必要とする統合コードは次のようになります。

```
Livefyre.require(['auth'], function (auth) {  
// Perform action... 
});
```

## メソッド {#section_ojx_1lz_fz}

`Livefyre.require`を使用して上記のように組み込まれると、認証モジュールは次のメソッドを公開し、このメソッドを呼び出して、認証関連のイベントをページ上の他のアプリに通知できます。

| メソッド | 説明 |
|--- |--- |
| `.login(callback)` | 登録されたAuthDelegateが実装するログインフローのトリガー。 通常は、認証が有効なアプリだけがこの呼び出しを行い、ホストページ自体は呼び出しません。 |
| `.logout(callback)` | エンドユーザーが外部の手段でログアウトしたこと、およびすべての証明書利用アプリが次回のログインまで認証状態をクリアする必要があることを認証に通知します。 これにより、Authが管理する内部セッションがクリアされます。 |
| `.authenticate(credentials)` | ユーザーが外部の方法で認証され、エンドユーザー用にLivefyre認証トークンが入手されたことを認証済みに通知します。 Livefyreトークンに対してcookieを設定する場合、またはユーザー用のトークンを持っていて、ユーザーを明示的にログインする場合に、これを使用します。 例えば、<br>`auth.authenticate({&nbsp;livefyre:&nbsp;`<br>`'<insert&nbsp;lftoken&nbsp;string&nbsp;for&nbsp;newly&nbsp;logged-in&nbsp;user>'&nbsp;});` |
| `.delegate(authDelegate)` | 認証の実装の詳細（カスタム認証フローなど）を、定義したオブジェクトに委任します。 Livefyre Appsのインタラクティブ機能を有効にするには、このメソッドをホストページで呼び出す必要があります。 |
