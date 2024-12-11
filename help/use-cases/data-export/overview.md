---
title: データ書き出しのユースケース
description: Customer Journey Analyticsのための様々なデータエクスポートのユースケースについて
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: ae0e7a906700522d7babc1d573a0b4cdbf1be6fc
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 1%

---

# データ書き出しのユースケース

この節では、データ書き出しの使用例と、1 つ以上のCustomer Journey AnalyticsまたはExperience Platformの機能を使用してこれらの使用例を実装する方法について説明します。 各機能について詳しくは、別の記事を参照してください。

## はじめに

Adobe Analyticsとアトリビューションのユニークな違いの 1 つは、Customer Journey Analyticsとセッション化のためのデータの処理に関連しています。 詳しくは、[Adobe AnalyticsとCustomer Journey Analytics間でのデータ処理の比較 ](/help/getting-started/aa-vs-cja/data-processing-comparisons.md) を参照してください。

### Adobe Analytics：コレクション時間のアトリビューションとセッション。

Adobe Analyticsでは、すべてのイベントがデバイス ID 別にライブで順に処理されるので、Adobeは、コレクション時に、以下の永続化された値または属性を含むクリックストリームデータを生成、保存および書き出すことができます。

* Dimensionの永続性（例えば、90 日後に期限切れになるキャンペーントラッキングコード）。
* 訪問回数とセッション。
* 処理および VISTA ルールによって計算されるDimension値。

これは、Adobe Analyticsからのデータの書き出しに影響します。

* データ処理は、最初の収集後は静的です。
* データフィードには、コレクション時の処理を反映する「post」列が含まれます。


### Customer Journey Analytics：クエリ時間アトリビューションとセッション化

Customer Journey Analyticsすると、イベントが順番に収集されず、デバイス ID の代わりにユーザー ID が使用されるので、Customer Journey Analyticsはレポート時にアトリビューションとセッション化を更新できます。 このタイプのデータ収集では、次のような柔軟性が導入されます。

* ステッチでは、毎日または毎週データを _再生_ し、匿名イベントを既知のイベントに関連付けることができます。 詳しくは、[ ステッチ ](../../stitching/overview.md) を参照してください。
* セッション化と永続化の値は毎回変更されます
   * 新しいデータが収集されるか、
   * ステッチにより、個人の履歴にイベントが追加されます。

レポート時間処理は、Customer Journey Analyticsからのデータの書き出しに影響します。 永続的な値を含む書き出しは、Customer Journey Analyticsレポートに一致せず、値は時間の経過と共にずれます。

指標の一貫性を保つには、Customer Journey Analyticsの新機能を使用することをお勧めします。 一般に、Experience PlatformおよびCustomer Journey Analyticsのデータ書き出し機能は、Adobe Analyticsのデータフィード機能を超えています。 Experience PlatformとCustomer Journey Analyticsが提供する機能は次のとおりです。

* 新しいデータソースと、データの書き出し対象となる処理

   * 非デジタルデータソースを含める、
   * ビジネスルールに基づいたカスタム属性およびセッションの適用
   * ステッチを使用してカスタマージャーニーを更新します。

* カスタマイズされたデータ書き出しのユースケースの実現

   * Business Intelligence（BI）ツールやクラウドの宛先など、必要な場所にデータを書き出すことができます。
   * bi ツールの統合を通じてAnalysis Workspaceとのデータの同期を維持し、
   * 独自のシステムに処理ロジックをレプリケートする必要はありません。
   * 計算指標、派生フィールドおよびセグメント化の新しいサポート。

* 設計によるセキュリティとデータガバナンスの考慮

   * ユーザーおよび宛先別のすべてのデータ書き出しを監視する。
   * エクスポートできるデータの制限を設定する。
   * スケジュールされた配信期間における配信の問題と制限に関するアラートを設定します。


## ユースケースと機能

一般に、データの書き出しでは、多くのユースケースをサポートしています。 必要なデータとそのデータにアクセスして書き出す方法に関しては、ユースケースごとに異なります。 Experience PlatformとCustomer Journey Analyticsには、様々なユースケースを解決できる多数の機能が用意されており、それぞれ単独で使用することも、組み合わせて使用することもできます。 次の表に、特定されたデータ書き出しのユースケースと、これらのユースケースを実装するためのExperience PlatformおよびCustomer Journey Analytics機能の概要を示します。

| データ書き出しのユースケース | Experience PlatformとCustomer Journey Analytics機能 |
|---|---|
| **データのバックアップ**<br/> コンプライアンスや規制の目的で、デジタル・データの完全なコピーを保持します。 | **Experience Platform**: [**データセットを書き出し**](export-datasets.md)<br/> Experience Platformで収集したデータを、スケジュールに従って、またはアドホックでクラウドの宛先に直接書き出します。 |
| **データの検証**<br/> データ収集の正確性を確保するためにクリックストリームデータを評価します。 | **Experience Platform**: [**クエリサービス （データDistiller）とデータセットの書き出し**](queryservice-export-datasets.md)<br/> お気に入りの SQL ツールを使用してアドホック SQL クエリを実行し、データセット内のデータを検証する Interactive PostgreSQL インターフェイス。<br/><br/>**Customer Journey Analytics**: [**完全なテーブルをエクスポート**](export-full-table.md)<br/> アトリビューションとセッション化が適用された状態で、CJA から処理済みデータを検証します。 |
| **データレイク、Data Warehouseまたは BI ツール**<br/> 独自の BI ツールまたはデータレイクにデジタルデータを取り込み、追加のデータセットで使用します。 | **Customer Journey Analytics**: [**BI 拡張機能**](bi-extension.md)<br/> Customer Journey Analyticsの処理済み指標をデータなどのPower BIビジュアライゼーションツールに追加し、カスタムレポートの追加データと組み合わせます <br/><br/>**Experience Platform**: [**クエリサービス（Data Distiller）とデータセットの書き出し**](queryservice-export-datasets.md)<br> SQL を使用してカスタマイズされたクリックストリームデータを生成し、クラウドの宛先に配信します。 |
| **AI/ML への対応**<br/> Customer Journey Analyticsデータを用いて人工知能/機械学習モデルとタスクを強化します。 | **Customer Journey Analytics**: [**完全なテーブルをエクスポート**](export-full-table.md)<br/> Customer Journey Analyticsで処理されたディメンションと指標を、計算指標やセグメント化を含めて、クラウドの宛先に 1 回限りまたは定期的にエクスポートします。<br/><br/>**Experience Platform**: [**クエリサービス （データDistiller）およびデータセットの書き出し**](queryservice-export-datasets.md)<br/> SQL を使用してカスタマイズされたクリックストリームデータを生成し、AI / ML モデルを強化します。 |
