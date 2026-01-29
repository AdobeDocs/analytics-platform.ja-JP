---
title: 並べ替え
description: Customer Journey Analyticsの様々な BI ツールでの BI 拡張機能の並べ替えのユースケース
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 1%

---

# 並べ替え


このユースケースでは、2023 年 1 月の製品名の購入収益と購入を、購入収益の降順に並べ替えてレポートします。

+++ Customer Journey Analytics

このユースケースでは、例えば **[!UICONTROL 並べ替え]** パネルを使用します。

![Customer Journey Analytics並べ替えパネル ](../assets/cja-sort.png)

+++

+++ BI ツール

>[!PREREQUISITES]
>
>このユースケースを試す BI ツールについて、[ 接続に成功し、データビューをリストし、データビューを使用できる ](connect-and-validate.md) ことを検証したことを確認します。
>

>[!BEGINTABS]

>[!TAB Power BI デスクトップ ]

1. **[!UICONTROL データ]** ペインで、次の操作を行います。
   1. **[!UICONTROL daterange]** を選択します。
   1. **[!UICONTROL product_namr]** を選択します。
   1. **[!UICONTROL sum purchase_revenue]** を選択します。
   1. 「**[!UICONTROL 購入を合計]**」を選択します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として「**[!UICONTROL 詳細フィルタリング]**」を選択します。
   1. **[!UICONTROL 値が次の値の場合に項目を表示]****[!UICONTROL が次の値以上の場合に項目を表示]**`1/1/2023`**[!UICONTROL および]****[!UICONTROL が次の値の前]**`2/1/2023` のフィルターを定義してください。

1. ビジュアライゼーション パネルで、次の操作を行います。
   1. ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、Columns から daterange を削除します。
   1. **[!UICONTROL purchase_revenue の合計]** を **[!UICONTROL 列]** 項目の下部にドラッグします。

1. レポートで、「**[!UICONTROL purchase_revenue の合計]** を選択して、購買収益の降順でテーブルをソートします。

   Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](../assets/uc11-powerbi-final.png)

BI 拡張機能を使用してPower BI Desktop が実行するクエリには、`sort` ステートメントが含まれていません。 `sort` ステートメントがないということは、並べ替えがクライアントサイドで実行されることを意味します。

```sql
select "_"."product_name",
    "_"."a0",
    "_"."a1"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."purchases") as "a0",
        sum("rows"."purchase_revenue") as "a1"
    from 
    (
        select "_"."daterangeName",
            "_"."daterange",
            "_"."filterId",
            "_"."filterName",
            "_"."timestamp",
            "_"."affiliate_name",
            "_"."affiliate_url",
            "_"."commerce.order.priceTotal",
            "_"."customer_city",
            "_"."customer_region",
            "_"."daterangeday",
            "_"."daterangefifteenminute",
            "_"."daterangefiveminute",
            "_"."daterangehour",
            "_"."daterangeminute",
            "_"."daterangemonth",
            "_"."daterangequarter",
            "_"."daterangesecond",
            "_"."daterangethirtyminute",
            "_"."daterangeweek",
            "_"."daterangeyear",
            "_"."hitdatetime",
            "_"."page_name",
            "_"."page_url",
            "_"."product_category",
            "_"."product_name",
            "_"."product_short_review",
            "_"."product_subCategory",
            "_"."referrer_url",
            "_"."search_engine",
            "_"."search_keywords",
            "_"."store_city",
            "_"."store_name",
            "_"."store_region",
            "_"."store_type",
            "_"."timepartdayofmonth",
            "_"."timepartdayofweek",
            "_"."timepartdayofyear",
            "_"."timeparthourofday",
            "_"."timepartminuteofhour",
            "_"."timepartmonthofyear",
            "_"."timepartquarterofyear",
            "_"."timepartweekofyear",
            "_"."cm_session_end_rate_defaultmetric",
            "_"."cm_session_person_defaultmetric",
            "_"."cm_session_start_rate_defaultmetric",
            "_"."cm_timespent_person_defaultmetric",
            "_"."cm_timespent_session_defaultmetric",
            "_"."cm_product_name_count_distinct",
            "_"."ad_views",
            "_"."adobe_sessionends",
            "_"."adobe_sessionstarts",
            "_"."adobe_timespent",
            "_"."exchange_buybacks",
            "_"."exchange_cost",
            "_"."exchange_purchases",
            "_"."exchange_revenue",
            "_"."occurrences",
            "_"."page_views",
            "_"."product_quantity",
            "_"."product_reviews",
            "_"."product_views",
            "_"."purchase_revenue",
            "_"."purchases",
            "_"."visitors",
            "_"."visits"
        from "public"."cc_data_view" "_"
        where "_"."daterange" < date '2023-02-01' and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null or not "_"."a1" is null
limit 1000001
```


