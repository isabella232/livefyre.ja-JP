---
description: チェックリストの手順に従って、HTTPからHTTPSへの変換が正常に行われることを確認します。
title: SSLチェックリスト
exl-id: 20161aa5-57c9-417b-af0e-c9e1e771f861
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# SSLチェックリスト{#ssl-checklist}

チェックリストの手順に従って、HTTPからHTTPSへの変換が正常に行われることを確認します。

次の項目が完了すると、HTTPからHTTPSに正常に変換されます。

* サーバー間統合では、すべてHTTPSを使用します。
* サーバー間統合のすべてでTLS 1.2暗号がサポートされています。
* すべてのモバイルアプリでHTTPSが使用されています。
* すべてのモバイルアプリでTLS 1.2暗号がサポートされています。
* カスタムのJavaScript統合（StreamhubSDKまたは直接APIを使用）では、すべてHTTPSを使用しています。
* Livefyre JavaScriptをバンドルした場合は、最新バージョンを使用しています。
* サードパーティのサービス（コンテンツ分析、モデレートなど）を通知しました。 これらの変更に代わってLivefyre APIを使用する
