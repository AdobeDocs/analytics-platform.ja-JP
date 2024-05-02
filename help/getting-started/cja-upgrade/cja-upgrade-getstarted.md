---
title: Customer Journey Analyticsへのアップグレードの概要
description: Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードを計画します
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: fd3b36ab-72c1-469a-b2c7-419813c82425
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 10%

---

# 手順 1:Customer Journey Analyticsへのアップグレードの概要

Customer Journey Analyticsは次世代の分析です。 マルチチャネルデータ収集（オンラインデータとオフラインデータの両方）と、強力なレポート時間処理機能を組み合わせることができます（データビューでコンポーネントや派生フィールドを定義します）。

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードのプロセスを開始する前に、Customer Journey Analyticsのメリットとアップグレードの成功に必要な手順を理解しておく必要があります。

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

## アップグレードプロセスについて

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 1 について説明します。 Adobe AnalyticsからCustomer Journey Analyticsにアップグレードするには、次の表に示すすべての手順を実行します。

| アップグレードタスク | 詳細 |
|---------|----------|
| <span class="preview">**手順 1：アップグレードの概要**</span> | <span class="preview">Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。</span> |
| **手順 2: [アップグレードパスの選択](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在のAdobe Analytics環境と長期目標に応じて、組織に最適な方法を選択します。 |
| **手順 3: [Adobe Experience Platformへのデータの送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4: [履歴データを保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの企業は、Adobe Analyticsの履歴データを一定期間保持する必要があります。 そのための様々なオプションが用意されています。 |
| **手順 5: [追加の実装タスクの実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>次のようなタスクがあります。</p><ul><li>他のデータのExperience Platform化</li><li>Platform データセットとCustomer Journey Analytics間の接続の作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとData Warehouseのアカウント</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーのオンボーディングの計画</li></ul> <p>詳しくは、を参照してください [Customer Journey Analyticsを開始する](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

## まず、アップグレードパスを選択します

Customer Journey Analyticsへのアップグレードには様々な方法があります。 [組織に最適な方法を選択します](/help/getting-started/cja-upgrade/cja-upgrade-path.md).

選択するアップグレードパスは、組織の現在のAdobe Analytics環境と長期目標によって異なります。