>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択し、`01/01/2023` - `1/2/2023` を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** をドラッグし、**[!UICONTROL 行]** の横のフィールドにエントリをドロップします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 購入]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が **[!UICONTROL SUM （Purchases）]** に変更されます。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 購入売上高]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールド、**[!UICONTROL SUM （購入）]** の横のエントリをドロップします。 値が「**[!UICONTROL SUM （Purchase Revenue）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。
   1. **[!UICONTROL 購入収益]** 列ヘッダーを選択し、この列のテーブルを降順で並べ替えます。

      Tableau Desktop は次のようになります。

      ![Tableau Desktop 並べ替え ](../assets/uc11-tableau-final.png)

BI 拡張機能を使用して Tableau Desktop で実行されるクエリには、`sort` ステートメントが含まれていません。 この `sort` ステートメントがないということは、並べ替えがクライアント側で実行されることを意味します。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok",
  SUM("cc_data_view"."purchase_revenue") AS "sum:purchase_revenue:ok",
  SUM("cc_data_view"."purchases") AS "sum:purchases:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (DATE '2023-01-01')) AND ("cc_data_view"."daterange" <= (DATE '2023-02-01')))
GROUP BY 1
```

>[!TAB Looker]

1. Looker の **[!UICONTROL 探索]** インターフェイスで、接続を更新します。 「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL キャッシュのクリアと更新]**」を選択します。
1. Looker の **[!UICONTROL 探索]** インターフェイスで、クリーンな設定ができていることを確認します。 そうでない場合は、「![ 設定 ](/help/assets/icons/Setting.svg)**[!UICONTROL フィールドとフィルターを削除]**」を選択します。
1. **[!UICONTROL フィルター]** の下の「**[!UICONTROL + フィルター]** を選択します。
1. **[!UICONTROL フィルターを追加]** ダイアログで、次の手順を実行します。
   1. 「**[!UICONTROL ‣ Cc データビュー」を選択します]**
   1. フィールドのリストから、「**[!UICONTROL ‣Daterange Date」を選択し]** 「**[!UICONTROL Daterange Date]**」を選択します。
      ![Looker フィルター ](../assets/uc2-looker-filter.png)
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2023/02/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションで、「**[!UICONTROL 製品名]**」を選択します。
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
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](../assets/uc11-looker-result.png)


BI 拡張機能を使用して Looker によって生成されるクエリには `ORDER BY` が含まれています。これは、Looker および BI 拡張機能を使用して並べ替えが実行されることを意味します。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"fc83573987b999306eaf6e1a3f2cde70","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COALESCE(SUM(CAST(( cc_data_view."purchase_revenue"  ) AS DOUBLE PRECISION)), 0) AS "purchase_revenue"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2024-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2023-02-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 500 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   data = %sql SELECT product_name AS `Product Name`, SUM(purchase_revenue) AS `Purchase Revenue`, SUM(purchases) AS `Purchases` \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Purchase Revenue` DESC \
               LIMIT 5;
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 ](../assets/uc11-jupyter-results.png)

クエリは、Jupyter Notebook で定義されているように、BI 拡張機能によって実行されます。


>[!TAB RStudio]

1. 新しいチャンクで、` ```{r} ` と ` ``` ` の間に次のステートメントを入力します。

   ```R
   ## Dimension 1 Sorted
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01") %>%
      group_by(product_name) %>%
      summarise(purchase_revenue = sum(purchase_revenue), purchases = sum(purchases), .groups = "keep") %>%
      arrange(desc(purchase_revenue), .by_group = FALSE)
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 ](../assets/uc11-rstudio-results.png)

RStudio が BI 拡張機能を使用して生成するクエリには `ORDER BY` が含まれています。これは、RStudio と BI 拡張機能を通じて順序が適用されることを意味します。

```sql
SELECT
  "product_name",
  SUM("purchase_revenue") AS "purchase_revenue",
  SUM("purchases") AS "purchases"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2023-02-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "purchase_revenue" DESC
LIMIT 1000
```

>[!ENDTABS]

+++
