---
title: 形式コンポーネントの設定
description: 指標の形式を設定します。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: e4e0c3cf2e865454837df6626c3b1b09f119f07f
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 23%

---

# 形式コンポーネントの設定 {#format-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format"
>title="形式"
>abstract="レポートで使用される際のコンポーネントの表示方法を決定します。"

<!-- markdownlint-enable MD034 -->


形式を使用すると、レポートで使用される際の特定の指標の表示方法を決定できます。

## 指標の形式設定の指定

形式設定を調整することで、特定の指標の表示方法を決定できます。

1. Customer Journey Analyticsで、「[!UICONTROL **データビュー**]」タブを選択します。

1. 形式設定を設定するコンポーネントを含むデータビューを選択します。

1. 「[!UICONTROL **コンポーネント**]」タブを選択します。

1. 設定するコンポーネントを選択し、ページの右側にある「[!UICONTROL **形式**]」セクションを展開します。

   ![形式設定](../assets/format-settings.png)

1. 次の情報を指定します。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL 形式]** | 指標の書式を、10 進数、時間、パーセント、通貨の形式で指定できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 整数スキーマのデータタイプには表示されません。指標で表示する小数点以下の桁数を指定できます。 |
   | **[!UICONTROL 日付]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日時]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 通貨]** | 指標の表示に使用する通貨を決定できます。 <p>様々な通貨で取引が発生するグローバル・データを分析する場合は、[ 通貨換算の使用 ](#use-currency-conversion) を参照してください。</p> |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | この指標の上昇傾向を良い（緑）と見なすか、悪い（赤）と見なすかを指定できます。 |
   | **[!UICONTROL True 値]** と **[!UICONTROL False 値]** | ブールスキーマのデータタイプでのみ表示されます。`true` 値と `false` 値のディメンション項目ラベルをカスタマイズできます。 |

   {style="table-layout:auto"}

## 通貨換算を使用 {#use-currency-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_format_currencyconversion"
>title="通貨換算"
>abstract="通貨コードのディメンションを選択して、選択した通貨タイプで通貨を設定および表示します。"

<!-- markdownlint-enable MD034 -->

Customer Journey Analyticsの為替コンバージョンは、国際的に事業を展開する企業にとって非常に価値があります。 Customer Journey Analyticsの為替コンバージョンは、手動での為替コンバージョンの複雑さを取り除くことで、財務データの均一性と明確性をもたらします。 通貨コンバージョンでは、毎日の履歴為替レートを追跡し、それらの毎日のレートを 4 年間維持します。

例えば、e コマース事業が米国、英国、EU で展開されている場合、売上データを自動的に米ドルに変換できるため、パフォーマンスの比較や全体像の把握が容易になります。

>[!NOTE]
>
>通貨換算の指標の設定を開始する前に、次の点を考慮してください。
>
>* 通貨換算のために選択する指標は、数値タイプ（倍精度浮動小数点数、長整数、短整数、バイト）である必要があります。
>* 通貨指標を含むすべてのイベントに対して通貨コードディメンションを保持するイベントデータセットを少なくとも 1 つ含むように、Customer Journey Analytics接続を設定します。 その通貨コード次元では、通貨を表すために、[ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 規格に準拠したアルファベットの通貨コードを使用します。 これらの値は完全な大文字で指定する必要があります。例えば、$は USD、€は EUR、£は GBP です。

特定の指標に対して通貨を表示して換算する方法を決定するには、次の手順に従います。

1. 前述のように、[ 指標の形式設定の指定 ](#configure-format-settings-for-a-metric) で、通貨を形式として使用する指標の設定を開始します。

1. 指標を選択した状態で、ページの右側にある [!UICONTROL **形式**] セクションで次の選択を行います。

   * 「[!UICONTROL **フォーマット**]」フィールドで「[!UICONTROL **通貨**]」を選択します。

   * [!UICONTROL **小数点以下の桁数**] フィールドで、指標に表示する小数点以下の桁数を選択します。

     このオプションは、指標の数値タイプが「Double」の場合にのみ使用できます。

   * 「[!UICONTROL **通貨を換算**]」オプションを選択します。

   * 「[!UICONTROL **通貨コード次元の選択**]」フィールドで、変換元の通貨（データの基となる通貨）を表す次元を選択します。 例えば、「通貨コード [!UICONTROL **というディメンションを選択し**] す。

     現在のデータスキーマに通貨コードフィールドを含むディメンションがない場合は、[ データ準備 ](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja)、[ データDistiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html) または [ 派生フィールド ](/help/data-views/derived-fields/derived-fields.md) を使用して新しい通貨コードフィールドを作成できます。 データ準備は将来的にのみ行われるので、新しい実装にのみ適しています。 組織の設定に応じて、データDistillerおよび派生フィールドを使用して、履歴に基づく通貨コード値にアクセスできます。

   * [!UICONTROL **通貨を換算および表示**] フィールドで、データを換算する通貨を選択します。

1. 追加の指標に通貨換算を適用する場合は、これらの手順を繰り返します。



### よくある質問

+++ 通貨換算はどのように実行されますか？

レポート時に、指標の値と元の通貨コードは USD に変換され、表示用に設定された通貨に変換されます。 この変換では、イベントの期間に適用される毎日の通貨為替レートを使用します。

+++

