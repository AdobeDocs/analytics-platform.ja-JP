---
title: 日付範囲名を使用してフィルター
description: Customer Journey Analyticsの様々な BI ツールで、日付範囲名を使用して、BI 拡張機能のユースケースをフィルタリングします
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 1%

---

# 日付範囲名を使用してフィルター

このユースケースでは、Customer Journey Analyticsで定義した日付範囲を使用して、昨年の発生件数（イベント数）をフィルタリングしてレポートします。

+++ Customer Journey Analytics

日付範囲を使用してレポートを作成するには、Customer Journey Analyticsで **[!UICONTROL タイトル]** `Last Year 2023` を使用して日付範囲を設定します。

![Customer Journey Analytics フィルターに日付範囲名を使用 &#x200B;](../assets/cja-daterange.png)

次に、使用例の **[!UICONTROL 日付範囲名をフィルターに使用]** パネルでその日付範囲を使用できます。

![Customer Journey Analytics個別カウント値 &#x200B;](../assets/cja-using-date-range-filter-names-to-filter.png)

フリーフォームテーブルのビジュアライゼーションで定義された日付範囲が、パネルに適用される日付範囲をどのように上書きするかに注意してください。

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[&#x200B; 接続に成功し、データビューをリストし、データビューを使用できる &#x200B;](connect-and-validate.md) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangemonth]** を選択します。
   1. **[!UICONTROL daterangeName]** を選択します。
   1. **[!UICONTROL 発生件数の合計]** を選択します。

   **[!UICONTROL このビジュアルのデータ取得エラー]** と表示されるビジュアライゼーションが表示されます。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterangeName は（すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 基本フィルタリング]** を選択します。
   1. **[!UICONTROL 検索]** フィールドの下で、Customer Journey Analyticsで定義された日付範囲の名前である **[!UICONTROL Last Year 2023]** を選択します。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、**[!UICONTROL daterangeName]** を **[!UICONTROL Columns]** から削除します。

   適用した **[!UICONTROL daterangeName]** フィルターで更新されたテーブルが表示されます。 Power BI デスクトップは次のようになります。

   ![&#x200B; 日付範囲名を使用してフィルターを適用するPower BI デスクトップ &#x200B;](../assets/uc8-powerbi-final.png)

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange Name]** エントリをドラッグします。
   1. **[!UICONTROL フィルター\[Daterange Name\]]** ダイアログで **[!UICONTROL リストから選択]** が選択されていることを確認し、リストから **[!UICONTROL Last Year 2023]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterangemonth]** エントリをドラッグし、**[!UICONTROL 行]** の横のフィールドにドロップします。 「**[!UICONTROL Daterangemonth]**」を選択し、「**[!UICONTROL 月]**」を選択します。 値が「**[!UICONTROL MONTH （Daterangemonth）]**」に変わります。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. ツールバーの **[!UICONTROL 行と列を入れ替える]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](../assets/uc8-tableau-final.png)

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![&#x200B; 設定 &#x200B;](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Name]**」を選択します。
1. **[!UICONTROL CC データビューのデータレンジ名]** フィルターを **[!UICONTROL のままに指定し]** 値リストから **[!UICONTROL 昨年 2023]** を選択します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL Daterange Month]** を選択してから、**[!UICONTROL Month]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](../assets/uc8-looker-result.png)


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   data = %sql SELECT daterangeName FROM cc_data_view;
   style = {'description_width': 'initial'}
   daterange_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Date Range Name:',
      style=style
   )
   display(daterange_name)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 &#x200B;](../assets/uc8-jupyter-input.png)

1. ドロップダウンメニューから **[!UICONTROL 釣り製品]** を選択します。

1. 新しいセルに次のステートメントを入力します。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterangeName = '{daterange_name.value}' \
               GROUP BY 1 \
               ORDER BY Month ASC
   df = data.DataFrame()
   df = df.groupby('Month', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Month', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 &#x200B;](../assets/uc8-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクで、` ` ``{r} ` と ` `` ` ` の間に次のステートメントを入力します。 適切な日付範囲名を使用していることを確認してください。 例：`Last Year 2023`。

   ```R
   ## Monthly Events for Last Year
   df <- dv %>%
      filter(daterangeName == "Last Year 2023") %>%
      group_by(daterangemonth) %>%
      count() %>%
      arrange(daterangemonth, .by_group = FALSE)
   ggplot(df, aes(x = daterangemonth, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 &#x200B;](../assets/uc8-rstudio-results.png)

>[!ENDTABS]

+++

