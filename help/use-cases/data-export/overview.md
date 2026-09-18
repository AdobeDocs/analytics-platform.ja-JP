---
title: データ書き出しのユースケース
description: Customer Journey Analyticsの様々なデータ書き出しのユースケースについて
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
TQID: https://experienceleague.adobe.com/ad4wWxqEZZxsnSTpus7pxFMlwNo3nNUpHeS9VfxrEdw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 06d3fa4838d48567f1b9804992aa0f718937916d
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%
---
# データ書き出しのユースケース {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="データフィードと同様の書き出し機能の使用"
>abstract="データフィードの完全な代替機能は、Customer Journey Analyticsではまだ使用できませんが、テーブルの書き出し、Platform データセットの書き出し、BI ツールの統合、レポート APIを通じて同様の機能を使用できます。"

<!-- markdownlint-enable MD034 -->

この節では、データ書き出しのユースケースと、Customer Journey AnalyticsまたはExperience Platformの1つ以上の機能でこれらのユースケースを実装する方法について説明します。 各機能については、別の記事でさらに詳しく説明しています。

## はじめに

Adobe AnalyticsとCustomer Journey Analyticsのユニークな違いのひとつは、アトリビューションとセッション化のためのデータ処理です。 詳しくは、[Adobe AnalyticsとCustomer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)のデータ処理の比較を参照してください。

### Adobe Analytics：コレクション時間のアトリビューションとセッション化

Adobe Analyticsでは、すべてのイベントがライブでデバイス IDごとに処理されるため、Adobeでは、収集時に永続的または属性値を含むクリックストリームデータを生成、保存、エクスポートできます。

* Dimensionの永続性（例えば、90日後に失効するキャンペーントラッキングコード）。
* 訪問回数とセッション化：
* 処理ルールとVISTA ルールによって計算されるDimension値。

これは、Adobe Analyticsからのデータの書き出しに影響します。

* データ処理は初期収集後は静的です。
* データフィードには、「post」列があり、これは収集時の処理を反映しています。


### Customer Journey Analytics：クエリ時間のアトリビューションとセッション化

Customer Journey Analyticsでは、イベントは順番に収集されず、デバイス IDの代わりに個人IDが使用されるため、レポート時にCustomer Journey Analyticsでアトリビューションとセッションを更新できます。 こうしたデータ収集は、次のような柔軟性をもたらします。

* 結合すると、匿名のイベントを既知のイベントに関連付けて、毎日または毎週&#x200B;_リプレイ_ データを再生できます。 詳しくは、[ ステッチ ](../../stitching/overview.md)を参照してください。
* セッション化と永続的な値は、常に変更されます
  * 新しいデータが収集されるか、
  * 結合すると、ユーザーの履歴にイベントが追加されます。

レポート時処理は、Customer Journey Analyticsからのデータの書き出しに影響します。 永続的な値を含む書き出しは、Customer Journey Analytics レポートと一致せず、値は時間の経過とともに異なります。

指標の一貫性を保つためには、Customer Journey Analyticsの新機能を使用することをお勧めします。 一般的に、Experience PlatformとCustomer Journey Analyticsのデータ書き出し機能は、Adobe Analyticsのデータフィード機能を超えています。 Experience PlatformとCustomer Journey Analyticsには、次の機能があります。

* データ書き出しの対象となる新しいデータソースと処理

  * 非デジタルデータソース，
  * ビジネスルールにもとづいてカスタムのアトリビューションとセッション化を適用し、
  * つなぎ合わせてカスタマージャーニーを最新の状態に保つ。

* カスタマイズされたデータ書き出しのユースケースの導入

  * Business Intelligence（BI）ツールやクラウドの宛先など、必要な場所にデータを書き出し，
  * ビジネスインテリジェンス（BI）ツールとの統合により、データをAnalysis Workspaceと同期し，
  * 自分のシステムで処理ロジックを複製する必要がなく，
  * 計算指標、派生フィールド、セグメント化の新しいサポート

* セキュリティとデータガバナンスの考慮

  * ユーザーと宛先ごとのあらゆるデータ書き出しを監視し，
  * 書き出しに使用できるデータの制限を設定し、
  * 配信の問題に対するアラートを設定し、スケジュールされた配信ウィンドウを制限します。


## ユースケースと機能

一般的に、データ書き出しは多くのユースケースをサポートしています。 必要なデータとそのデータへのアクセス方法や書き出し方法はユースケースごとに異なります。 Experience PlatformとCustomer Journey Analyticsは、それぞれ個別に使用するか、組み合わせて使用することで、さまざまなユースケースを解決できる機能を数多く提供しています。 次の表に、特定されたデータ書き出しのユースケースと、これらのユースケースを実装するExperience PlatformとCustomer Journey Analyticsの機能の概要を示します。

