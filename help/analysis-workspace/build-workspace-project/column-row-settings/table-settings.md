---
description: 行設定は、テーブルにドラッグしたコンポーネントによって異なります。
title: 行設定
uuid: f30c31d5-1fd4-4b93-94c3-ca441099fe2e
translation-type: tm+mt
source-git-commit: 05bc0b378c962f4513ab292d518e32f5f70f7dfd
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 89%

---


# 行設定

>[!NOTE] Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

行設定は、テーブルにドラッグしたコンポーネントによって異なります。

また、[テーブル内の右クリックアクション](/help/analysis-workspace/visualizations/freeform-table.md)を使用して、選択されている行を管理することもできます。

テーブルの行の設定にアクセスするには、それぞれのディメンション、セグメント、指標、期間または分類の横にある設定アイコンをクリックします。

![](assets/row-settings.png)

| 行設定 | 説明 |
|--- |--- |
| 日付の比較 | 各列の日付を整列させて、すべて同じ行から始まるようにします。日付を整列させると、例えば 2016 年の 10 月を 9 月と比較する前月比の場合、左側の列は 10 月 1 日、右側の列は 9 月 1 日から始まります。<br>デフォルトでは無効です。 |
| 割合（％） | 行ごとに割合を計算という新しい設定により、フリーフォームテーブルでは、列ではなく行全体のセルの割合が表示されるようになります。これは、割合のトレンド分析に特に役立ちます。<br>「視覚化」アイコンを使用している場合は、デフォルトで有効になります。 |
| 列の合計 | これらの設定は、 [static rows](/help/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) (when you have selected a finite set of items), not with dynamic rows (i.e., when you drop in a dimension that shows all items).<ul><li>**[!UICONTROL 現在の行の合計として表示]** - テーブル内の行のクライアント側の合計を表示します。これは、合計で訪問回数や訪問者数などの指標の重複が排除&#x200B;**されない**&#x200B;ことを意味します。</li><li>**[!UICONTROL 総計を表示]** - サーバー側の合計を表示します。つまり、合計で訪問回数や訪問者数などの指標の重複が排除されます。</li></ul> |
| 分類 | **[!UICONTROL 位置で分類]**：フリーフォームテーブル分類で固定位置に基づいて分類を実行できます。例えば、常に上位 7 行が分類されるように指定できます。<br>（以前は、分類の値のリストはレポート作成の時点で「ロック」されていました。例えば、日付をページごとに分類した場合、選択した日付範囲の上位 50 ページのリストが表示されていました。そのレポートを保存して 1 ヶ月後に実行した場合、上位 50 ページが変動している可能性があるものの、Analysis Workspace は現在の月を日付範囲としながらも、以前の分類の結果を使用して同じページを返していました。）<br>固定位置に基づいて分類を実行するには、以下を実行します。1.テーブルの一部の行を分類します。2. 固定位置にするテーブル行の横にある設定（ギア）アイコンをクリックします。3. 「位置で分類」の横にあるチェックボックスをオンにします。4. 並べ替え順序または日付範囲を変更すると、分類はハードコードされた行ではなく行の位置に基づいておこなわれます。<br>デフォルトでは無効です。 |