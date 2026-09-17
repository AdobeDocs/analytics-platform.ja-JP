---
title: Customer Journey Analytics Report Builder
description: Report Builderを使用してCustomer Journey Analytics データをExcelに取り込み、定期的なレポートを作成する方法について説明します。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 2%
---

# Report Builder

この記事では、[!DNL Report Builder]を使用して次の[ データ書き出しの使用例](overview.md)を実装する方法について説明します。

* アドホックレポートと定期的レポート

## はじめに

[!DNL Report Builder] [!DNL Report Builder]は、Customer Journey Analytics データをブックのデータ ブロックに取り込むMicrosoft Excel アドインです。 既にExcelに精通しているビジネスユーザーは、Analysis WorkspaceやSQLについて学ばなくても、定期的なレポートを作成できます。

## 詳細情報

[!DNL Report Builder]の各データブロックは、最大50,000行を返します。 より多くの行を取得するには、**[!UICONTROL ページ]**&#x200B;および&#x200B;**[!UICONTROL 行]** オプションを使用して、50,000行の制限を超えるシーケンシャルページのデータを取得します。 詳しくは、[ フィルターディメンション ](/help/report-builder/filter-dimensions.md)を参照してください。

電子メールで配信するブックをスケジュールしたり、Amazon S3、Google Cloud Platform、Azureなどのクラウドに書き出したりできます。 詳しくは、[電子メールを介した共有によるワークブックのスケジュール ](/help/report-builder/schedule-reportbuilder.md)および[ クラウド宛先への書き出しによるワークブックのスケジュール ](/help/report-builder/report-builder-export.md)を参照してください。

[!DNL Report Builder]の設定と使用の概要については、[Report Builderの概要](/help/report-builder/rb-overview.md)を参照してください。
