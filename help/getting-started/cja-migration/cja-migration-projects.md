---
title: Customer Journey Analyticsへのプロジェクトおよびコンポーネントの移行
description: プロジェクトとコンポーネントをCustomer Journey Analyticsに移行するためのコンポーネント移行について説明します。
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: da71e96749093821b49806c5a1bfd2f82ca85dd4
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 17%

---

# 手順 9：プロジェクトおよびコンポーネントをCustomer Journey Analyticsに移行する

+++このページの情報は、大規模な移行プロセスの一部です。 このセクションを展開すると、移行プロセス内でこの情報が収まる場所を確認できます。 </br></br>このページの情報を続行する前に、以前の移行手順をすべて完了する必要があります。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 9 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行方法の選択](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 1 で選択した移行方法によって異なります。 |
| **手順 4: [XDM スキーマへのデータマッピングを計画します](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行方法では、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| <span class="preview">**手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)**</span> | <span class="preview">Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。</span> |

{style="table-layout:auto"}

+++

Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。

移行プロセスには、次が含まれます。

* Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。

* Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。

移行を開始する前に、まず[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行する準備をします](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=ja)。

必要な準備をすべて整えたら、[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=ja)できます。