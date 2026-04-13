---
title: 日々のトレンド
description: Customer Journey Analyticsの様々なBI ツールでのBI拡張機能の日次トレンドのユースケース
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: 09810072-1be4-4c78-8c84-b33db1872dbc
source-git-commit: a0251638e66d5a2524418fc17f56dddc4e48accd
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 0%

---

# 日々のトレンド


この使用例では、2023年1月1日から2023年1月31日までの日次トレンド（イベント）を示すテーブルと単純な行のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例&#x200B;**[!UICONTROL Daily Trend]** パネル：

![Customer Journey Analytics日次トレンドパネル ](../assets/cja_daily_trend.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>[成功した接続を検証し、このユースケースを試すBI ツールのデータビュー](connect-and-validate.md)を一覧表示して使用できることを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangeday]**&#x200B;を選択します。
   1. **[!UICONTROL 合計回数]**&#x200B;を選択します。

   現在の月の発生件数を示すテーブルが表示されます。 可視性を高めるには、ビジュアライゼーションを拡大します。

1. **[!UICONTROL フィルター]** ペインで、次の操作を行います。

   1. このビジュアル **[!UICONTROL の]** フィルターから&#x200B;**[!UICONTROL daterangeday is （All）]**&#x200B;を選択します。
   1. **[!UICONTROL 詳細フィルタリング]**&#x200B;を&#x200B;**[!UICONTROL フィルタータイプ]**&#x200B;として選択します。
   1. 値&#x200B;****&#x200B;が&#x200B;****&#x200B;以降`1/1/2023`および&#x200B;****&#x200B;が&#x200B;****&#x200B;より前の場合に`2/1/2023.`項目を表示するようにフィルターを定義します。カレンダーアイコンを使用して、日付を選択できます。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   適用された&#x200B;**[!UICONTROL daterangeday]** フィルターでテーブルが更新されます。

1. **[!UICONTROL ビジュアライゼーション]** ペインで、**[!UICONTROL 折れ線グラフ]** ビジュアライゼーションを選択します。

   折れ線グラフのビジュアライゼーションは、表と同じデータを使用している間に表を置き換えます。 Power BI デスクトップは以下のようになります。

   ![Power BI Desktop ユースケース 2日付範囲フィルター](../assets/uc2-pbi-daterange.png)

1. 折れ線グラフのビジュアライゼーション：

   1. ![詳細](/help/assets/icons/More.svg)を選択します。
   1. コンテキストメニューから、**[!UICONTROL テーブルとして表示]**&#x200B;を選択します。

   メインビューが更新され、行のビジュアライゼーションと表の両方が表示されます。 Power BI デスクトップは以下のようになります。

   ![Power BI デスクトップ版ユースケース 2の最終的な日次トレンドのビジュアライゼーション ](../assets/uc2-pbi-final.png)

>[!TAB Tableau Desktop]

1. 下部の「**[!UICONTROL シート 1]**」タブを選択して、**[!UICONTROL データソース]** ビューから切り替えます。 **[!UICONTROL シート 1]** ビューで：
   1. **[!UICONTROL Data]** ペインの&#x200B;**[!UICONTROL Tables]** リストから&#x200B;**[!UICONTROL Daterange]** エントリをドラッグし、エントリを&#x200B;**[!UICONTROL Filters]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで、**[!UICONTROL 日付の範囲]**&#x200B;を選択し、**[!UICONTROL 次>]**&#x200B;を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで、**[!UICONTROL 日付の範囲]**&#x200B;を選択し、`01/01/2023` ～ `01/02/2023`の期間を指定します。

      ![Tableau Desktop Filter](../assets/uc2-tableau-filter.png)

   1. **[!UICONTROL Data]** ペインの&#x200B;**[!UICONTROL Tables]** リストから&#x200B;**[!UICONTROL Daterangeday]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL 列]**&#x200B;の横にあるフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから&#x200B;**[!UICONTROL Day]**&#x200B;を選択して、値を&#x200B;**[!UICONTROL DAY （Daterangeday）]**&#x200B;に更新します。
   1. **[!UICONTROL データ]** ペインの&#x200B;**[!UICONTROL テーブル （*メジャー名*）]** リストから&#x200B;**[!UICONTROL 発生回数]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL 行]**&#x200B;の横にあるフィールドにエントリをドロップします。 値は自動的に&#x200B;**[!UICONTROL SUM （Occurrences）]**&#x200B;に変換されます。
   1. ツールバーの「**[!UICONTROL フィット]**」ドロップダウンメニューから「**[!UICONTROL 標準]**」を「**[!UICONTROL ビュー全体]**」に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Graph](../assets/uc2-tableau-graph.png)

