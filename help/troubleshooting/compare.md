---
title: Analytics Source Connector データとAdobe Analyticsの比較
description: Adobe AnalyticsとCustomer Journey Analyticsで同様のレポートを表示する際のデータの違いについて説明します。
role: Data Engineer, Data Architect, Admin
solution: Customer Journey Analytics
exl-id: dd273c71-fb5b-459f-b593-1aa5f3e897d2
feature: Troubleshooting
keywords: クエリサービス;クエリサービス;SQL 構文
source-git-commit: d96404479aabe6020566e693245879b5ad4fad9c
workflow-type: tm+mt
source-wordcount: '720'
ht-degree: 4%

---

# Analytics Source Connector データとAdobe Analyticsの比較

Customer Journey Analyticsを採用する場合、Adobe AnalyticsとCustomer Journey Analyticsの間でデータの違いがいくつかあることに気付くことがあります。 これらの違いは正常であり、いくつかの理由で発生する可能性があります。 Customer Journey Analyticsは、Adobe Analyticsのデータに関する制限の一部を改善できるように設計されています。 この柔軟性により、Customer Journey Analyticsでのデータの解釈方法に多少の違いが生じる可能性があります。 この記事では、Customer Journey AnalyticsとAdobe Analyticsでのデータの処理方法に関する潜在的な違いを説明します。

ここでは、[Analytics ソースコネクタ &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) を使用してAdobe Analytics データをAdobe Experience Platformに取り込んだあと、Customer Journey Analyticsで [&#x200B; 接続 &#x200B;](/help/connections/overview.md) および [&#x200B; データビュー &#x200B;](/help/data-views/data-views.md) を作成したことを前提としています。

![データは、Adobe Analytics からデータコネクタを経由して Adobe Experience Platform に、CJA 接続を使用して Custoer Journey Analytics に送られます。](assets/compare.png)

レポートプラットフォーム間でデータが異なる可能性がある次の理由を考慮してください。

* **異なるデータセットまたはレポートスイート**:Adobe Analyticsのレポートスイートと、Source コネクタからデータが派生するレポートスイートが同じであることを確認します。
* **カレンダー設定**:Adobe Analyticsのレポートスイートには、設定可能なタイムゾーンやその他のカレンダー設定が含まれています。 同様に、Customer Journey Analyticsのデータビューには、制御可能な別の設定があります。 パリティが必要な場合は、製品間でこれらの設定が一致していることを確認してください。
* **追加のデータセット**:Customer Journey Analyticsでは、1 つの接続内に複数のデータセットを含めることができます。 これらの違いには、追加のイベントデータセット、プロファイルデータセット、ルックアップデータセットなどが含まれます。 この機能は、Adobe AnalyticsとCustomer Journey Analyticsの重要な差別化要因であり、insightをクロスチャネルデータに変えることができます。
* **ステッチされたデータセット**:Adobeには、2 つのデータセット間で人物 ID を分析する機能が用意されており、その結果、ステッチされた ID を含む新しいデータセットが作成されます。 これらの [&#x200B; ステッチされたデータセット &#x200B;](/help/stitching/overview.md) には、Adobe Analytics レポートスイートで提供される以外の追加データが含まれます。
* **データソース**:Customer Journey Analyticsには、概要データソースやトランザクション ID データソースなど、Adobe Analytics レポートスイートにアップロードされた [&#x200B; データソース &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/import/data-sources/overview) は含まれていません。
* **Dimensionと指標の設定**：データビュー内では、すべてのディメンションと指標には、組織で変更できる独自の設定が含まれています。 これらの変更はレポートの実行時に適用されるので、遡及的に適用されます。 Adobe AnalyticsのDimensionと指標の設定によってデータの収集方法が変わり、その後変更が加えられます。 いずれかの製品でコンポーネント設定を変更すると、レポートの違いが生じる可能性があります。 特定のディメンションに焦点を当てる場合は、アトリビューションと永続性の設定がAdobe AnalyticsとCustomer Journey Analyticsの間で一致していることを確認してください。

  >[!TIP]
  >
  >Adobeでは、Adobe Analyticsのディメンションで「最新（最後）  の配分を使用することを強くお勧めします。 この配分設定により、Customer Journey Analyticsでのアトリビューションの柔軟性が大幅に向上します。

* **訪問定義**：個々のディメンションと指標の設定に加えて、データビュー自体には、訪問者データの解釈方法を根本的に変更する設定が含まれています。 例えば、データビュー全体（Adobe Analyticsの [&#x200B; 仮想レポートスイート &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/components/virtual-report-suites/vrs-about) と同様）にセグメントを適用できます。 また、訪問期間の定義を変更したり、目的のイベントで自動的に新しい訪問を開始したりすることもできます。 これらの設定は、Customer Journey AnalyticsとAdobe Analyticsのレポートの違いに大きな影響を与える場合があります。

## 製品間のレコード数の確認

上記の設定がすべて似ている場合に、製品間のレコード数を少なくとも検証するには、次の手順を使用します。

1. Adobe Experience Platform[&#x200B; クエリサービス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home) で、次のタイムスタンプ別の合計レコード数クエリを実行します。

   ```sql
   SELECT
     Substring(from_utc_timestamp(timestamp,'{timeZone}'), 1, 10) AS Day,
     Count(_id) AS Records
   FROM  {dataset}
   WHERE   timestamp >= from_utc_timestamp('{fromDate}','UTC')
     AND timestamp < from_utc_timestamp('{toDate}','UTC')
     AND timestamp IS NOT NULL
     AND enduserids._experience.aaid.id IS NOT NULL
   GROUP BY Day
   ORDER BY Day;
   ```

1. Adobe Analytics[&#x200B; データフィード &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics/export/analytics-data-feed/data-feed-overview) で、目的の日付範囲のフィードファイルを生成します。 次の行を識別して除外し、各ファイル内の行数をカウントします。

   * `exclude_hit` は `0` ではありません（両方の製品でAnalysis Workspaceからデータが除外されました）
   * `hit_source` には、`0`、`3`、`5`、`7`、`8`、`9` または `10` （データソースおよびその他のヒットしないデータ）があります
   * `page_event` is `53` or `63` （Streaming Media keep-alive hits）

   上記の条件のいずれかに一致する行は、Analytics Source コネクタの取り込みワークフローから除外されるので、データフィード行をカウントする際にも除外する必要があります。

1. クエリサービスの合計レコード数は、同期間のデータフィードの行数と一致する必要があります。
