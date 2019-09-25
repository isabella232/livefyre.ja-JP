---
description: サイトでLivefyreを動力付与するために使用するコアLivefyreライブラリ。
seo-description: サイトでLivefyreを動力付与するために使用するコアLivefyreライブラリ。
seo-title: Livefyre.js
solution: Experience Manager
title: Livefyre.js
uuid: 7b3eca57-d5e8-416d-badf-a9c51d10dadd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre.js {#livefyre-js}

サイトでLivefyreを動力付与するために使用するコアLivefyreライブラリ。

`Livefyre.js` は、Livefyre対応のすべてのWebページにインストールできるコアライブラリです。 これは、グローバ `window.Livefyre` ルオブジェクトと単一のパブリックメソッドを定義します。このメソッドを使用して、 `Livefyre.require`Livefyre Appsの埋め込み、Livefyre [とLivefyre](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)などの認証プロバイダーの統合に役立つ他のLivefyre javaScriptライブラリを読み込むことができます [](/help/implementation/t-about-identity-integration/t-about-identity-integration.md) 。

## サイトに追加 {#section_cst_twg_xz}

次のタグをWebページま `<script>` たはWebサイトのテンプレートに追加します。 可能であれば、HTMLドキュメントのセ `<head>` クションに追加して、すばやく読み込めるようにします。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

>[!NOTE]
>
>このスクリプトは、Livefyre.jsスカウトと呼ばれる非常に小さな(1 KB)ファイルを埋め込み、その後、Webページにアクセスしたプロトコル（HTTPまたはHTTPS）を使用して最新バージョンのLivefyre.jsを読み込みます。

## Livefyre.require {#section_ipq_hwg_xz}

`Livefyre.require` は、 [curl.jsやRequireJSなどのカスタムJavaScriptモジュールローダ](https://github.com/cujojs/curl)[ーです](https://requirejs.org/)。 Livefyreによって公開されたほとんどのパッケージを読み込んで、使いやすく直観的な統合パスを表示するのに使用できます。

を通じてアクセス可能なパッケージは、セ `Livefyre.require` マンティックバージョン管理を [使用してバージョン管理されま](https://semver.org/)す。 パッケージは、特定のバージョンまたは特定のバージョンの範囲に必要になる場合があり、新しいバグ修正機能を利用してWebページを自動的に利用できます。 これにより、Livefyreをサイトに統合する際に柔軟性が得られます。 で使用できるバージョンの固定には3つのレベルがありま `Livefyre.require`す。

* **** package-name#1:メジャーバージョンv1にピン留めします。 下位互換性のあるAPIを維持する新しいアップデートがすべて入手できます。 メジャーバージョンにピン留めして、そのバージョンのバグ修正とマイナー機能の強化を受け取ります。
* **** package-name#1.1:マイナーバージョンv1.1にピン留めします。このマイナーバージョンに関するバグ修正はすべて行われます。 Livefyre Engineeringは、Webページ上で新しい予期しない動作を引き起こす可能性のある方法でパッケージのデフォルトの動作や機能範囲が変更された場合、常にマイナーバージョンのパッケージをバンプします。 自動バグ修正を受け取り、デフォルト動作の追加機能や変更を受け取らない場合は、マイナーバージョンに固定します。
* **** package-name#1.1.1:パッチバージョンv1.1.1にピン留めします。この埋め込みの動作は、バグ修正があっても変更されません。 変更される可能性のあるパッケージのマークアップ構造に依存するCSSを広範にカスタマイズしている場合や、実行中のLivefyreバージョンが変更されないようにする理由が他にある場合は、パッチバージョンに固定します。

を使用した統合の例を次 `Livefyre.require` に示します。

```
<!-- First add Livefyre.js to the page --> 
<script src="https://cdn.livefyre.com/Livefyre.js"></script> 
  
<!-- Then load up all the desired Livefyre packages and Do Stuff in the callback --> 
<script> 
Livefyre.require([ 
    'lfawesome#1', 
    'lfsuperawesome#2.1.2' 
], function (LFAwesome, LFSuperAwesome) { 
    var greatness = new LFAwesome(); 
    // etc.. 
}); 
</script>
```

## 利用可能なパッケージ {#section_ygd_dwg_xz}

どのLivefyre javaScriptパッケージを通じて入手できるか不思議に思う `Livefyre.require`場合 サポートされているパッケージとその最新バージョンの一覧は、次のURLからいつでも入手できます。 [packages.html](https://cdn.livefyre.com/packages.html).

## パッケージのプレリリースバージョンのテスト {#section_pgm_dpg_xz}

Livefyreパッケージの今後のバージョンをテストして、Webサイト上で動作することを確認したり、要求に応じて開発される機能の受け入れテストを行ったりする場合があります。 セマンティックバージョン範囲を含める以外に、プレリリースUAT環境を指定できます。

例えば、次の例では、UATリリースの、コメント、ラ `fyre.conv`イブブログ、およびチャットアプリケーションが必要です。

```
Livefyre.require(['fyre.conv#uat'], callback); 
```