1. 「**[!UICONTROL シート 1]**」タブのコンテキストメニューから「**[!UICONTROL 複製]**」を選択して、2番目のシートを作成します。
1. 「**[!UICONTROL シート 1]**」タブのコンテキストメニューから「**[!UICONTROL 名前を変更]**」を選択して、シートの名前を`Graph`に変更します。
1. 「**[!UICONTROL シート 1 （2）]**」タブのコンテキストメニューから「**[!UICONTROL 名前を変更]**」を選択して、シートの名前を`Data`に変更します。
1. **[!UICONTROL Data]** シートが選択されていることを確認します。 **[!UICONTROL データ]** ビューで：
   1. 右上の「**[!UICONTROL 自分を表示]**」を選択し、「**[!UICONTROL テキストテーブル]**」（左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. ツールバーから「**[!UICONTROL 行と列を入れ替え]**」を選択します。
   1. ツールバーの「**[!UICONTROL フィット]**」ドロップダウンメニューから「**[!UICONTROL 標準]**」を「**[!UICONTROL ビュー全体]**」に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Data](../assets/uc2-tableau-data.png)

1. 「**[!UICONTROL 新しいダッシュボード]**」タブ ボタン（下部）を選択して、新しい&#x200B;**[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL グラフ]** シートを&#x200B;**[!UICONTROL シート]** シェルフから&#x200B;**[!UICONTROL シートをここにドロップ]**&#x200B;する&#x200B;*ダッシュボード 1* ビューにドラッグ&amp;ドロップします。
   1. **[!UICONTROL グラフ]** シートの下の&#x200B;**[!UICONTROL シート]** シェルフから&#x200B;**[!UICONTROL データ]** シートを&#x200B;**[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで&#x200B;**[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]**&#x200B;を&#x200B;**[!UICONTROL 幅を修正]**&#x200B;に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Dashboard 1](../assets/uc2-tableau-dashboard.png)


>[!TAB Looker]

1. Lookerの&#x200B;**[!UICONTROL Explore]** インターフェイスで、クリーンな設定が行われていることを確認します。 そうでない場合は、![設定](/help/assets/icons/Setting.svg) **[!UICONTROL フィールドとフィルターの削除]**&#x200B;を選択します。
1. 「**[!UICONTROL フィルター]**」の下の「**[!UICONTROL + フィルター]**」を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログ：
   1. **[!UICONTROL ‣ Cc データビュー]**&#x200B;を選択
   1. フィールドのリストから、**[!UICONTROL }‣ Daterange Date]**、次に&#x200B;**[!UICONTROL Daterange Date]**を選択します。
      ![Looker フィルター](../assets/uc2-looker-filter.png)
1. **[!UICONTROL Cc データビューの日付変更日]** フィルターを&#x200B;**[!UICONTROL が範囲]** **[!UICONTROL 2023/01/01]** **[!UICONTROL から（前）]** **[!UICONTROL 2023/02/01]**&#x200B;に指定します。
1. 左側のパネルの「**[!UICONTROL Cc Data View]**」セクションから，
   1. **[!UICONTROL ディメンション]**&#x200B;のリストから&#x200B;**[!UICONTROL ‣Daterange Date]**、次に&#x200B;**[!UICONTROL Date]**&#x200B;を選択します。
   1. 左パネル（下部）の&#x200B;**[!UICONTROL 測定]**&#x200B;の下にある&#x200B;**[!UICONTROL カウント]**&#x200B;を選択します。
1. **[!UICONTROL 実行]**&#x200B;を選択します。
1. 行のビジュアライゼーションを表示するには、**[!UICONTROL ‣ ビジュアライゼーション]**&#x200B;を選択します。

次のようなビジュアライゼーションと表が表示されます。

![Looker結果の日次トレンド ](../assets/uc2-looker-result.png)


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangeday AS Date, COUNT(*) AS Events \
             FROM cc_data_view \
             WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
             GROUP BY 1 \
             ORDER BY Date ASC
   df = data.DataFrame()
   df = df.groupby('Date', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Date', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebookの結果](../assets/uc2-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクに次のコードブロックを入力します。

   ```R
   ## Daily Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(daterangeday) %>%
      count() %>%
      arrange(daterangeday, .by_group = FALSE)
   ggplot(df, aes(x = daterangeday, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Date")
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio結果](../assets/uc2-rstudio-results.png)

>[!ENDTABS]

+++
