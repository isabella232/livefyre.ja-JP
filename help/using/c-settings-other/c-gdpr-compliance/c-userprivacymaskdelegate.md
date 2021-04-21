---
description: ビデオマスクに表示される警告テキストは、を使用して変更できます。
title: userPrivacyMaskDelegate
translation-type: tm+mt
source-git-commit: a2449482e617939cfda7e367da34875bf187c4c9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 0%

---


# userPrivacyMaskDelegate{#userprivacymaskdelegate}

ビデオマスクに表示される警告テキストは、を使用して変更できます。

このテキストは、GDPR規制に準拠するために存在します。 ソースがプロキシをサポートしていない場合は、ユーザーがビデオをクリックしてそのソースから潜在的なトラッキングを承認しない限り、Livefyreはこのテキストとマスクをコンテンツに表示します。

`userPrivacyMaskDelegate`を使用しない場合、次のデフォルトのテキストが表示されます。

追加`userPrivacyMaskDelegate`を`userPrivacyOptOut`の後に置きます。 すべてのLivefyreのプライバシーフラグを、1つのLivefyreオブジェクトの一部として一度に追加できます。

`userPrivacyMaskDelegate`の使い方の例を以下に示します。

```
userPrivacyMaskDelegate: function () { 
    var container = document.createElement('div'); 
    var firstParagraph = document.createElement('p'); 
    firstParagraph.innerHTML = 'Text of first paragraph'; 
    var secondParagraph = document.createElement('p'); 
    secondParagraph.innerHTML = 'Text of second paragraph'; 
    container.appendChild(firstParagraph); 
    container.appendChild(secondParagraph); 
    return container; 
}
```
