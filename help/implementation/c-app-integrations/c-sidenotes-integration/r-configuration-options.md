---
description: Sidenots configオブジェクトは、Livefyre Appがページ上でレンダリングするコンテンツを指定するために使用するJSONオブジェクトです。
seo-description: Sidenots configオブジェクトは、Livefyre Appがページ上でレンダリングするコンテンツを指定するために使用するJSONオブジェクトです。
seo-title: サイトの設定オプション
solution: Experience Manager
title: サイトの設定オプション
uuid: 067e51e6-9720-4226-a805-c7a07c8cdaa0
translation-type: tm+mt
source-git-commit: 67aeb3de964473b326c88c3a3f81ff48a6a12652
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 2%

---


# サイズ構成オプション{#sidenotes-configuration-options}

Sidenots configオブジェクトは、Livefyre Appがページ上でレンダリングするコンテンツを指定するために使用するJSONオブジェクトです。

このオブジェクトには次のパラメーターが含まれます。

| パラメーター | タイプ | 説明 |
|--- |--- |--- |
| authDelegate | ** requiredobject | 新しいまたは古いスタイルの初期化された認証委任。 |
| collectionMeta | ** requiredobject | 詳しくは、collectionMetaトークンを参照してください。 |
| customIcon | ** optionalstring | カスタムランチャーアイコンのURLを設定します。 初期設定はLivefyreバブルです。 |
| customStyles | ** optionalobject | カスタムスタイルを追加して、サイドの外観を変更します。 詳しくは、「カスタムスタイル」を参照してください。 |
| disableStream | ** optionalBoolean | trueの場合、（他のコメントストリーム内ではなく）このSidentインスタンス内のリアルタイムストリーミングを無効にします。 デフォルトは false です。 |
| 環境 | ** optionalstring | Livefyre UAT環境を指定します。 指定できる値は`t402.livefyre.com`のみです。 実稼働環境では、このパラメーターを削除する必要があります。 |
| iconVisibility | ** optionalobjectまたはstring | カーソルを合わせたときにサイドアイコンを表示するか、静的に表示するかを定義します。 これが文字列の場合は、ブロックアイコンの両方のバージョン（空白、サイド付き）に使用されます。 オブジェクトの場合は、次の各タイプを指定する必要があります。{empty:‘hover’, num:「static」}に置き換えます。 初期設定はstaticです。 |
| inlineThreads | ** optionalboolean | trueの場合、スレッドが関連付けられているブロックの直後に挿入されます。 デフォルトは false です。 |
| numSidentEl | ** optionalobject、string、またはarray | サイド数ウィジェットを装飾する要素を指定します。 （このウィジェットは、ページ上のサイトの数とサイトに関する情報を表示します）。 文字列セレクターが複数の要素と一致する場合は、最初の要素が選択されます。 （CSS3 DOMセレクター仕様を使用）。 |
| position | ** optionalstring | 「サイズ」が有効な要素をクリックした場合のポップアップの位置を決定します。 指定できる値は、「smart」、「left」、「right」、「bottom」です。 初期設定は「smart」で、十分なスペースがない場合（その場合はコンテンツの下に移動します）は、ポップアップをページの右に揃えます。 |
| セレクター | ** 必須オブジェクト、文字列、または配列 | ランチャーアイコンを表示する要素を指定します。 （CSS3 DOMセレクター仕様を使用）。 オブジェクトの場合、「含む」セクションと「除外する」セクションを含み、一致する「含む」に対してCSSセレクターを適用し、除外に一致する要素を削除します。 文字列の場合、一致する要素がページに含まれます。 配列の場合、含める要素をリストします。 |
| 文字列 | ** optionalobject | カスタムテキスト文字列を追加して、アプリケーション全体の任意の言語またはテキストを変更します。 詳しくは、「カスタム文字列」を参照してください。 |
| threadContainerEl | ** optionalobject、string、またはarray | サイドのねじを表示する要素を指定します。 このパラメーターを使用すると、ねじの位置を変更できます。 文字列セレクターが複数の要素と一致する場合は、最初の要素が選択されます。 （CSS3 DOMセレクター仕様を使用）。 |

