---
title: 毎時トレンド
description: Customer Journey Analyticsの様々な BI ツールにおける BI 拡張機能の時間別トレンドユースケース
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---

# 毎時トレンド


## 毎時トレンド

このユースケースでは、2023 年 1 月 1 日の発生件数（イベント）の 1 時間ごとのトレンドを表示するテーブルと単純な線のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 時間別トレンド]** パネル：

![Customer Journey Analyticsの時間別トレンドビジュアライゼーション ](../assets/cja_hourly_trend.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](connect-and-validate.md) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

![AlertRed](/help/assets/icons/AlertRed.svg) Power BIは日時フィールドの処理方法を **認識** ていないので、**[!UICONTROL daterangehour]** や **[!UICONTROL daterangeminute]** などのディメンションはサポートされていません。

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` ～ `02/01/2023` の期間を指定します。

      ![Tableau Desktop フィルター ](../assets/uc3-tableau-filter.png)

   1. **[!UICONTROL データ]** ペインの「**[!UICONTROL テーブル]**」リストから **[!UICONTROL Daterangehour]** をドラッグ&amp;ドロップし、「**[!UICONTROL 列]**」の横のフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから **[!UICONTROL More]** > **[!UICONTROL Hours]** を選択し、値が **[!UICONTROL HOUR （Daterangeday）]** に更新されるようにします。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル（*メジャー名*）]** リストから **[!UICONTROL 発生件数]** をドラッグ&amp;ドロップし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。 値は自動的に **[!UICONTROL SUM （発生件数）]** に変換されます。
   1. ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL 標準]** を **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop グラフ ](../assets/uc3-tableau-graph.png)

1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 複製]** を選択し、2 番目のシートを作成します。
1. [**[!UICONTROL シート 1]**] タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Graph` に変更します。
1. **[!UICONTROL シート 1 （2）]** タブの右クリック メニューから **[!UICONTROL 名前変更]** を選択して、シートの名前を `Data` に変更します。
1. **[!UICONTROL データ]** シートが選択されていることを確認します。 **[!UICONTROL データ]** 表示で、次の操作を行います。
   1. 右上の **[!UICONTROL 表示]** を選択し、**[!UICONTROL テキストテーブル]** （左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. **[!UICONTROL HOUR （Daterangeday）]** を **[!UICONTROL Columns]** から **[!UICONTROL Rows]** にドラッグします。
   1. ツールバーの **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL 標準]** を **[!UICONTROL ビュー全体]** に変更します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop データ ](../assets/uc3-tableau-data.png)

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL Sheets]** シェルフから **[!UICONTROL Graph]** シートを **[!UICONTROL Dashboard 1]** ビュー（「シートをここにドロップ *」と表示されているビュー* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL グラフ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで **[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]** を **[!UICONTROL 固定幅]** に変更します。

      **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

      ![Tableau Desktop ダッシュボード 1](../assets/uc3-tableau-dashboard.png)


>[!TAB Looker]


1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](../assets/uc2-looker-filter.png)
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/01/02]** として指定します。
1. 左側のパネルの「**[!UICONTROL Cc データビュー]**」セクションから、
   1. 「**[!UICONTROL ‣ Daterangehour Date]**」を選択し、「**[!UICONTROL DIMENSIONS]**」のリストから「**[!UICONTROL Time]**」を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](../assets/uc3-looker-result.png)


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangehour AS Hour, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-01-02' \
               GROUP BY 1 \
                ORDER BY Hour ASC
   df = data.DataFrame()
   df = df.groupby('Hour', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.lineplot(x='Hour', y='Events', data=df)
   plt.show()
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 ](../assets/uc3-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクで、` ```{r} ` と ` ``` ` の間に次のステートメントを入力します。

   ```R
   ## Hourly Events
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-01-02") %>%
      group_by(daterangehour) %>%
      count() %>%
      arrange(daterangehour, .by_group = FALSE)
   ggplot(df, aes(x = daterangehour, y = n)) +
      geom_line(color = "#69b3a2") +
      ylab("Events") +
      xlab("Hour")
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 ](../assets/uc3-rstudio-results.png)

>[!ENDTABS]

+++
