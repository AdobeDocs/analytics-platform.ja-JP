---
title: 月次トレンド
description: Customer Journey Analyticsの様々なBI ツールでのBI拡張機能の月次トレンドユースケース
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: 9be5180e-6926-431e-aa70-61cb98130ef6
autotag-review: '2026-05-19T09:42:27.611Z'
TQID: 'https://experienceleague.adobe.com/-dIZ7-pLL2i8dFOLWIWqjyqMVGwsMMfHnKu72ZS-jOU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: f24857a4-4b64-4b25-b237-d43026362144
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 802
ht-degree: 0%

---

# 月次トレンド


このユースケースでは、2023年の毎月の発生傾向（イベント）を示すテーブルと簡単な行のビジュアライゼーションを表示します。

+++ Customer Journey Analytics

使用例の&#x200B;**[!UICONTROL 月次トレンド]** パネルの例：

![Customer Journey Analytics月次トレンドのビジュアライゼーション ](../assets/cja_monthly_trend.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>接続が成功したことを[検証し、データビューを一覧表示でき、このユースケースを試すBI ツールにデータビュー](connect-and-validate.md)を使用していることを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterangemonth]**&#x200B;を選択します。
   1. **[!UICONTROL 合計回数]**&#x200B;を選択します。

   現在の月の発生件数を示すテーブルが表示されます。 可視性を高めるには、ビジュアライゼーションを拡大します。

1. **[!UICONTROL フィルター]** ペインで、次の操作を行います。

   1. このビジュアル ]**の**[!UICONTROL  フィルターから&#x200B;**[!UICONTROL daterangemonth is （All）]**&#x200B;を選択します。
   1. **[!UICONTROL 詳細フィルタリング]**&#x200B;を&#x200B;**[!UICONTROL フィルタータイプ]**&#x200B;として選択します。
   1. 値&#x200B;]****[!UICONTROL &#x200B;が&#x200B;]**`1/1/2023`以降**[!UICONTROL &#x200B;および&#x200B;]****[!UICONTROL &#x200B;が&#x200B;]**`1/1/2024.`より前の場合に**[!UICONTROL &#x200B;項目を表示するようにフィルターを定義します。カレンダーアイコンを使用して、日付を選択できます。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

   適用された&#x200B;**[!UICONTROL daterangemonth]** フィルターでテーブルが更新されます。

1. **[!UICONTROL ビジュアライゼーション]** ペインで、次の操作を行います。

   1. **[!UICONTROL 折れ線グラフ]**&#x200B;のビジュアライゼーションを選択します。

   折れ線グラフのビジュアライゼーションは、表と同じデータを使用している間に表を置き換えます。 Power BI デスクトップは以下のようになります。

   ![Power BI Desktop ユースケース 2日付範囲フィルター](../assets/uc4-pbi-filter-daterange.png)

1. 折れ線グラフのビジュアライゼーション：

   1. ![詳細](/help/assets/icons/More.svg)を選択します。
   1. コンテキストメニューから、**[!UICONTROL テーブルとして表示]**&#x200B;を選択します。

   メインビューが更新され、行のビジュアライゼーションと表の両方が表示されます。 Power BI デスクトップは以下のようになります。

   ![Power BI デスクトップ版ユースケース 2の最終的な日次トレンドのビジュアライゼーション ](../assets/uc4-pbi-filter-final.png)

>[!TAB Tableau Desktop]

1. 下部の「**[!UICONTROL シート 1]**」タブを選択して、**[!UICONTROL データソース]**&#x200B;から切り替えます。 **[!UICONTROL シート 1]** ビューで：
   1. **[!UICONTROL Data]** ペインの&#x200B;**[!UICONTROL Tables]** リストから&#x200B;**[!UICONTROL Daterange]** エントリをドラッグし、エントリを&#x200B;**[!UICONTROL Filters]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで、**[!UICONTROL 日付の範囲]**&#x200B;を選択し、**[!UICONTROL 次>]**&#x200B;を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで、**[!UICONTROL 日付の範囲]**&#x200B;を選択し、`01/01/2023` ～ `01/01/2024`の期間を指定します。

      ![Tableau Desktop Filter](../assets/uc4-tableau-filter.png)

   1. **[!UICONTROL Data]** ペインの&#x200B;**[!UICONTROL Tables]** リストから&#x200B;**[!UICONTROL Daterangeday]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL 列]**&#x200B;の横にあるフィールドにエントリをドロップします。
      * **[!UICONTROL Daterangeday]** ドロップダウンメニューから&#x200B;**[!UICONTROL MONTH]**&#x200B;を選択し、値を&#x200B;**[!UICONTROL MONTH （Daterangeday）]**&#x200B;に更新します。
   1. **[!UICONTROL データ]** ペインの&#x200B;**[!UICONTROL テーブル （*メジャー名*）]** リストから&#x200B;**[!UICONTROL 発生回数]**&#x200B;をドラッグ&amp;ドロップし、**[!UICONTROL 行]**&#x200B;の横にあるフィールドにエントリをドロップします。 値は自動的に&#x200B;**[!UICONTROL SUM （Occurrences）]**&#x200B;に変換されます。
   1. ツールバーの「**[!UICONTROL フィット]**」ドロップダウンメニューから「**[!UICONTROL 標準]**」を「**[!UICONTROL ビュー全体]**」に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Graph](../assets/uc4-tableau-graph.png)

