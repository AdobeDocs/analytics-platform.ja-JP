---
title: Customer Journey Analytics の用語集
description: Customer Journey Analytics の用語集。
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 100%

---

# Customer Journey Analytics の用語集

Customer Journey Analytics の用語には、Adobe Analytics でこれまで使用されていた用語と異なるものがあります。

| 新しい Customer Journey Analytics の用語 | Adobe Analytics の用語 | 説明 |
|---|---|---|
| ルックアップデータセット | 分類 | 1 対 1の関係があるキーと一致キー（イベントデータセット内）の値を、指定したデータセットから取得する場合に、ルックアップを使用します。例えば、イベントデータセット内の「tracking_code」に一致するキーとして「tracking_code」を指定できます。 |
| Profile データセット | 顧客属性 | エンタープライズ顧客データを顧客関係管理（CRM）データベースに取り込んでいる場合は、そのデータを Adobe Experience Platform の Profile デーアセットにアップロードできます。Customer Journey Analytics でそのデータセットへの接続を作成し、データビューを作成したら、Workspace でそのデータを利用できます。 |
| ログイン会社 | Experience Cloud 組織 | [組織とアカウントのリンク](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=ja#topic_C31CB834F109465A82ED57FF0563B3F1)を参照してください。 |
| 該当なし | レポートスイート | 従来の Adobe Analytics のレポートスイートは存在しなくなりました。代わりに、接続を確立した Platform データセットから（仮想）[データビュー](/help/data-views/create-dataview.md)を作成します。 |
| フィルター | セグメント | セグメントはフィルターになりました。Customer Journey Analytics のフィルターは、セグメントと同じように動作します。用語のみが変更されました。 |
| データビュー | 仮想レポートスイート | Adobe Analytics では、仮想レポートスイートは親レポートスイートのフィルターされたビューになります。 仮想レポートスイートと CJA におけるデータビューの主な違いは、仮想レポートスイートが「ベース」または「親」レポートスイートのサブセットであり、その設定の一部が継承される点です。親／基本レポートスイートは存在しなくなるので、独自の設定でデータビューを定義します。 |

## Adobe Experience Platform の用語

Adobe Experience Platform は、企業全体のデータとコンテンツを標準化、リアルタイムの消費者プロファイルを強化、データサイエンスを可能にし、コンテンツの速度を向上させて、カスタマージャーニーをまたいだエクスペリエンスのパーソナライゼーションを促進します。
詳しくは、[Adobe Experience Platform の用語](https://docs.adobe.com/content/help/ja-JP/experience-platform/landing/glossary.html)を参照してください。
