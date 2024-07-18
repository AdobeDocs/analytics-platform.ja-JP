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
ht-degree: 63%

---

# 手順 1:Customer Journey Analyticsへのアップグレードの概要

Customer Journey Analytics は、次世代の分析です。強力なレポート時処理機能（データビューでのコンポーネントと派生フィールドの定義を通じて）と組み合わせて、マルチチャネルデータ収集（オンラインデータとオフラインデータの両方）を実現できます。

Adobe AnalyticsからCustomer Journey Analyticsへのアップグレードのプロセスを開始する前に、Customer Journey Analyticsのメリットとアップグレードの成功に必要な手順を理解しておく必要があります。

## Customer Journey Analytics のメリットについて

主なメリットには、次のようなものがあります（包括的なリストと、これらの主な機能のそれぞれについて詳しくは、[Customer Journey Analytics でのみ利用可能な機能](/help/getting-started/aa-vs-cja/cja-aa.md#adobe-customer-journey-analytics-features-not-available-in-adobe-analytics)を参照してください）。

* [マルチチャネルレポート](/help/getting-started/aa-to-cja-user.md#changes-to-data-architecture)

  Customer Journey Analytics は、あらゆる種類のデータスキーマとタイプを保持する Experience Platform の機能と組み合わされています。デジタル（Web）、POS（販売時点情報管理）システム、モバイル、CRM システムなどの複数のチャネルからデータを収集してレポートします。

* [データビューでのレポート時の変換](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md#customer-journey-analytics-data-views)

  Customer Journey Analytics のデータビューを使用すると、接続からのデータをさらに深く解釈できます。実装を変更せずにデータを変更または削除、部分文字列を使用してディメンションを操作、任意の値から指標を作成、サブイベントをフィルタリング、または派生フィールドを使用できます。これらの変換はすべて非破壊的に行われます。

* [変換は履歴データと新規データに適用されます](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)

  データビューの操作は、履歴データにも新しいデータにも、非破壊で適用できます。

* [派生フィールド](/help/data-views/derived-fields/derived-fields.md)

  派生フィールドを使用すると、レポート時にデータを変換できます。データは、その場で結合、修正、作成し、すべてのレポートに対して遡って適用できます。

* [データビューは仮想レポートスイートを置き換えます](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-virtual-report-suites)

  データビューは、現在存在する仮想レポートスイートの概念を取り入れ、これを拡張して、接続によって利用できるデータに対する追加の制御を有効にします。これらの変更により、タイムゾーンやセッションのタイムアウト間隔などの一般的な設定が設定可能になり、遡って適用できるようになります。

* [無制限の顧客ディメンションと指標](/help/getting-started/aa-to-cja-user.md#changes-to-the-concept-of-evars-and-props)

  値には、数値、テキスト、オブジェクト、リスト、すべての組み合わせを使用できます。ディメンションはネストまたは階層化できます。

## アップグレードプロセスについて

<!-- Include a graphic of the end-to-end process, as well as links to each step of the process -->
このページの情報では、次の表で強調表示されている、アップグレードプロセスの手順 1 について説明します。 Adobe AnalyticsからCustomer Journey Analyticsにアップグレードするには、次の表に示すすべての手順を実行します。

| アップグレードタスク | 詳細 |
|---------|----------|
| <span class="preview">**手順 1：アップグレードの概要**</span> | <span class="preview">Customer Journey Analyticsへのアップグレードのメリットと基本的なアップグレードプロセスについて説明します。</span> |
| **手順 2:[ アップグレードパスを選択する](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Customer Journey Analyticsへのアップグレードには様々な方法があります。 組織の現在の Adobe Analytics 環境と長期的な目標に応じて、組織に最適な方法を選択してください。 |
| **手順 3：[データを Adobe Experience Platform に送信](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Adobe Experience Platformにデータを送信するプロセスは、手順 2 で選択したアップグレードパスによって異なります。 |
| **手順 4：[履歴データの保持](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | ほとんどの組織では、Adobe Analytics の履歴データを一定期間保持する必要があります。これを実現するために様々なオプションが利用できます。 |
| **手順 5：[追加の実装タスクを実行](/help/getting-started/cja-getting-started.md)** | アップグレードプロセスのこの時点では、Customer Journey Analytics環境を使用する準備を整える前に、様々なタスクを実行する必要があります。<p>これらの追加タスクは、Adobe Analyticsからのアップグレードや、新しいCustomer Journey Analyticsの実装にも当てはまります。</p><p>これらのタスクには次のものが含まれます。</p><ul><li>他のデータを Experience Platform に取り込む</li><li>手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続を作成</li><li>データビューの作成</li><li>レポート API の使用状況の移植</li><li>データフィードとデータウェアハウスの考慮</li><li>プロジェクトとコンポーネントの移行</li><li>ユーザーオンボーディングの計画</li></ul> <p>詳しくは、[Customer Journey Analytics の概要](/help/getting-started/cja-getting-started.md)を参照してください。 |

{style="table-layout:auto"}

## まず、アップグレードパスを選択します

Customer Journey Analyticsへのアップグレードには様々な方法があります。 [組織に最適な方法を選択します](/help/getting-started/cja-upgrade/cja-upgrade-path.md)。

選択するアップグレードパスは、組織の現在のAdobe Analytics環境と長期目標によって異なります。