1. 「**[!UICONTROL シート 1]**」タブのコンテキストメニューから「**[!UICONTROL 複製]**」を選択して、2番目のシートを作成します。
1. 「**[!UICONTROL シート 1]**」タブのコンテキストメニューから「**[!UICONTROL 名前を変更]**」を選択して、シートの名前を`Graph`に変更します。
1. 「**[!UICONTROL シート 1 （2）]**」タブのコンテキストメニューから「**[!UICONTROL 名前を変更]**」を選択して、シートの名前を`Data`に変更します。
1. **[!UICONTROL Data]** シートが選択されていることを確認します。 データビューで、次の操作を行います。
   1. 右上の「**[!UICONTROL 自分を表示]**」を選択し、「**[!UICONTROL テキストテーブル]**」（左上のビジュアライゼーション）を選択して、データビューのコンテンツをテーブルに変更します。
   1. **[!UICONTROL MONTH （Daterangeday）]**&#x200B;を&#x200B;**[!UICONTROL 列]**&#x200B;から&#x200B;**[!UICONTROL 行]**&#x200B;にドラッグします。
   1. ツールバーの「**[!UICONTROL フィット]**」ドロップダウンメニューから「**[!UICONTROL 標準]**」を「**[!UICONTROL ビュー全体]**」に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Data](../assets/uc4-tableau-data.png)

1. 「**[!UICONTROL 新しいダッシュボード]**」タブボタン（下部）を選択して、新しい&#x200B;**[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL グラフ]** シートを&#x200B;**[!UICONTROL シート]** シェルフから&#x200B;*シートをここにドロップ*&#x200B;する&#x200B;**[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. **[!UICONTROL グラフ]** シートの下の&#x200B;**[!UICONTROL シート]** シェルフから&#x200B;**[!UICONTROL データ]** シートを&#x200B;**[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビューで&#x200B;**[!UICONTROL データ]** シートを選択し、**[!UICONTROL ビュー全体]**&#x200B;を&#x200B;**[!UICONTROL 幅を修正]**&#x200B;に変更します。

      Tableau デスクトップは以下のようになります。

      ![Tableau Desktop Dashboard 1](../assets/uc4-tableau-dashboard.png)


>[!TAB Looker]

1. Lookerの&#x200B;**[!UICONTROL Explore]** インターフェイスで、クリーンな設定が行われていることを確認します。 そうでない場合は、![設定](/help/assets/icons/Setting.svg) **[!UICONTROL フィールドとフィルターの削除]**&#x200B;を選択します。
1. 「**[!UICONTROL フィルター]**」の下の「**[!UICONTROL + フィルター]**」を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログ：
   1. **[!UICONTROL ‣ Cc データビュー]**&#x200B;を選択
   1. フィールドのリストから、**[!UICONTROL }‣ Daterange Date]**、次に&#x200B;**[!UICONTROL Daterange Date]**を選択します。
      ![Looker フィルター](../assets/uc2-looker-filter.png)
1. **[!UICONTROL Cc データビューの日付変更日]** フィルターを&#x200B;**[!UICONTROL が範囲]** **[!UICONTROL 2023/01/01]** **[!UICONTROL から（前）]** **[!UICONTROL 2024/01/01]**&#x200B;に指定します。
1. 左側の&#x200B;**[!UICONTROL Cc データビュー]** パネルから，
   1. **[!UICONTROL ディメンション]**&#x200B;のリストから&#x200B;**[!UICONTROL ‣Daterangemonth Date]**、次に&#x200B;**[!UICONTROL Month]**&#x200B;を選択します。
   1. 左パネル（下部）の&#x200B;**[!UICONTROL 測定]**&#x200B;の下にある&#x200B;**[!UICONTROL カウント]**&#x200B;を選択します。
1. **[!UICONTROL 実行]**&#x200B;を選択します。
1. 行のビジュアライゼーションを表示するには、**[!UICONTROL ‣ ビジュアライゼーション]**&#x200B;を選択します。

次のようなビジュアライゼーションと表が表示されます。

![Looker結果の日次トレンド ](../assets/uc4-looker-result.png)


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT daterangemonth AS Month, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
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

   ![Jupyter Notebookの結果](../assets/uc4-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクに次のコードブロックを入力します。

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

   ![RStudio結果](../assets/uc4-rstudio-results.png)

>[!ENDTABS]

+++
