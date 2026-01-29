---
title: 制限
description: Customer Journey Analyticsの様々な BI ツールの BI 拡張機能のユースケースを制限します
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0962f64e9bc0fed89f52191bebe6dd0e14bde61d
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 1%

---

# 制限


このユースケースでは、2023 年中に発生した上位 5 回の製品名についてレポートします。

+++ Customer Journey Analytics

このユースケースの例では **[!UICONTROL 制限]** パネルは次のようになります。

![Customer Journey Analytics制限パネル ](../assets/cja-limit.png)

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
   1. **[!UICONTROL product_name]** を選択します。
   1. **[!UICONTROL 発生件数の合計]** を選択します。

1. **[!UICONTROL フィルター]** パネルで、次の操作を行います。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL daterange is （すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 相対日付]** を選択します。
   1. フィルターを定義して **[!UICONTROL 値が過去]** **[!UICONTROL 暦年]** に含まれる場合に項目を表示 `1`**[!UICONTROL します]**。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。
   1. **[!UICONTROL このビジュアルのフィルター]** から **[!UICONTROL product_name は（すべて）]** を選択します。
   1. **[!UICONTROL フィルタータイプ]** として **[!UICONTROL 上位 N]** を選択します。
   1. 「**[!UICONTROL 項目を表示]****[!UICONTROL 上位]**」 `5` 「**[!UICONTROL 値別]**」を選択します。
   1. **[!UICONTROL データ]** ペインから **[!UICONTROL 合計回数]** をドラッグ&amp;ドロップし、「**[!UICONTROL データフィールドをここに追加]**」にドロップします。
   1. 「**[!UICONTROL フィルターを適用]**」を選択します。

1. ビジュアライゼーションパネルで、
   * ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、Columns から daterange を削除します。

   Power BI デスクトップは次のようになります。

   ![ 日付範囲名を使用してフィルターを適用するPower BI デスクトップ ](../assets/uc12-powerbi-final.png)

BI 拡張機能を使用してPower BI Desktop が実行するクエリには、`limit` ステートメントが含まれていますが、想定されたステートメントは含まれていません。 Power BI デスクトップでは、明示的な製品名の結果を使用して、上位 5 件の発生件数の制限が適用されます。

```sql
select "_"."product_name",
    "_"."a0"
from 
(
    select "rows"."product_name" as "product_name",
        sum("rows"."occurrences") as "a0"
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
        where (("_"."product_name" in ('Saltwater Monofilament Line', 'Pop-Up Beach Tent', 'Instant Pop-Up Tent', 'Envelop Sleeping Bag', 'Waterproof Tackle Bag')) and "_"."daterange" < date '2024-01-01') and "_"."daterange" >= date '2023-01-01'
    ) "rows"
    group by "product_name"
) "_"
where not "_"."a0" is null
limit 1000001
```

>[!TAB Tableau Desktop]

1. 下部にある「**[!UICONTROL シート 1]**」タブを選択して、「**[!UICONTROL データソース]**」から切り替えます。 **[!UICONTROL シート 1]** ビューで、次の操作を行います。
   1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL テーブル]** リストから **[!UICONTROL Daterange]** エントリをドラッグします。
   1. **[!UICONTROL フィルターフィールド \[Daterange\]]** ダイアログで **[!UICONTROL 日付範囲]** を選択して **[!UICONTROL 次へ >]** を選択します。
   1. **[!UICONTROL フィルター\[Daterange\]]** ダイアログで **[!UICONTROL 相対的な日付]** を選択し、**[!UICONTROL 年]** を選択してから **[!UICONTROL 以前の年]** を選択します。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 製品名]** を **[!UICONTROL 行]** にドラッグします。
   1. **[!UICONTROL テーブル]** リストから **[!UICONTROL 発生件数]** エントリをドラッグし、**[!UICONTROL 列]** の横のフィールドにドロップします。 値が「**[!UICONTROL SUM （発生件数）]**」に変わります。
   1. **[!UICONTROL 表示]** から **[!UICONTROL テキストテーブル]** を選択します。
   1. **[!UICONTROL フィット]** ドロップダウンメニューから **[!UICONTROL フィット幅]** を選択します。
   1. **[!UICONTROL 行]** の **[!UICONTROL 製品名]** を選択します。 ドロップダウンメニューから **[!UICONTROL フィルター]** を選択します。
      1. **[!UICONTROL フィルター\[ 製品名\]]** ダイアログで **[!UICONTROL トップ]** タブを選択します。
      1. **[!UICONTROL フィールド別：]** **[!UICONTROL 上位]** `5` **[!UICONTROL 発生件数別]** **[!UICONTROL 合計]** を選択します。
      1. **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

         ![AlertRed](/help/assets/icons/AlertRed.svg) テーブルが消えていることがわかります。 発生件数別に上位 5 つの製品名を選択しても、このフィルターを使用して正しく機能しない **** 場合。
      1. **[!UICONTROL フィルター]** シェルフの **[!UICONTROL 製品名]** を選択し、ドロップダウンメニューから **[!UICONTROL 削除]** を選択します。 テーブルが再び表示されます。
   1. **[!UICONTROL マーク]** シェルフで **[!UICONTROL SUM （発生件数）]** を選択します。 ドロップダウンメニューから **[!UICONTROL フィルター]** を選択します。
      1. **[!UICONTROL フィルタ \[ オカレンス\]]** ダイアログで **[!UICONTROL 最低]** を選択します。
      1. 値として `47.799` と入力します。 この値を使用すると、テーブルに上位 5 項目のみが表示されます。 **[!UICONTROL 適用]** および **[!UICONTROL OK]** を選択します。

         Tableau Desktop は次のようになります。

         ![Tableau Desktop の制限 ](../assets/uc12-tableau-final.png)

