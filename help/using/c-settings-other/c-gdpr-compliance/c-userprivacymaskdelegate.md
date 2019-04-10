---
description: ビデオマスクに表示される警告テキストを変更できます。
seo-description: ビデオマスクに表示される警告テキストを変更できます。
seo-title: UserPrivacyMaskDelegate
solution: Experience Manager
title: UserPrivacyMaskDelegate
uuid: 8e5a2750- bf45-4e70- a5f9-37f5e7c61f8e
translation-type: tm+mt
source-git-commit: 566ea2587f101202045488e9f4edf73ece100293

---


# UserPrivacyMaskDelegate{#userprivacymaskdelegate}

ビデオマスクに表示される警告テキストを変更できます。

GDPR規則に準拠するためにこのテキストが存在します。ソースがプロキシをサポートしていない場合、ユーザーがビデオをクリックし、そのソースからの潜在的なトラッキングを承認しない限り、Livefyreはコンテンツにこのテキストとマスクを表示します。

使用 `userPrivacyMaskDelegate`しない場合、次のデフォルトのテキストが表示されます。

`userPrivacyMaskDelegate` 後 `userPrivacyOptOut`に追加Livefyreのプライバシーフラグはすべて1つのLivefyreオブジェクトの一部として追加できます。

`userPrivacyMaskDelegate`以下に、使用例を示します。

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
