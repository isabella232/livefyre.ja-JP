---
description: サイト上のLivefyreのパワーに使用されるLivefyreライブラリ。
seo-description: サイト上のLivefyreのパワーに使用されるLivefyreライブラリ。
seo-title: Livefyre. js
solution: Experience Manager
title: Livefyre. js
uuid: 7b3eca57- d5e8-416d- badf- a9c51d10dadd
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652

---


# Livefyre. js {#livefyre-js}

サイト上のLivefyreのパワーに使用されるLivefyreライブラリ。

`Livefyre.js` は、Livefyre対応のすべてのWebページにインストールできるコアライブラリです。これはグローバル `window.Livefyre` オブジェクトと単一のパブリックメソッドを定義するもので、 `Livefyre.require`Livefyreアプリケーションの埋め込みに [役立つ他のLivefyre JavaScriptライブラリの読み込みに使用できます](/help/implementation/c-getting-started/c-implementation-process/c-using-livefyre.js-to-create-customize-and-use-apps-on-your-site.md)。 [また、LivefyreアプリケーションとLivefyre](/help/implementation/t-about-identity-integration/t-about-identity-integration.md) の統合にも使用できます。

## サイトに追加 {#section_cst_twg_xz}

WebページまたはWebサイトテンプレートに `<script>` 次のタグを追加します。可能であれば、HTMLドキュメントの `<head>` セクションに追加してすばやく読み込みます。

```
<script src="//cdn.livefyre.com/Livefyre.js"></script>
```

>[!NOTE]
>
>このスクリプトは、Livefyre. js scoutという非常に小さな（~1KB）ファイルを埋め込みます。このファイルは、Webページがアクセスされたプロトコル（HTTPまたはHTTPS）の最新バージョンのLivefyre. jsを読み込みます。

## Livefyre. require {#section_ipq_hwg_xz}

`Livefyre.require` は [、curl. js](https://github.com/cujojs/curl) や [requireJSのようなカスタムJavaScriptモジュールローダー](https://requirejs.org/)です。Livefyreによって公開されたパッケージの読み込みに使用でき、便利で直感的な統合パスを提供できます。

アクセス可能なパッケージは、セマンティック `Livefyre.require` のバージョニングを使用 [してバージョン管理](https://semver.org/)されます。パッケージは特定のバージョンまたはバージョンのバージョンで必要となるので、Webページの新しいバフ修正機能から自動的にメリットが得られます。これにより、Livefyreのサイトへの統合を柔軟に行うことができます。バージョンの固定には3つのレベル `Livefyre.require`があります。

* **package- name#1:** メジャーバージョンv1に固定します。後方互換性のあるAPIを維持する新しいアップデートをすべて取得します。バグ修正を受信するためのメジャーバージョンに固定し、そのバージョンの機能強化を行いました。
* **package- name#1.1:** マイナーバージョンv1.1に固定します。このマイナーバージョンに関するすべてのバグ修正を行います。デフォルトの動作または機能スコープの変更が、Webページで予期しない動作を引き起こす可能性がある場合、Livefyreエンジニアリングは常にマイナーバージョンのパッケージにバンプします。自動バグ修正を受信する場合は、マイナーバージョンにピン留めしますが、デフォルトの動作に対する追加の機能や変更はありません。
* **package- name#1.1.1:** 固定バージョンv1.1.1に固定します。バンフィックスがある場合でも、この埋め込みの動作は変更されません。変更可能なパッケージのマークアップ構造に依存するサイト向けの広範なCSSカスタマイズがある場合、または実行しているLivefyreバージョンが変更されないようにするには、パッチバージョンに固定します。

次に例 `Livefyre.require` を示します。

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

## 使用可能なパッケージ {#section_ygd_dwg_xz}

どのLivefyre JavaScriptパッケージを通じて利用できる `Livefyre.require`か。サポートされているパッケージと最新バージョンの最新のリストは、いつでも入手できます。 [packages.html](https://cdn.livefyre.com/packages.html).

## テストプレリリース版パッケージのテスト {#section_pgm_dpg_xz}

将来のバージョンのLivefyreパッケージをテストして、お客様のWebサイトで動作するか、お客様の要求で開発中の機能をテストすることが必要な場合があります。セマンティックバージョンの範囲を含めるだけでなく、プレリリースUAT環境を指定することもできます。

例えば、次の例では、コメント、ライブブログ、チャット `fyre.conv`アプリケーションのUATリリースが必要です。

```
Livefyre.require(['fyre.conv#uat'], callback); 
```
