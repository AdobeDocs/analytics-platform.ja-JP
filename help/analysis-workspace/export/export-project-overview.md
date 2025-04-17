---
description: Analysis Workspace からの書き出しに使用できる方法について説明します。
keywords: Analysis Workspace
title: プロジェクトデータの書き出し方法
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# 書き出しの概要

Customer Journey Analytics レポートは、Analysis Workspace から書き出すことができます。サードパーティのツールで使用したり、外部データと組み合わせたりするなど、様々な理由で Customer Journey Analytics レポートを書き出すことができます。

次の節では、サポートされているファイルタイプ、書き出しに使用できる様々な方法、各方法のメリットについて説明します。

## サポートされているファイルタイプ

Customer Journey Analytics レポートは、PDF、CSV、または JSON ファイルとして書き出すことができます。

* **PDF：**&#x200B;関係者とビジュアルデータを簡単に共有できる方法を提供します。PDF ファイルには、プロジェクトで表示される（表示可能な）すべてのテーブルとビジュアライゼーションが含まれています。

* **CSV：** Excel などのスプレッドシートアプリケーションで生データを表示できます。 CSV ファイルには、プレーンテキストデータが含まれています。

* **JSON：**&#x200B;データを共有するためのオープン標準ファイル形式を提供します。

## 書き出しの方法

Analysis Workspace から書き出す際、様々な方法があります。書き出し方法を選択する際は、書き出す対象と、書き出しにアクセスする必要があるユーザーを考慮します。

| 書き出し方法 | メリット |
|---------|----------|
| [ワークステーションにダウンロード](/help/analysis-workspace/export/download-send.md) | 次の場合に、この方法を使用します。 <ul><li>プロジェクトを個人用ワークステーションにダウンロードする。</li><li>ダウンロードがアドホック専用である（スケジュール設定はできません）。</li> <li>合計 50,000 行をダウンロードする。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [他のユーザーに送信](/help/analysis-workspace/export/t-schedule-report.md) | 次の場合に、この方法を使用します。 <ul><li>書き出された Customer Journey Analytics データを組織の他のユーザーにメールで送信する。</li><li>アドホックに指定するか、スケジュールに従うことができる。</li> <li>合計 50,000 行を含める。</li> <!--true?--> |
| [クラウドアプリケーションに送信](/help/analysis-workspace/export/export-cloud.md) | 次の場合に、この方法を使用します。 <ul><li>Adobe Experience Platform Data Landing Zone、Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflake などの共有の場所に書き出す。</li><li>アドホックに指定するか、スケジュールに従うことができる。</li><li>大量の Customer Journey Analytics データを保存する。</li><li>数千または数百万の行を含む完全なテーブルを書き出す。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
