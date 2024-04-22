---
title: Customer Journey Analyticsへの移行の概要
description: Adobe AnalyticsからCustomer Journey Analyticsへの移行の計画
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: a23322ab189e6469783a179e2de7aa0195eda737
workflow-type: tm+mt
source-wordcount: '745'
ht-degree: 11%

---

# 手順 1:Customer Journey Analyticsへの移行の概要

Customer Journey Analyticsは次世代の分析です。 マルチチャネルデータ収集（オンラインデータとオフラインデータの両方）と、強力なレポート時間処理機能を組み合わせることができます（データビューでコンポーネントや派生フィールドを定義します）。

Adobe AnalyticsからCustomer Journey Analyticsへの移行プロセスを開始する前に、移行の利点とCustomer Journey Analyticsを正常に行うために必要な手順を理解する必要があります。

## Customer Journey Analyticsのメリットについて

主なメリットを次に示します。（これらの主な機能の概要と詳細については、を参照してください。 [Customer Journey Analyticsでのみ使用できる機能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics).）

* [マルチチャネルレポート](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。デジタル（Web）、POS （販売時点管理システム）、モバイル、CRM システムなど、複数のチャネルからのデータを収集してレポートします。

* [データビューでのレポート時間変換](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics のデータビューを使用すると、接続からのデータをさらに解釈できます。実装を変更せずにデータを変更または削除したり、部分文字列を使用してディメンションを操作したり、任意の値から指標を作成したり、サブ値をフィルタリングしたり、派生フィールドを使用したりできます。 これらの変換はすべて非破壊的です。

* [変換は、履歴データと新しいデータに適用されます](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  データビューの操作は、履歴データと新しいデータの両方に非破壊的に適用できます。

* [派生フィールド](/help/data-views/derived-fields/derived-fields.md)

  派生フィールドを使用すると、レポート時にデータを変換できます。データは、その場で結合、修正、作成し、すべてのレポートに対して遡って適用できます。

* [データビューが仮想レポートスイートを置き換える](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  データビューは、現在の仮想レポートスイートの概念をさらに拡大するものです。接続で使用可能になるデータを、さらに制御できるようになります。 これらの変更により、タイムゾーンやセッションのタイムアウト間隔などの一般的な設定が、設定したり遡及したりできるようになりました。

* [無制限の顧客ディメンションと指標](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  値には、数値、テキスト、オブジェクト、リスト、またはすべてが混在する場合があります。 Dimensionはネストまたは階層的にすることができます。

## 移行プロセスについて

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
このページは、次の表に示すように、移行のステップ 1 を表します。 Adobe AnalyticsからCustomer Journey Analyticsに移行するには、次の表のすべての手順を実行します。

| タスク | 詳細 |
|---------|----------|
| **手順 1: [移行の基本を学ぶ](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。 |
| **手順 2: [移行方法の選択](/help/getting-started/cja-migration/cja-migration-method.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 1 で選択した移行方法によって異なります。 |
| **手順 4: [XDM スキーマへのデータマッピングを計画します](/help/getting-started/cja-migration/cja-migration-xdm.md)** | [XDM スキーマ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home#xdm-schemas) は、Adobe Experience Platformで使用され、一貫した再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。<p>ほとんどの移行方法では、新しい XDM スキーマを作成するか、データストリームマッピングを使用して既存のAdobe Analytics スキーマを XDM にマッピングする必要があります。</p> |
| **手順 5: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 6: [ユーザーのオンボーディングの計画](/help/getting-started/cja-migration/cja-migration-onboarding.md)** | Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。 |
| **手順 7: [レポート API の使用状況を移植](/help/getting-started/cja-migration/cja-migration-api.md)** | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 8: [データフィードとData Warehouseの置き換え](/help/getting-started/cja-migration/cja-migration-export-options.md)** | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を置き換えるために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 |
| **手順 9: [プロジェクトとコンポーネントを移行する](/help/getting-started/cja-migration/cja-migration-projects.md)** | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。 |

{style="table-layout:auto"}

## まず、移行方法を選択します

Customer Journey Analyticsへの移行には様々な方法があります。 [組織に最適な方法を選択します](/help/getting-started/cja-migration/cja-migration-method.md).

どの移行方法を選択するかは、組織の現在のAdobe Analytics環境と長期目標によって異なります。