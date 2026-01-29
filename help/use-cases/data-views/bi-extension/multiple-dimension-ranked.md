---
title: 複数のDimensionがランク付け
description: Customer Journey Analyticsの様々な BI ツールでの BI 拡張機能の複数ディメンションランクのユースケース
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 1%

---

# 複数のディメンションのランク


このユースケースでは、2023 年を超える製品カテゴリ内の製品名について、購入収益と購入を分類したテーブルを表示する必要があります。 その上に、いくつかのビジュアライゼーションを使用して、各製品カテゴリ内での製品カテゴリ分布と製品名の貢献度の両方を示します。

+++ Customer Journey Analytics

ユースケースの例 **[!UICONTROL 複数のDimensionのランク付け]** パネルを次に示します。

![Customer Journey Analyticsの複数のDimensionのランクパネル ](../assets/cja-multiple-dimension-ranked.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](connect-and-validate.md) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. 日付範囲をすべてのビジュアライゼーションに確実に適用するには、**[!UICONTROL データ]** パネルから **[!UICONTROL このページのフィルター]** に **[!UICONTROL daterangeday]** をドラッグ&amp;ドロップします。
   1. **[!UICONTROL このページのフィルター]** から **[!UICONTROL daterangeday is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 相対日付]** を選択します。
   1. フィルターを定義して **[!UICONTROL 値が過去]** **[!UICONTROL 暦年]** に含まれる場合に項目を表示 `1`**[!UICONTROL します]**。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL datarangeday]** を選択します。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. **[!UICONTROL sum purchase_revenue]** を選択します
   1. 「**[!UICONTROL 購入の合計]**」を選択します。

1. 縦棒グラフをテーブルに変更するには、テーブルが選択されていることを確認し、**[!UICONTROL ビジュアライゼーション]** ペインから **[!UICONTROL マトリックス]** を選択します。
   * **[!UICONTROL product_name]** を **[!UICONTROL 列]** からドラッグし、[!UICONTROL  行 ] の****[!UICONTROL product_categor]****y の下にあるフィールドを **[!UICONTROL ビジュアライゼーション]** ペインにドロップします。

