---
title: Customer Journey Analyticsへの移行の概要
description: Adobe AnalyticsからCustomer Journey Analyticsへの移行の計画
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: d734e5daf9b5c9a559c0390622ab5aa15f2aa7a2
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 10%

---

# 手順 1:Customer Journey Analyticsへの移行の概要

Customer Journey Analyticsは次世代の分析です。 マルチチャネルデータ収集（オンラインデータとオフラインデータの両方）と、強力なレポート時間処理機能を組み合わせることができます（データビューでコンポーネントや派生フィールドを定義します）。

Adobe AnalyticsからCustomer Journey Analyticsへの移行プロセスを開始する前に、移行のメリットとCustomer Journey Analyticsを成功させるために必要な手順を理解する必要があります。

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
このページの情報では、次の表で強調表示されている、移行の手順 1 について説明します。 Adobe AnalyticsからCustomer Journey Analyticsに移行するには、次の表のすべての手順を実行します。

| 移行タスク | 詳細 |
|---------|----------|
| <span class="preview">**手順 1：移行の概要**</span> | <span class="preview">Adobe Analyticsへの移行のメリットと基本的な移行プロセスについて説明します。</span> |
| **手順 2: [移行パスを選択](/help/getting-started/cja-migration/cja-migration-path.md)** | Customer Journey Analyticsへの移行には様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択した移行パスによって異なります。 |
| **手順 4: [履歴データを保持](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | Customer Journey Analyticsプロセスのこの時点では、移行に使用する準備が整う前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからの移行と、新しいCustomer Journey Analytics実装に当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## まず、移行パスを選択します。

Customer Journey Analyticsへの移行には様々な方法があります。 [組織に最適な方法を選択します](/help/getting-started/cja-migration/cja-migration-path.md).

どの移行パスを選択するかは、組織の現在のAdobe Analytics環境と長期目標によって異なります。
