---
title: データ書き出しのユースケース
description: Customer Journey Analyticsの様々なデータ書き出しのユースケースについて
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: ba9ae0e5084aaf1b14cff0ac89abd9b9f3569cc0
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 7%

---

# データ書き出しのユースケース {#data-export-use-cases}

<!-- This contextual help is for the upgrade checklist -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds-step"
>title="データフィードと同様の書き出し機能の使用"
>abstract="データフィードの完全な代替機能は、Customer Journey Analytics ではまだ利用できません。 ただし、完全なテーブルの書き出し、Platform データセットの書き出し、BI ツールの統合、レポート API などの機能を使用すると、同様の機能を実現できます。"

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

* 結合すると、匿名のイベントを既知のイベントに関連付けて、毎日または毎週&#x200B;_リプレイ_ データを再生できます。 詳しくは、[&#x200B; ステッチ &#x200B;](../../stitching/overview.md)を参照してください。
* セッション化と永続的な値は、常に変更されます
   * 新しいデータが収集されるか、
   * 結合すると、ユーザーの履歴にイベントが追加されます。

レポート時処理は、Customer Journey Analyticsからのデータの書き出しに影響します。 永続的な値を含む書き出しは、Customer Journey Analytics レポートと一致せず、値は時間の経過とともにドリフトします。

指標の一貫性を保つためには、Customer Journey Analyticsの新機能を使用することをお勧めします。 一般的に、Experience PlatformとCustomer Journey Analyticsのデータ書き出し機能は、Adobe Analyticsのデータフィード機能を超えています。 Experience PlatformとCustomer Journey Analyticsには、次のような機能があります。

* データ書き出しの対象となる新しいデータソースと処理

   * 非デジタルデータソース，
   * ビジネスルールにもとづいてカスタムのアトリビューションとセッション化を適用し、
   * つなぎ合わせてカスタマージャーニーを最新の状態に保つ。

* カスタマイズされたデータ書き出しのユースケースの実現

   * Business Intelligence（BI）ツールやクラウドの宛先など、必要な場所にデータを書き出し，
   * ビジネスインテリジェンス（BI）ツールとの統合により、データをAnalysis Workspaceと同期し，
   * 独自のシステムで処理ロジックをレプリケートする必要はなく，
   * 計算指標、派生フィールド、セグメント化の新しいサポート

* 設計によるセキュリティとデータガバナンスの検討

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