| データ書き出しのユースケース | Experience PlatformとCustomer Journey Analyticsの機能 |
|---|---|
| **データバックアップ**<br/> コンプライアンスまたは規制上の目的で、デジタルデータの完全なコピーを保持します。 | **Experience Platform**: [**データセットの書き出し**](export-datasets.md)<br/> Experience Platformで収集したデータを、スケジュールまたはアドホックでクラウドの宛先に直接書き出します。 |
| **データ検証**<br/> データ収集の正確性に関するクリックストリームデータを評価します。 | **Experience Platform**: [**クエリサービス（Data Distiller）とデータセットの書き出し**](queryservice-export-datasets.md)<br/> インタラクティブ PostgreSQL インターフェイス。お気に入りのSQL ツールを使用してアドホック SQL クエリを実行し、データセット内のデータを検証できます。<br/><br/>**Customer Journey Analytics**: [**テーブル全体を書き出し**](export-full-table.md)<br/>&#x200B;属性とセッションが適用されたCJAから処理済みデータを検証します。 |
| **データレイク、Data Warehouse、BI ツール**<br/>&#x200B;独自のBI ツールまたはデータレイクにデジタルデータを取り込んで、他のデータセットで使用します。 | **Customer Journey Analytics**: [**BI拡張機能**](bi-extension.md)<br/> Customer Journey Analyticsで処理された指標をPower BIなどのデータビジュアライゼーションツールに追加し、カスタムレポート用の追加データと組み合わせる&#x200B;<br/><br/>**Experience Platform**: [**Query Service （Data Distiller）とデータセットの書き出し**](queryservice-export-datasets.md)<br> SQLを使用してカスタマイズされたクリックストリームデータを生成し、クラウドの宛先に配信します。 |
| **AI/マシンラーニングへの対応**<br/> Customer Journey Analytics データを使用して、AI/マシンラーニングモデルとタスクを強化する。 | **Customer Journey Analytics**: [**テーブル全体を書き出し**](export-full-table.md)<br/> Customer Journey Analyticsで処理されたディメンションと指標をクラウドの宛先に1回限りまたは定期的に書き出します（計算指標とセグメント化を含む）。<br/><br/>**Experience Platform**: [**クエリサービス（Data Distiller）とデータセットの書き出し**](queryservice-export-datasets.md)<br/> SQLを使用してカスタマイズされたクリックストリームデータを生成し、AI/ML モデルを強化します。 |
| **アドホックおよび定期的なレポート**<br/> データパイプラインを設定せずに、個々のユーザーまたはビジネス部門に処理済みCustomer Journey Analytics データへのセルフサービス アクセス権を付与します。 | **Customer Journey Analytics**: [**Workspace書き出し**](workspace-export.md)<br/> Analysis Workspace プロジェクトから直接データをダウンロードまたは電子メールで送信して、1回限りの分析または共有を行います。<br/><br/>**Customer Journey Analytics**: [**Report Builder**](report-builder.md)<br/> Customer Journey Analytics データをExcel ワークブックに取り込み、定期的なビジネス ユーザー向けのレポートを作成します。 |
| **カスタムアプリケーションの統合**<br/> Customer Journey Analytics データを使用して、ダッシュボード、社内ツール、または自動化ワークフローを強化します。 | **Customer Journey Analytics**: [**レポート API**](reporting-api.md)<br/> Customer Journey Analytics データをプログラムで取得して、独自のアプリケーションまたはオートメーションと統合します。 |

## 機能の選択

複数の機能で同じユースケースを実装できます。 最適なオプションを選択したら、次のことを検討します。

* **データボリューム**: [Workspace書き出し](/help/use-cases/data-export/workspace-export.md)や[Report Builder](/help/use-cases/data-export/report-builder.md)などのアドホックメソッドは、数万行に制限されています。 [ テーブル全体の書き出し](/help/use-cases/data-export/export-full-table.md)および[ データセットの書き出し](/help/use-cases/data-export/export-datasets.md)は、数百万行をサポートしています。
* **Rawと処理済みデータ**: [ データセットの書き出し](/help/use-cases/data-export/export-datasets.md)および[Query Service （Data Distiller）とデータセットの書き出し](/help/use-cases/data-export/queryservice-export-datasets.md)により、データレイクから未処理の生データが配信されます。 [BI拡張機能](/help/use-cases/data-export/bi-extension.md)、[ テーブル全体を書き出し](/help/use-cases/data-export/export-full-table.md)、[Workspace書き出し](/help/use-cases/data-export/workspace-export.md)、[Report Builder](/help/use-cases/data-export/report-builder.md)、および[ レポート API](/help/use-cases/data-export/reporting-api.md)は、Customer Journey Analyticsが既に処理したデータ（アトリビューション、セッション化、計算指標など）を配信します。
* **技術的な専門知識**: [Query Service （Data Distiller）およびデータセットの書き出し](/help/use-cases/data-export/queryservice-export-datasets.md)と[BI拡張機能](/help/use-cases/data-export/bi-extension.md)には、SQLに関する知識が必要です。 [Workspace書き出し](/help/use-cases/data-export/workspace-export.md)と[Report Builder](/help/use-cases/data-export/report-builder.md)は、ポイント&amp;クリック操作のインターフェイスを使用しています。 [ レポート API](/help/use-cases/data-export/reporting-api.md)には、プログラミングの知識が必要です。
* **スケジュール設定**: [ データセットの書き出し](/help/use-cases/data-export/export-datasets.md)、[ テーブル全体の書き出し](/help/use-cases/data-export/export-full-table.md)、[Report Builder](/help/use-cases/data-export/report-builder.md)では、定期的な配信がサポートされます。 [Workspace書き出し](/help/use-cases/data-export/workspace-export.md) ダウンロードはアドホックのみです。
* **出力形式と宛先**: クラウドストレージのファイル、BI ツールのテーブル、Excelのワークブック、API呼び出しからの応答のいずれが必要かを検討し、それを提供する機能と一致させます。
