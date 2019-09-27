---
cloud: Experience Cloud
solution-title: 学習とサポート
solution-hub-url: https://helpx.adobe.com/support/experience-manager/6-4.html
solution-icon: assets/experience-cloud-logo-24.png
getting-started-title: 導入
getting-started-url: https://docs.adobe.com/content/help/en/livefyre/implementation/c-getting-started/implementation-process/c-implementation-process.html
tutorials-title: チュートリアル
tutorials-url: https://helpx.adobe.com/experience-manager/kt/index/aem-6-4-videos.html
mini-toc-levels: '2'
git-repo: https://github.com/AdobeDocs/livefyre.en
translation-type: tm+mt
source-git-commit: 170fa6b446345d5e2e272294a3267d1ebbb0cd09

---


# 内部使用のためのメタデータ

metadata.mdファイルには、リポジトリ内のユーザガイドTOC.mdファイルに渡すリポジトリレベルのメタデータが含まれます。 ユーザガイドのmetadata.mdコンテンツを変更する場合は、任意のTOC.mdファイルで変更します。

| メタデータ | 役割 |
|--- |--- |
| 解決権 | 記事のヘッダーにリンクとして使用 |
| solution-hub-url | Opens helpx hub page |
| solution-icon | Displays solution icon next to solution title. Not yet implemented |
| getting-started-url | Link to helpx getting started page |
| tutorials-url | Link to video tutorials--either helpx tutorials or KT tutorials |
| mini-toc-levels | Determines the number of heading levels that appear in right rail. デフォルトは 2 です。 |
| git-repo | Specifies the location of the master repo for internal use |

TOC.mdファイル内

| メタデータ | 役割 |
|--- |--- |
| user-guide-title | Used in article header as link |
| user-guide-url | helpxハブページを開きます |
