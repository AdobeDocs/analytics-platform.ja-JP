---
description: Analysis Workspaceからの書き出しに使用できる方法を理解します。
keywords: Analysis Workspace
title: プロジェクトデータのエクスポート方法
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 1%

---

# 書き出しの概要

Analysis WorkspaceからCustomer Journey Analyticsレポートを書き出すことができます。 サードパーティのツールで使用したり、外部データと組み合わせたりするなど、様々な理由でCustomer Journey Analyticsレポートを書き出すことができます。

以下の節では、サポートされているファイルタイプ、書き出しに使用できる様々な方法、各方法の利点について説明します。

## サポートされているファイルタイプ

Customer Journey Analyticsレポートは、PDF、CSV、JSON ファイル形式で書き出すことができます。

* **PDF:** 関係者とビジュアル データを簡単に共有できます。 PDFファイルには、プロジェクト内に表示されるすべてのテーブルとビジュアライゼーションが含まれています。

* **CSV:** 生データを Excel などのスプレッドシートアプリケーションで表示できます。 CSV ファイルには、プレーンテキストデータが含まれています。

* **JSON:** データを共有するためのオープンな標準ファイル形式を提供します。

## 書き出しの方法

Analysis Workspaceからの書き出しには、様々な方法があります。 書き出し方法を選択する際は、書き出す対象と、書き出しにアクセスする必要があるユーザーを検討します。

| 書き出し方法 | メリット |
|---------|----------|
| [ ワークステーションにダウンロード ](/help/analysis-workspace/export/download-send.md) | 次の場合に、この方法を使用します。 <ul><li>プロジェクトを個人用ワークステーションにダウンロードします。</li><li>ダウンロードはアドホック専用です（スケジュール設定はできません）。</li> <li>合計 50,000 行をダウンロードします。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [ 他のユーザーに送信 ](/help/analysis-workspace/export/t-schedule-report.md) | 次の場合に、この方法を使用します。 <ul><li>メールを使用して、組織内の他のユーザーにCustomer Journey Analyticsデータを書き出しました。</li><li>アドホックまたはスケジュールに従って実行できます。</li> <li>合計 50,000 行を含めます。</li> <!--true?--> |
| [ クラウドアプリケーションに送信 ](/help/analysis-workspace/export/export-cloud.md) | 次の場合に、この方法を使用します。 <ul><li>Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflakeなどの共有の場所に書き出します。</li><li>アドホックまたはスケジュールに従って実行できます。</li><li>大量のCustomer Journey Analyticsデータを保存する。</li><li>何千または何百万の行を含む完全なテーブルをエクスポートします。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
