---
title: Customer Journey Analyticsへの移行時にAdobe Experience Platformにデータを送信
description: Customer Journey Analyticsへの移行時にAdobe Experience Platformにデータを送信
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 3e362a62d2ffd6d15e3028706e3704264df80222
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 3%

---

# 手順 3:Customer Journey Analyticsへの移行時にAdobe Experience Platformにデータを送信する

+++このセクションを展開すると、このページの情報が大規模な移行プロセスのどこに適合するかを確認できます。 以前の移行手順がすべて完了していることを確認します。

この節を続行する前に、まず、以前のすべての移行タスクを完了していることを確認してください。

このページの情報では、次の表で強調表示されている手順 3 について説明します。

| 移行タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行方法の選択](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| <span class="preview">**手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)**</span> | <span class="preview">Adobe Experience Platformにデータを送信するプロセスは、手順 1 で選択した移行方法によって異なります。</span> |
| **手順 4: [XDM スキーマへのデータのマッピング](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行方法では、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |

{style="table-layout:auto"}

+++


お先に [移行方法の選択](#step-2-choose-your-customer-journey-analytics-migration-method) 組織に最適な方法は、Adobe Experience Platformへのデータの送信を開始して、Customer Journey Analyticsで利用できるようにすることです。

以下に、各移行方式でExperience Platformにデータを送信するプロセスを示します。 詳しくは、以下の表に示すリンクを参照してください。

| 移行方法 | Platform へのデータ送信プロセス |
|---------|----------|
| Web SDK の新しい実装 | これは Web SDK の新しい実装なので、に記載されているすべての手順に従う必要があります [Adobe Experience Platform Web SDK を使用したデータの取り込み](/help/data-ingestion/aepwebsdk.md). |
| Web SDK を使用するようにAdobe Analytics実装を移行する | Adobe Analytics Web SDK に移行する手順は、現在の実装が Analytics 拡張機能かAppMeasurementかによって異なります。 <p>Analytics タグ拡張機能を使用している場合： [Adobe Analyticsのタグ拡張機能から Web SDK のタグ拡張機能への移行](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</p><p>または</p><p>AppMeasurementを使用している場合： [AppMeasurementから Web SDK への移行](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk) |
| 既存のAdobe Analytics Web SDK 実装を設定し、データをCustomer Journey Analyticsに送信します | Adobe Analyticsの実装は既に Web SDK を使用しているので、次の操作のみ必要です [データストリームの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream). その他のセクションは無視できます [Adobe Experience Platform Web SDK を使用したデータの取り込み](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk). |
| Analytics ソースコネクタ | [従来の Adobe Analytics からのデータの取り込みと使用](/help/data-ingestion/analytics.md) |

## 次に、XDM スキーマへのデータのマッピング

上の表に記載されているリンクをたどってExperience Platformにデータを送信した後、次の操作が必要になる場合があります [xdm スキーマへのデータのマッピング](/help/getting-started/cja-migration/cja-migration-xdm.md)選択した実装方法によって異なります。

次の実装方法では、データを XDM スキーマにマッピングする必要があります。

* Adobe Analyticsのタグ拡張機能から Web SDK のタグ拡張機能への移行

* 既存のAdobe Analytics Web SDK 実装を設定し、データをCustomer Journey Analyticsに送信します

または、Web SDK の新しい実装を行うことを選択した場合、既にマッピングは必要ありません [新しい XDM スキーマの設定](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema) 新しい実装の一環として。

移行に Analytics ソースコネクタを使用することを選択した場合は、マッピングは必要ありません。これは、Analytics ソースコネクタが XDM スキーマではなく既存のAdobe Analytics スキーマを使用するからです。