上に示すように、Tableau Desktop が実行するこのクエリは、製品名に対して上位 5 件の発生フィルターを定義すると失敗します。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
  INNER JOIN (
  SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
    SUM("cc_data_view"."occurrences") AS "$__alias__0"
  FROM "public"."cc_data_view" "cc_data_view"
  GROUP BY 1
  ORDER BY 2 DESC,
    1 ASC
  LIMIT 5
) "t0" ON (CAST("cc_data_view"."product_name" AS TEXT) = "t0"."product_name")
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
GROUP BY 1
```

Tableau Desktop で実行されるクエリは、発生件数に対して上位 5 件のフィルターを定義する際に、以下のように表示されます。 制限は、クエリおよび適用されたクライアントサイドには表示されません。

```sql
SELECT CAST("cc_data_view"."product_name" AS TEXT) AS "product_name",
  SUM("cc_data_view"."occurrences") AS "sum:occurrences:ok"
FROM "public"."cc_data_view" "cc_data_view"
WHERE (("cc_data_view"."daterange" >= (TIMESTAMP '2023-01-01 00:00:00.000')) AND ("cc_data_view"."daterange" < (TIMESTAMP '2024-01-01 00:00:00.000')))
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
1. **[!UICONTROL CC データビュー日付範囲]** フィルターを **[!UICONTROL 範囲内]** **[!UICONTROL 2023/01/01]****[!UICONTROL 前）まで]** **[!UICONTROL 2024/01/01]** として指定します。
1. 左側のパネルの「**[!UICONTROL ‣ Cc データビュー]**」セクションから、
   1. **[!UICONTROL 製品名]** を選択します。
   1. 左パネル（下部）の **[!UICONTROL MEASURES]** の下にある **[!UICONTROL Count]** を選択します。
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. **[!UICONTROL 購入収益]** 列で **[!UICONTROL ↓]** （**[!UICONTROL 降順、並べ替え順：1]**）を選択していることを確認します。
1. 「**[!UICONTROL 実行]**」を選択します。
1. 「**[!UICONTROL ‣ビジュアライゼーション]**」を選択します。

以下に示すようなビジュアライゼーションとテーブルが表示されます。

![Looker count distinct](../assets/uc12-looker-result.png)

BI 拡張機能を使用して Looker によって生成されるクエリには `FETCH NEXT 5 ROWS ONLY` が含まれています。これは、制限が Looker と BI 拡張機能を通じて実行されることを意味します。

```sql
-- Looker Query Context '{"user_id":6,"history_slug":"a8f3b1ebd5712413ca1ae695090f70db","instance_slug":"71d4667f0b76c0011463658f45c3f7a3"}' 
SELECT
    cc_data_view."product_name"  AS "cc_data_view.product_name",
    COUNT(*) AS "cc_data_view.count"
FROM
    "public"."cc_data_view" AS "cc_data_view"
WHERE ((( cc_data_view."daterange"  ) >= (DATE_TRUNC('day', DATE '2023-01-31')) AND ( cc_data_view."daterange"  ) < (DATE_TRUNC('day', DATE '2024-01-01'))))
GROUP BY
    1
ORDER BY
    2 DESC
FETCH NEXT 5 ROWS ONLY
```


>[!TAB Jupyter Notebook]

1. 新しいセルに次のステートメントを入力します。

   ```python
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               GROUP BY 1 \
               ORDER BY `Events` DESC \
               LIMIT 5;
   display(data)
   ```

1. セルを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![Jupyter Notebook の結果 ](../assets/uc12-jupyter-results.png)

クエリは、Jupyter Notebook で定義されているように、BI 拡張機能によって実行されます。

>[!TAB RStudio]

1. 新しいチャンクで、` ```{r} ` と ` ``` ` の間に次のステートメントを入力します。

   ```R
   ## Dimension 1 Limited
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2024-01-01") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE) %>%
      head(5)
   print(df)
   ```

1. チャンクを実行します。 以下のスクリーンショットのような出力が表示されます。

   ![RStudio の結果 ](../assets/uc12-rstudio-results.png)

RStudio が BI 拡張機能を使用して生成するクエリには `LIMIT 5` が含まれています。これは、RStudio と BI 拡張機能によって制限が適用されることを意味します。

```sql
SELECT "product_name", COUNT(*) AS "n"
FROM (
  SELECT "cc_data_view".*
  FROM "cc_data_view"
  WHERE ("daterange" >= '2023-01-01' AND "daterange" < '2024-01-01')
) AS "q01"
GROUP BY "product_name"
ORDER BY "n" DESC
LIMIT 5
```

>[!ENDTABS]

+++
