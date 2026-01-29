---
title: セグメント名を使用したセグメント化
description: Customer Journey Analyticsの様々な BI ツールでの BI 拡張機能のユースケースをセグメント名でセグメント化します
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 1%

---

# セグメント名を使用したセグメント化

このユースケースでは、Customer Journey Analyticsで定義した既存のセグメントを釣り商品カテゴリに使用します。 2023 年 1 月中に製品名と発生件数（イベント）をセグメント化し、レポートします。

+++ Customer Journey Analytics

Customer Journey Analyticsで使用するセグメントを調べます。

![Customer Journey Analytics フィルター名を使用してフィルター &#x200B;](../assets/cja-fishing-products.png)

次に、使用例の **[!UICONTROL セグメント名をセグメントに使用]** パネルでそのセグメントを使用できます。

![Customer Journey Analytics個別カウント値 &#x200B;](../assets/cja-using-filter-names-to-filter.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[&#x200B; 接続に成功し、データビューをリストし、データビューを使用できる &#x200B;](connect-and-validate.md) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL filterName]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. **[!UICONTROL 発生件数の合計]** を選択します。

**[!UICONTROL このビジュアルのデータ取得エラー]** と表示されるビジュアライゼーションが表示されます。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。

   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL filterName is （All）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 基本フィルタリング]** を選択します。
   1. **[!UICONTROL 検索]** フィールドの下で、**[!UICONTROL 釣り商品]** を選択します。これは、Customer Journey Analyticsで定義されている既存のフィルターの名前です。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]**&#x200B;**[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]**&#x200B;**[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、**[!UICONTROL filterName]** を **[!UICONTROL Columns]** から削除します。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して **[!UICONTROL Daterange]** を **[!UICONTROL Columns]** から削除します。

   適用した **[!UICONTROL filterName]** フィルターで更新されたテーブルが表示されます。 Power BI デスクトップは次のようになります。

   ![&#x200B; 日付範囲名を使用してフィルターを適用するPower BI デスクトップ &#x200B;](../assets/uc9-powerbi-final.png)


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL フィルター名]** エントリをドラッグします。
   1. **[!UICONTROL フィルター\[ フィルター名\]]** ダイアログで **[!UICONTROL リストから選択]** が選択されていることを確認し、リストから **[!UICONTROL 釣り製品]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterang\]]** ダイアログで **[!UICONTROL 日付の範囲]** を選択し、`01/01/2023` - `01/02/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](../assets/uc9-tableau-final.png)

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![&#x200B; 設定 &#x200B;](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター &#x200B;](../assets/uc2-looker-filter.png)
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]**&#x200B;**[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択して、別のフィルターを追加します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣フィルター名]**」を選択します。
1. フィルターの選択範囲が **[!UICONTROL is]** であることを確認します。
1. 可能な値のリストから **[!UICONTROL 釣り製品]** を選択します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品名]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](../assets/uc9-looker-result.png)



>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   data = %sql SELECT filterName FROM cc_data_view;
   style = {'description_width': 'initial'}
   filter_name = widgets.Dropdown(
      options=[d for d, in data],
      description='Filter Name:',
      style=style
   )
   display(filter_name)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 &#x200B;](../assets/uc9-jupyter-input.png)

1. ドロップダウンメニューから **[!UICONTROL 釣り製品]** を選択します。

1. 新しいセルに次のステートメントを入力します。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
                  AND filterName = '{filter_name.value}' \
               GROUP BY 1 \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 &#x200B;](../assets/uc9-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクで、` ` ``{r} ` と ` `` ` ` の間に次のステートメントを入力します。 適切なフィルター名を使用していることを確認してください。 例：`Fishing Products`。

   ```R
   ## Dimension filtered by name
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & filterName == "Fishing Products") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 &#x200B;](../assets/uc9-rstudio-results.png)


>[!ENDTABS]

+++
