---
title: 日付範囲の作成
description: レポートで使用する日付範囲を作成します。
feature: Calendar
exl-id: 3e4fa3cc-c14b-45e5-afbb-518ecfa0033e
role: User
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 39%

---

# 日付範囲の作成


誰でもカスタムの日付範囲を作成できます。 日付範囲は、次の方法で作成します。

![注釈の作成](assets/create-date-range.png)

* ??メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 日付範囲]**」を選択します。 [[!UICONTROL  日付範囲 ](/help/assets/icons/AddCircle.svg) マネージャー ](/help/components/date-ranges/manage.md) から「![AddCircle][!UICONTROL **[!UICONTROL Add]**]」を選択します。
* ??Workspace プロジェクトで、ビジュアライゼーションのコンテキストメニューから「**[!UICONTROL この日付範囲に対するカスタムの日付範囲]**」を選択します。
* ??Workspace プロジェクトで、メニューから **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL 日付範囲を作成]** を選択します。
* ??Workspace プロジェクトで、ショートカットキー **[!UICONTROL ctrl+shift+d]** （Windows）または **[!UICONTROL shift+command+d]** （macOS）を使用します。
* ??Workspace プロジェクトのコンポーネント左パネルで、「![ カレンダー ](/help/assets/icons/Add.svg)**日付範囲 ![ に ](/help/assets/icons/Calendar.svg) 「追加**」を選択します。

注釈を定義するには、[[!UICONTROL  日付範囲ビルダー ]](#annotation-builder) を使用します。

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 日付範囲ビルダー {#date-range-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="終了時間"
>abstract="終了時間には常に 59 秒が含まれます。"

<!-- markdownlint-enable MD034 -->




**[!UICONTROL 新しい日付範囲]** または **[!UICONTROL 日付範囲を編集]** ダイアログを使用して、新しい日付範囲を作成または既存の日付範囲を編集します。

![次の節で説明するフィールドとオプションを表示する注釈の詳細ウィンドウ。](assets/edit-date-range.png)


1. 日付範囲の **[!UICONTROL タイトル]** を指定します。 例えば、**[!UICONTROL 四半期]** のように指定します。
1. オプションで、「**[!UICONTROL 説明]**」を指定します。
1. 1 つ以上の **[!UICONTROL タグ]** を作成または適用して、フィルターを整理します。 入力を開始して、選択可能な既存のタグを検索します。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。 ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、タグを削除します。 |
1. 最初に開始日を選択し、次に終了日を選択して、「**[!UICONTROL 日付範囲]**」を選択します。
または、**[!UICONTROL プリセットを選択]**&#x200B;ドロップダウンメニューから「[!UICONTROL *プリセット*]」を選択できます。

1. オプションで、「**[!UICONTROL 詳細設定を表示]**」を選択して、次の操作を行います。

   * デフォルトの `12:00 AM`（`0:00`）と `11:59 PM`（`23:59`）以外の&#x200B;**[!UICONTROL 開始時間]**&#x200B;と&#x200B;**[!UICONTROL 終了時間]**&#x200B;を指定します。終了時間には常に 59 秒が含まれます。日付範囲が何日にもわたる場合、開始時間は日付範囲の最初の日、終了時間は日付範囲の最終日に適用されます。**[!UICONTROL 日時の値をリセット]**&#x200B;を使用して、開始時間と終了時間をデフォルトにリセットします。
   * **[!UICONTROL 相対日付の使用]**&#x200B;有効にした場合、現在の日付と時間の進行状況に応じて、プリセットされた日付範囲 **[!UICONTROL 過去 7 日間]** が動的に更新されます。 無効にすると、そのようなプリセットは適用されると更新されません。

     角括弧で囲まれたテキスト（例：**[!UICONTROL 固定開始 – 四半期ごとのローリング]**）を選択して、パネルを拡張し、**[!UICONTROL 開始]** と **[!UICONTROL 終了]** の詳細を指定できます。

     ![Rollinf の日付 ](assets/rolliing-dates.png)

      1. 「**[!UICONTROL 開始日]**」、「**[!UICONTROL 終了日]**」または「**[!UICONTROL 固定日]**」を選択します。
      1. 「**[!UICONTROL 開始日]**」または「**[!UICONTROL 終了日]**」を選択すると、完全な式を作成できます。例：**[!UICONTROL 終了日]****[!UICONTROL 今四半期]****[!UICONTROL マイナス]**`20`**[!UICONTROL 日]** 式の個々の部分に適した値を選択します。
         * 現在の値を選択します。例えば、**[!UICONTROL 今四半期]** です。
         * 追加の計算の値を選択します。例えば、**[!UICONTROL minus]** と指定します。
         * 追加の計算を指定した場合は、値を指定します。 例：`20`。
         * 追加の計算を指定した場合は、計算に使用する期間を選択します。 例えば、**[!UICONTROL days]** と指定します。

     周期的な日付の計算の詳細を非表示にするには、「**[!UICONTROL 詳細を非表示]**」を選択します。

1. を選択：
   * **[!UICONTROL 保存]**：日付範囲を保存します。
   * **[!UICONTROL 名前を付けて保存]**：日付範囲のコピーを保存します。
   * **[!UICONTROL キャンセル]**：日付範囲に対して行った変更をキャンセルしたり、新しい日付範囲の作成をキャンセルしたりします。


<!--


You can create a date range using either of the following two methods:

* Directly in a workspace project by clicking the '`+`' button next to the list of date range components on the left
* Within the date range manager

To create a date range in the date range manager:

1. Log in to [analytics.adobe.com](https://analytics.adobe.com) using your AdobeID credentials.
1. Navigate to [!UICONTROL Components] > [!UICONTROL Date Ranges].
1. Click the [!UICONTROL Add] button to open the modal window that creates a date range.

## Create a date range modal window

The modal window has four fields you can edit:

* **Date range**: The date range you want for this component.
* **Title**: The name you want for this component. The title is used in workspace projects.
* **Description**: The description you want for this component. The description is seen when clicking the ![i](../assets/i.png) icon.
* **Tags**: Use tags to organize your date ranges. A date range can belong to multiple tags.

## Selecting a date range

When clicking the date range in the modal window, you have several options:

* **Calendar**: Select the start and end date.
* **Use rolling dates**: Check this box if you want the date range to change as time goes on. Do not check this box if you want your date range to remain static.
* **Select preset**: Use this drop-down selection if you want a custom date range based on a range that Adobe offers by default. When you select a preset, you can further customize the date range to suit your needs. It does not affect the preset that Adobe offers.

## Rolling date ranges

If you want a rolling date range, you can customize when it rolls. You can control when the start and end dates roll independently of each other.

* **When the date starts**: Choose if the date starts at the beginning of a time period, at the end of a time period, or use a fixed day.
* **The time period to use**: Choose how often the date range rolls. You can have it roll every day, every week, every month, every quarter, or every year.
* **Offset**: Choose the offset of the date range. You can add or subtract days, weeks, months, quarters, or years.

## Rolling date examples

Some date ranges can be useful in certain reports.

Year-to-date:

```text
Start: Start of current year
End: End of current day
```

Last Thursday to this Thursday:

```text
Start: Start of current week minus 3 days
End: Start of current week plus 4 days
```

Fiscal year (for example, if a fiscal year starts in December)

```text
Start: Start of current year minus 1 month
End: End of current year minus 1 month
```


-->