1. テーブル内に表示される製品の数を制限するには、**[!UICONTROL フィルター]** ペインで **[!UICONTROL product_name is （All）]** を選択します。

   1. **[!UICONTROL 詳細フィルター]** を選択します。
   1. **[!UICONTROL フィルタータイプ]****[!UICONTROL 上位 N]****[!UICONTROL 項目を表示]****[!UICONTROL 上位]**`15`**[!UICONTROL 値別]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 購入]** を **[!UICONTROL ここにデータフィールドを追加]** にドラッグします。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. 読みやすくするには、トップメニューから **[!UICONTROL 表示]** を選択し、**[!UICONTROL ページビュー]**/**[!UICONTROL 実際のサイズ]** を選択して、テーブルビジュアライゼーションのサイズを変更します。

1. テーブルの各カテゴリを分類するには、製品カテゴリレベルで **[!UICONTROL +]** を選択します。 Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションのランク付けマトリックス テーブル ](../assets/uc6-powerbi-data.png)

1. 上部のメニューから **[!UICONTROL ホーム]** を選択し、「**[!UICONTROL 新しいビジュアル]** を選択します。 新しいビジュアルがレポートに追加されます。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL product_name]** を選択します。
   1. **[!UICONTROL purchase_revenue]** を選択します。

1. ビジュアルを変更するには、棒グラフを選択し、「**[!UICONTROL ビジュアライゼーション]** パネルから **[!UICONTROL ツリーマップ]** を選択します。
1. **[!UICONTROL product_category]** が **[!UICONTROL Category]** の下にリストされ、**[!UICONTROL product_name]** が **[!UICONTROL ビジュアライゼーション]** ペインの **[!UICONTROL 詳細]** の下にリストされていることを確認します。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションのランクツリーマップ ](../assets/uc6-powerbi-treemap.png)

1. 上部のメニューから **[!UICONTROL ホーム]** を選択し、「**[!UICONTROL 新しいビジュアル]** を選択します。 新しいビジュアルがレポートに追加されます。

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL product_category]** を選択します。
   1. **[!UICONTROL purchase_revenue]** を選択します。
   1. **[!UICONTROL 購入]** を選択します。

1. **[!UICONTROL ビジュアライゼーション]** パネルで、
   1. ビジュアライゼーションを変更するには、**[!UICONTROL 折れ線グラフと積み重ね柱状グラフ]** を選択します。
   1. **[!UICONTROL 列の y 軸]** から **[!UICONTROL 行の y 軸]** に **[!UICONTROL sum_of_purchases]** をドラッグします。

1. レポートで、個々のビジュアライゼーションを再シャッフルします。

   Power BI デスクトップは次のようになります。

   ![Power BI Desktop の複数ディメンションが最終ランクに ](../assets/uc6-powerbi-final.png) りました


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop Multiple Dimension Rank Filter](../assets/uc6-tableau-filter.png)

   1. **[!UICONTROL 製品カテゴリ]** をドラッグして、「列 **[!UICONTROL の横にドロップ]** ます。
   1. **[!UICONTROL 購入売上高]** をドラッグし、「行 **[!UICONTROL の横にドロップ]** ます。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. 「購入」をドラッグし、「**[!UICONTROL 行]**」の横にドロップします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL SUM （Purchases）]** を選択し、ドロップダウンメニューから **[!UICONTROL 二重軸]** を選択します。
   1. **[!UICONTROL マーク]** で **[!UICONTROL SUM （Purchases）]** を選択し、ドロップダウンメニューから **[!UICONTROL Line]** を選択します。
   1. **[!UICONTROL マーク]** で **[!UICONTROL SUM （Purchase Revenue）]** を選択し、ドロップダウンメニューから **[!UICONTROL 棒グラフ]** を選択します。
   1. **[!UICONTROL フィット]** メニューから **[!UICONTROL ビュー全体]** を選択します。
   1. グラフの **[!UICONTROL 購買収益]** タイトルを選択し、購買収益が昇順であることを確認します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop 複数ディメンションのランク付けカテゴリ ](../assets/uc6-tableau-category.png)

1. 現在の **[!UICONTROL シート 1]** シートの名前を `Category` に変更します。
1. **[!UICONTROL 新規ワークシート]** を選択して新規シートを作成し、名前を `Data` に変更します。

   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** に **[!UICONTROL 購入売上高]** をドラッグします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL 購入]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグし、**[!UICONTROL 購入収益]** の横にドラッグします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL 製品カテゴリ]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグし、**[!UICONTROL 製品カテゴリ]** の横にドラッグします。
   1. 2 つの横棒をテーブルに変更するには、「**[!UICONTROL 表示]**」から「**[!UICONTROL テキスト表]**」を選択します。
   1. 製品数を制限するには、「**[!UICONTROL 測定値]**」で「**[!UICONTROL 購入]**」を選択します。 ドロップダウンメニューから、「**[!UICONTROL フィルター]**」を選択します。
   1. **[!UICONTROL フィルター\[ 購入\]]** ダイアログで **[!UICONTROL 少なくとも]** を選択し、`7000` と入力します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop の複数Dimensionのランクデータ ](../assets/uc6-tableau-data.png)

1. **[!UICONTROL 新規ワークシート]** を選択して新しいシートを作成し、名前を **[!UICONTROL ツリーマップ]** に変更します。
   1. **[!UICONTROL データ]** ペインの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグし、**[!UICONTROL フィルター]** シェルフにドロップします。
   1. **[!UICONTROL フィルターフィールド\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 前年]** を指定します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 行]** に **[!UICONTROL 購入売上高]** をドラッグします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 購入]** を **[!UICONTROL 行]** にドラッグし、**[!UICONTROL 購入収益]** の横にドラッグします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL 製品カテゴリ]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグします。
   1. **[!UICONTROL 製品名]** を **[!UICONTROL データ]** ペインから **[!UICONTROL 列]** にドラッグします。
   1. 2 つの縦棒グラフをツリーマップに変更するには、「**[!UICONTROL 表示]**」から「**[!UICONTROL ツリーマップ]**」を選択します。
   1. 製品数を制限するには、「**[!UICONTROL 測定値]**」で「**[!UICONTROL 購入]**」を選択します。 ドロップダウンメニューから、「**[!UICONTROL フィルター]**」を選択します。
   1. **[!UICONTROL フィルター\[ 購入\]]** ダイアログで **[!UICONTROL 少なくとも]** を選択し、`7000` と入力します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop の複数Dimensionのランクデータ ](../assets/uc6-tableau-treemap.png)

1. **[!UICONTROL 新規ダッシュボード]**」タブボタン（下部）を選択して、新しい **[!UICONTROL ダッシュボード 1]** ビューを作成します。 **[!UICONTROL ダッシュボード 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL カテゴリ]** シートを **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビュー（「シートをここにドロップ *」と表示される* にドラッグ&amp;ドロップします。
   1. **[!UICONTROL ツリーマップ]** シートを、**[!UICONTROL カテゴリ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. **[!UICONTROL データ]** シートを、**[!UICONTROL ツリーマップ]** シートの下にある **[!UICONTROL シート]** シェルフから **[!UICONTROL ダッシュボード 1]** ビューにドラッグ&amp;ドロップします。
   1. ビュー内の各シートのサイズを変更します。

   **[!UICONTROL ダッシュボード 1]** ビューは次のようになります。

   ![Tableau Desktop ダッシュボード 1](../assets/uc6-tableau-final.png)


>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](../assets/uc2-looker-filter.png)
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品カテゴリ]** を選択します。
   1. **[!UICONTROL 製品名]** を選択します。
1. 左パネルの「**[!UICONTROL ‣カスタムフィールド]**」セクションから：
   1. 「**[!UICONTROL +追加]**」ドロップダウンメニューから「**[!UICONTROL カスタム測定]**」を選択します。
   1. **[!UICONTROL カスタム測定を作成]** ダイアログで、次の手順を実行します。
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入売上高]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchase Revenue`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「`0` 小数 **[!UICONTROL 」]** 入力されていることを確認します。
         ![Looker カスタム指標フィールド ](../assets/uc5-looker-customfield.png)
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 「**[!UICONTROL +追加]**」ドロップダウンメニューから **[!UICONTROL カスタム測定]** をもう一度選択します。 **[!UICONTROL カスタムを作成]** メジャーダイアログで、
      1. **[!UICONTROL 測定するフィールド]** ドロップダウンメニューから **[!UICONTROL 購入]** を選択します。
      1. **[!UICONTROL 測定タイプ]** ドロップダウンメニューから **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 名前]** のカスタムフィールド名を入力します。 例：`Sum of Purchases`。
      1. **[!UICONTROL フィールドの詳細]** タブを選択します。
      1. **[!UICONTROL 形式]** ドロップダウンメニューから「**[!UICONTROL 小数]**」を選択し、「`0` 小数 **[!UICONTROL 」]** 入力されていることを確認します。
      1. 「**[!UICONTROL 保存]**」を選択します。
   1. 両方のフィールドがデータビューに自動的に追加されます。
1. 「**[!UICONTROL フィルター]**」セクションで、「**[!UICONTROL + フィルター]**」を選択します。 **[!UICONTROL フィルターを追加]** ダイアログで以下を行います。 「**[!UICONTROL ‣カスタムフィールド]**」を選択し、「**[!UICONTROL 購入収益]**」を選択します。
1. **[!UICONTROL is >]** を選択し、`800000` と入力して結果を制限します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択して、折れ線グラフのビジュアライゼーションを表示します。
1. **[!UICONTROL ビジュアライゼーション]** の「**[!UICONTROL 編集]**」を選択して、ビジュアライゼーションを更新します。 ポップアップダイアログで以下を行います。
   1. 「**[!UICONTROL プロット]**」タブを選択します。
   1. 下にスクロールして、「**[!UICONTROL グラフ設定を編集]**」を選択します。
   1. 以下のスクリーンショットに示すように **** グラフ設定（上書き）で JSON を変更し、「**[!UICONTROL プレビュー]**」を選択します。

      ![Looker 検証設定 ](../assets/uc6-looker-visualization.png)

   1. 「**[!UICONTROL 適用]**」を選択します。
   1. ![ 編集 ](/help/assets/icons/CrossSize75.svg) の横にある **[!UICONTROL CrossSize75]** を選択して、ポップアップダイアログを非表示にします

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker 結果日別トレンド ](../assets/uc6-looker-result.png)


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_category AS `Product Category`, product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01' \
               GROUP BY 1, 2 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby(['Product Category', 'Product Name'], as_index=False).sum()
   plt.figure(figsize=(8, 8))
   sns.scatterplot(x='Product Category', y='Product Name', size='Purchase Revenue', sizes=(10, 200), hue='Purchases', palette='husl', data=df)
   plt.show()
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 ](../assets/uc6-jupyter-results.png)


>[!TAB RStudio]

1. 新しいチャンクで、` ```{r} ` と ` ``` ` の間に次のステートメントを入力します。

   ```R
   ## Multiple dimensions ranked
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_category, product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 ](../assets/uc6-rstudio-results.png)


>[!ENDTABS]

+++
