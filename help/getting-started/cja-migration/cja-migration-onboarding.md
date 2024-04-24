---
title: Customer Journey Analyticsへの移行時のユーザーのオンボーディングの計画
description: Customer Journey Analyticsへの移行時のユーザーのオンボーディングの計画
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 34ccab37-a37f-4d69-aa96-ae1047b1f195
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 3%

---

# 手順 6:Customer Journey Analyticsへの移行時にユーザーのオンボーディングを計画

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 6 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [XDM スキーマへのデータのマッピング](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行パスでは、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 4: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| <span class="preview">**手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)**</span> | <span class="preview">Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。</span> |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |

{style="table-layout:auto"}

+++

Customer Journey AnalyticsとAdobe Analyticsには、ユーザーが注意する必要がある主な違いがいくつかあります。

Adobe Analyticsと同様、Analysis WorkspaceはCustomer Journey Analyticsの主要なユーザーフェイシングツールです。 ただし、Customer Journey AnalyticsでAnalysis Workspaceを使用する際には、注意が必要ないくつかの重要な違いがあります。

Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。

Adobe AnalyticsとCustomer Journey Analyticsの主な違いについては、次を参照してください。 [Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md).

## 次に、レポート API 使用量を移植します

Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md) Adobe Analytics レポート API からCustomer Journey Analyticsレポート API に。
