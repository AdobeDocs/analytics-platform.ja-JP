---
description: データフィードを使用して、Customer Journey Analyticsから生のイベントレベルのデータを書き出す方法、前提条件を確認する方法、開始するために必要な記事を見つける方法を説明します。
keywords: クリックストリーム;データフィード;データフィード;データフィード
title: Customer Journey Analytics データフィードの概要
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: 34959e37a7040bcd861a506968895ad6f051b686
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%
---
# データフィードの概要

{{release-limited-testing}}

データフィードは、Customer Journey Analyticsからクラウドに生のイベントレベルのデータを書き出します。 Adobe以外のデータウェアハウスなどのプラットフォームでも、これらのデータを使用できます。

データフィードは、データビューのコンポーネントから構築されます。 含める各ディメンションと指標はデータフィードの列となり、永続性、派生フィールド、セグメントなどのデータビュー設定がデータに適用されます。 ファイルはParquet形式で配信されます。

次の種類のデータフィードを作成できます。

* **ライブフィード**：現在および将来のデータを1時間または1日ごとに書き出します。 各配信は、時間または日が終了し、処理遅延が経過した後に送信されます。

* **バックフィル フィード**：過去の日付範囲の履歴データを書き出します。

テーブルの書き出しなど、他のCustomer Journey Analytics書き出し方式とのデータフィードの比較については、[Analytics製品の比較](/help/getting-started/analytics-product-comparison.md)を参照してください。

## 前提条件

データフィードを使用する前に、次のすべての要件を満たしていることを確認してください。

* データはCustomer Journey Analyticsに取り込まれ、接続と[&#x200B; データビュー](/help/data-views/create-dataview.md)が設定されます。<!-- For more information, see Data ingestion overview - add link -->

* お客様のアカウントは、Customer Journey Analyticsの製品管理者であるか、使用するデータビューの&#x200B;[!UICONTROL **データフィード**]&#x200B;権限（[!UICONTROL **データビューツール**] カテゴリ）を持つ製品プロファイルに属しています。 詳しくは、[&#x200B; アクセス制御](/help/technotes/access-control.md)を参照してください。<!--Add a Data Feeds row to the Data View Tools permissions table in access-control.md.-->

* クラウド書き出しアカウントと場所は、[!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]、または[!DNL Azure SAS]用に設定されています。 詳しくは、[&#x200B; クラウド書き出しアカウントの設定](/help/components/exports/cloud-export-accounts.md)および[&#x200B; クラウド書き出し場所の設定](/help/components/exports/cloud-export-locations.md)を参照してください。

>[!TIP]
>
>データビュー内のコンポーネントの変更は、それを使用するすべてのデータフィードに影響を与えるため、データフィードにのみ使用されるデータビューの作成を検討してください。
>
>* **利点**: Analysis Workspace レポートに加えられた変更によって、データフィード出力が予期せず変更されるリスクを軽減します。
>
>* **欠点**：追加のデータビューを他のデータビューと並べて維持する必要があります。

## 基本を学ぶ

データフィードの計画、移行、作成には、次の記事を使用します。

### データフィードの計画

* [Customer Journey AnalyticsとAdobe Analyticsのデータフィードの比較](/help/components/exports/cja-data-feeds/df-comparison.md)：以前にAdobe Analytics データフィードを使用した場合の機能と概念の違いを理解します。

* [&#x200B; データフィードとAnalysis Workspace間のデータの不一致を理解](/help/components/exports/cja-data-feeds/df-comparison-workspace.md): データフィードの出力がAnalysis Workspaceのレポートと一致しない理由を説明します。

* [&#x200B; データフィードでのコンポーネントの可用性](/help/components/exports/cja-data-feeds/df-components.md): データフィードで必須、サポートされていない、または制限されているディメンションと指標について説明します。

### Adobe Analytics データフィードからの移行

1. [&#x200B; データフィード列のマッピングの準備](/help/components/exports/cja-data-feeds/df-column-mapping-prep.md): Adobe Analytics列のCustomer Journey Analyticsへのマッピング方法に影響する要因を理解します。

1. [Adobe Analytics データフィード列をCustomer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)にマッピング：保持する各Adobe Analytics列に相当するCustomer Journey Analyticsを検索します。

### データフィードの作成と設定

* [&#x200B; データフィードを作成](/help/components/exports/cja-data-feeds/create-feed.md): コンポーネントを選択し、スケジュールを設定し、配信を設定します。

* [&#x200B; データフィードのセグメント化](/help/components/exports/cja-data-feeds/df-segmentation.md): セグメントを適用して、データフィードのデータをフィルタリングします。

* [&#x200B; データ変換の適用](/help/components/exports/cja-data-feeds/df-data-transformations.md): コンポーネント設定、派生フィールド、またはSQLを使用してデータを変換します。

* [&#x200B; データフィードのサブイベントコンポーネント &#x200B;](/help/components/exports/cja-data-feeds/df-sub-event.md)：配列やマップのコンポーネントの書き出し方法とクエリ方法について説明します。

