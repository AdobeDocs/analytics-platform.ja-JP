---
title: 形式コンポーネントの設定
description: 指標の形式を設定します。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 6fdb6cbd6f12a0417f513565b02e3ad60c8df6cb
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 88%

---

# 形式コンポーネントの設定 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="形式"
>abstract="レポートで使用される際のコンポーネントの表示方法を決定します。"

<!-- markdownlint-enable MD034 -->


形式を使用すると、特定のコンポーネントがレポートで使用される際の表示方法を決定できます。

## コンポーネントの形式設定の指定

形式設定を調整することで、特定のコンポーネントの表示方法を決定できます。

1. Customer Journey Analytics で、「[!UICONTROL **データビュー**]」タブを選択します。

1. 形式設定を設定するコンポーネントを含むデータビューを選択します。

1. 「[!UICONTROL **コンポーネント**]」タブを選択します。

1. 設定するコンポーネントを選択し、ページの右側にある「[!UICONTROL **形式**]」セクションを展開します。

   ![形式設定](../assets/format-settings.png)

1. 次の情報を指定します。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL 形式]** | コンポーネントの書式を、10 進数、時間、パーセント、通貨の形式で指定できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 整数スキーマのデータタイプには表示されません。コンポーネントに表示する小数点以下の桁数を指定できます。 |
   | **[!UICONTROL 日付]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日時]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 通貨]** | コンポーネントを表示する通貨を決定できます。 <p>様々な通貨で取引が発生するグローバルデータを分析する場合は、[通貨換算の使用](#use-currency-conversion)を参照してください。</p> |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | このコンポーネントの上昇傾向を良い（緑）と見なすか、悪い（赤）と見なすかを指定できます。 |
   | **[!UICONTROL True 値]** と **[!UICONTROL False 値]** | ブールスキーマのデータタイプでのみ表示されます。`true` 値と `false` 値のディメンション項目ラベルをカスタマイズできます。 |

   {style="table-layout:auto"}

## 通貨換算を使用 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="通貨換算"
>abstract="通貨コードのディメンションを選択して、選択した通貨タイプで通貨を設定および表示します。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analytics での通貨換算は、国際的に運営するビジネスにとって非常に価値があります。手動での通貨換算の複雑さを排除することで、Customer Journey Analytics での通貨換算により財務データの統一性と明確性がもたらされます。通貨換算では、毎日の履歴為替レートが追跡され、その毎日のレートが 4 年間維持されます。

例えば、e コマースビジネスが米国、英国、EU で運営されている場合、売上データは自動的に米ドルに変換されるので、簡単に比較し、パフォーマンスを総合的に把握できます。

>[!NOTE]
>
>通貨換算の指標の設定を開始する前に、次の点を考慮します。
>
>* 通貨換算に選択する指標は、数値タイプ（倍精度浮動小数点数、長整数、整数、短整数、バイト）である必要があります。
>* 通貨指標を含むすべてのイベントに対して通貨コードディメンションを保持するイベントデータセットを 1 つ以上含めるには、Customer Journey Analytics 接続を設定します。この通貨コードディメンションでは、通貨を表すために [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 標準に準拠したアルファベットの通貨コードが使用されます。これらの値は、$ の場合は USD、€ の場合は EUR、£ の場合は GBP のように、すべて大文字の形式で指定する必要があります。

特定の指標に対して表示および変換する通貨を決定するには：

1. 上記の[指標の形式設定の指定](#configure-format-settings-for-a-metric)の説明に従って、通貨を形式として使用する指標の設定を開始します。

1. 指標を選択した状態で、ページの右側にある「[!UICONTROL **形式**]」セクションで次の選択を行います。

   * 「[!UICONTROL **形式**]」フィールドで、[!UICONTROL **通貨**]&#x200B;を選択します。

   * 「[!UICONTROL **小数点以下の桁数**]」フィールドで、指標に表示される小数点以下の桁数を選択します。

     このオプションは、指標の数値タイプが「倍精度浮動小数点数」の場合にのみ使用できます。

   * 「[!UICONTROL **通貨を換算**]」オプションを選択します。

   * 「[!UICONTROL **通貨コードのディメンションを選択**]」フィールドで、換算元の通貨（データの基になる通貨）を表すディメンションを選択します。例えば、[!UICONTROL **通貨コード**]&#x200B;というディメンションを選択します。

     現在のデータスキーマに通貨コードフィールドを含むディメンションがない場合は、[データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)、[Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html?lang=ja) または[派生フィールド](/help/data-views/derived-fields/derived-fields.md)を使用して新しい通貨コードフィールドを作成できます。データ準備は、今後に向けてのみ行われるので、新しい実装にのみ適しています。組織の設定に応じて、Data Distiller と派生フィールドを使用して、履歴に基づく通貨コード値にアクセスできます。

   * 「[!UICONTROL **通貨を換算および表示**]」フィールドで、データを換算する通貨を選択します。

1. 追加の指標に通貨換算を適用する場合は、これらの手順を繰り返します。



### よくある質問

+++ 通貨換算はどのように実行されますか？

レポート時に、指標の値と元の通貨コードは USD に変換され、その後、表示用に設定された通貨に変換されます。この変換には、イベントの期間に適用される毎日の通貨為替レートが使用されます。

+++

