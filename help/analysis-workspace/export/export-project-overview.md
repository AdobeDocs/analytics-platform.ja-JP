---
description: Analysis Workspaceからの書き出しに使用できる様々な方法について説明します。
keywords: Analysis Workspace
title: プロジェクトデータの書き出しの概要
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: ba59267dc39f1e564e555e0d5183613f9171403f
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---

# エクスポートの概要

Analysis WorkspaceからCustomer Journey Analyticsレポートを書き出すことができます。 サードパーティのツールでを利用したり、外部のデータと組み合わせたりするなど、様々な理由でCustomer Journey Analyticsレポートを書き出すことができます。

次の節では、サポートされるファイルの種類、書き出しに使用できる様々な方法、および各方法の利点について説明します。

## サポートされているファイルタイプ

Customer Journey AnalyticsレポートをPDF、CSV、JSON ファイルとして書き出すことができます。

* **PDF:** 関係者と視覚的なデータを簡単に共有できます。 PDFファイルには、プロジェクト内のすべての表示（表示）可能なテーブルとビジュアライゼーションが含まれています。

* **CSV :** Excel などのスプレッドシートアプリケーションで生データを表示できます。 CSV ファイルには、プレーンテキストデータが含まれています。

* **JSON:** データを共有するためのオープンな標準ファイル形式を提供します。

## 書き出しの方法

Analysis Workspaceから書き出す場合は、様々な方法を使用できます。 エクスポート方法を選択する際は、エクスポートする内容とアクセスする必要のあるユーザーを考慮します。

| 書き出し方法 | メリット |
|---------|----------|
| [ワークステーションにダウンロード](/help/analysis-workspace/export/download-send.md) | このメソッドは、次の場合に使用します。 <ul><li>個人用ワークステーションにプロジェクトをダウンロードします。</li><li>ダウンロードはアドホックのみです（スケジュールは設定できません）。</li> <li>合計 50,000 行をダウンロードします。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [他のユーザーに送信](/help/analysis-workspace/export/t-schedule-report.md) | このメソッドは、次の場合に使用します。 <ul><li>エクスポートしたCustomer Journey Analyticsデータを、組織内の他のユーザーに電子メールで送信します。</li><li>アドホックまたはスケジュールに基づいて設定できます。</li> <li>合計 50,000 行を含めます。</li> <!--true?--> |
| [クラウドアプリケーションに送信](/help/analysis-workspace/export/export-cloud.md) | このメソッドは、次の場合に使用します。 <ul><li>Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflakeなどの共有場所にエクスポートします。</li><li>アドホックまたはスケジュールに基づいて設定できます。</li><li>大量のCustomer Journey Analyticsデータを保存。</li><li>数千または数百万の行を含む完全なテーブルをエクスポートします。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}


