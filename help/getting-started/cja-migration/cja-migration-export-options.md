---
title: Customer Journey Analyticsへの移行時にデータフィードとData Warehouseを置換
description: Adobe AnalyticsからCustomer Journey Analyticsへの移行の計画
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 3a99aed3-26b9-494f-aaf9-f8eaa2c2d88f
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 4%

---

# 手順 8:Customer Journey Analyticsへの移行時にデータフィードとData Warehouseを置き換える

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 8 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [XDM スキーマへのデータのマッピング](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行パスでは、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 4: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| <span class="preview">**手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)**</span> | <span class="preview">Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。</span> |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |
| **手順 10: [移行後のタスクの実行](/help/getting-started/cja-getting-started.md)** | 移行が完了したら、様々なタスクを実行する必要があります。これには、他のデータのExperience Platformへの取り込み、Platform データセットとCustomer Journey Analytics間の接続の作成、データビューの作成、Analysis Workspaceでのクロスチャネルデータのレポート方法の学習が含まれます。 |

{style="table-layout:auto"}

+++

現在、Adobe AnalyticsでデータフィードまたはData Warehouseを使用している場合、Customer Journey Analyticsで使用できる様々な書き出しオプションについては、次の表を参照してください。

| Adobe Analytics | Customer Journey Analytics |
|---------|----------|
| データフィード | データフィードのユースケースを評価してから、Customer Journey Analyticsで使用可能な別の書き出し方法を任意に組み合わせて使用します。 <ul><li>未加工データセットを書き出すには： [クラウドストレージの宛先へのデータセットの書き出し](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/export-datasets)..&#x200B;</li><li>ユーザー ID またはタイムスタンプを使用したオーディエンスレベルまたはイベントレベルの書き出しの場合、を使用します [テーブル全体の書き出し](/help/analysis-workspace/export/export-cloud.md)..&#x200B;</li><li>Power BIと Tableau を直接統合するには、を使用します [Customer Journey Analytics BI 拡張機能](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension)..&#x200B;</li><li>Adobe Experience Platformのデータに SQL で直接アクセスするには、 [Adobe Experience Platform クエリサービス](https://experienceleague.adobe.com/en/docs/experience-platform/query/home).</li></ul> |
| Data Warehouse | 使用するAdobe Analytics Data Warehouseの書き出しの変更 [テーブル全体の書き出し](/help/analysis-workspace/export/export-cloud.md) Customer Journey Analyticsで。<p>Customer Journey Analyticsの完全なテーブルの書き出しは、Adobe AnalyticsのData Warehouseレポートが進化したものです。現在、Data Warehouseでは利用できない、頻繁にリクエストされる多くの新機能を備えています。</p> |

{style="table-layout:auto"}

## 次に、プロジェクトとコンポーネントを移行します

Adobe Analyticsのコンポーネント移行領域を使用して、次の操作を行います [プロジェクトとその関連コンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md) Adobe AnalyticsからCustomer Journey Analyticsへ
