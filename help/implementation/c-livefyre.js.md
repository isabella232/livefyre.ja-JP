---
description: サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。
seo-description: サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。
seo-title: Livefyre.js
solution: Experience Manager
title: Livefyre.js
uuid: 7b3eca57-d5e8-416d-badf-a9c51d10dadd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---


# Livefyre.js {#livefyre-js}

サイトでLivefyreの電源を投入するために使用するコアLivefyreライブラリ。

`Livefyre.js` は、Livefyre対応のすべてのwebページにインストールできるコアライブラリです。グローバル`window.Livefyre`オブジェクトと単一のパブリックメソッド`Livefyre.require`を定義します。これは、[Livefyre Apps](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)の埋め込み、[Livefyre](/help/implementation/t-about-identity-integration/t-about-identity-integration.md)との認証プロバイダーの統合などに役立つ他のLivefyre JavaScriptライブラリの読み込みに使用できます。

## サイト追加{#section_cst_twg_xz}に

次の追加`<script>`タグをwebページまたはWebサイトテンプレートに追加します。 可能であれば、HTMLドキュメントの`<head>`セクションに追加して、すばやく読み込むようにします。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

>[!NOTE]
>
>このスクリプトでは、Livefyre.jsスカウトと呼ばれる非常に小さな(1 KB)ファイルを埋め込みます。このファイルは、Livefyre.jsの最新バージョンを、Webページにアクセスされたプロトコル（HTTPまたはHTTPS）経由で読み込みます。

## Livefyre.require {#section_ipq_hwg_xz}

`Livefyre.require` は、 [curl.jsor RequireJSなどのカスタムJavaScriptモジュールローダー](https://github.com/cujojs/curl)  [](https://requirejs.org/)です。Livefyreによって公開されたほとんどのパッケージを読み込んで、使いやすく直観的な統合パスを提供するのに使用できます。

`Livefyre.require`経由でアクセス可能なパッケージは、[セマンティックのバージョン管理](https://semver.org/)を使用してバージョン付けされます。 パッケージは、特定のバージョンまたは特定のバージョンの範囲に必要となる場合があり、Webページで新しいバグ修正機能が自動的に利用できるようになります。 これにより、サイトでLivefyreを統合する際に柔軟性が高まります。 `Livefyre.require`で使用できるバージョンの固定には3つのレベルがあります。

* **package-name#1：メジャーバージョンv1に** 固定します。下位互換性のあるAPIを維持する新しいアップデートがすべて入手できます。 メジャーバージョンに固定すると、そのバージョンのバグ修正とマイナー機能の拡張を受け取ることができます。
* **package-name#1.1：マイナーバージョンv1.1に** 固定します。このマイナーバージョンに対するバグ修正はすべて行われます。Webページ上で新しく予期しない動作が発生する可能性があるようにパッケージのデフォルトの動作や機能範囲が変化した場合、Livefyre Engineeringは常にマイナーバージョンのパッケージをぶつけます。 自動バグ修正を受け取りたいが、デフォルト動作の追加機能や変更は受け取りたくない場合は、マイナーバージョンに固定します。
* **package-name#1.1.1：バージョンv1.1.1にパッチを適用します。バグ修正があっても、この埋め込みの動作は変わりません。** 変更される可能性のあるパッケージのマークアップ構造に依存する、サイトを広範にCSSをカスタマイズしている場合、または実行中のLivefyreバージョンが変更されないことを望む他の理由がある場合は、パッチバージョンに固定します。

`Livefyre.require`を使用した統合の例を次に示します。

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

## 利用可能なパッケージ{#section_ygd_dwg_xz}

`Livefyre.require`を通じてどのLivefyre JavaScriptパッケージが利用できるか不思議に思う サポート対象のパッケージと最新リストは、次の場所で常に確認できます。[packages.html](https://cdn.livefyre.com/packages.html).

## リリース前のパッケージのバージョンのテスト{#section_pgm_dpg_xz}

Livefyreパッケージの今後のバージョンをテストして、Webサイトで動作することを確認したり、リクエストに応じて開発される機能の受け入れテストを行ったりしたい場合があります。 セマンティックバージョン範囲を含める以外に、プレリリースUAT環境を指定できます。

例えば、次の例では、`fyre.conv`のUATリリース、コメント、Live Blog、Chatアプリケーションが必要です。

```
Livefyre.require(['fyre.conv#uat'], callback); 
```
