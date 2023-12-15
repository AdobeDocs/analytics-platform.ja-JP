---
title: 形式コンポーネントの設定
description: 指標の形式を設定します。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: cf9e8c90eec78658e470d3a7a56cb2e3414591d4
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 20%

---

# 形式コンポーネントの設定

形式を使用すると、特定の指標をレポートで使用する際の表示方法を指定できます。

## 指標の形式設定を行う

形式設定を調整することで、特定の指標の表示方法を決定できます。

1. Customer Journey Analyticsで、 [!UICONTROL **データビュー**] タブをクリックします。

1. 形式設定を設定するコンポーネントを含むデータビューを選択します。

1. 「[!UICONTROL **コンポーネント**]」タブを選択します。

1. 設定するコンポーネントを選択し、「 [!UICONTROL **形式**] 」セクションをクリックします。

   ![形式設定](../assets/format-settings.png)

1. 次の情報を指定します。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL 形式]** | 指標の書式を、10 進数、時間、パーセント、通貨の形式で指定できます。 |
   | **[!UICONTROL 小数点以下の桁数]** | 整数スキーマのデータタイプには表示されません。指標で表示する小数点以下の桁数を指定できます。 |
   | **[!UICONTROL 日付]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 日時]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
   | **[!UICONTROL 通貨]** | 指標を表示する通貨を決定できます。 <p>異なる通貨で取引が発生するグローバル・データを分析する場合は、  [通貨換算の使用](#use-currency-conversion).</p> |
   | **[!UICONTROL 上昇傾向を次の形式で表示]** | この指標の上昇傾向を良い（緑）と見なすか、悪い（赤）と見なすかを指定できます。 |
   | **[!UICONTROL True 値]** と **[!UICONTROL False 値]** | ブールスキーマのデータタイプでのみ表示されます。`true` 値と `false` 値のディメンション項目ラベルをカスタマイズできます。 |

   {style="table-layout:auto"}

## 通貨換算の使用

Customer Journey Analyticsでの通貨換算は、国際的に事業を展開する企業にとって非常に重要です。 手動での通貨換算の複雑さを取り除くことで、Customer Journey Analyticsでの通貨換算は、財務データの統一性と明確性をもたらします。 通貨換算では、日次の過去の為替レートを追跡し、4 年間その日次レートを維持します。

例えば、米国、英国、EU で e コマースビジネスを展開している場合、販売データを自動的に米ドルに変換して、パフォーマンスの比較と全体的な理解を容易にします。

>[!NOTE]
>
>通貨換算の指標を設定する前に、次の点に注意してください。
>
>* 通貨換算に選択する指標のタイプは、数値（倍精度、長さ、整数、短さ、バイト）である必要があります。
>* 通貨Customer Journey Analyticsを含む各イベントの通貨コードディメンションを保持する 1 つ以上のイベントデータセットを含むように通貨接続を設定します。 その通貨コードディメンションは、 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 通貨を表すための標準。 これらの値は、完全に大文字の形式にする必要があります。例えば、$の場合は USD、€の場合は EUR、£の場合は GBP です。

特定の指標に対する通貨の表示および換算方法を指定するには、次の手順に従います。

1. 通貨を形式として使用する指標の設定を開始します（前述のように）。 [指標の形式設定を行う](#configure-format-settings-for-a-metric).

1. 指標を選択した状態で、 [!UICONTROL **形式**] セクションの右側に表示されます。

   * Adobe Analytics の [!UICONTROL **形式**] フィールド、選択 [!UICONTROL **通貨**].

   * Adobe Analytics の [!UICONTROL **小数点以下の桁数**] 「 」フィールドで、指標に表示する小数点以下の桁数を選択します。

     このオプションは、指標の数値タイプが「倍精度」の場合にのみ使用できます。

   * を選択します。 [!UICONTROL **変換通貨**] オプション。

   * Adobe Analytics の [!UICONTROL **通貨コードディメンションを選択**] 「 」フィールドで、変換元の通貨（データの基になる通貨）を表すディメンションを選択します。 例えば、次の名前のディメンションを選択します。 [!UICONTROL **通貨コード**].

     現在のデータスキーマに通貨コードフィールドを含むディメンションがない場合、 [データ準備](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=ja), [Data Distiller](https://experienceleague.adobe.com/docs/experience-platform/query/data-distiller/overview.html)または [派生フィールド](/help/data-views/derived-fields/derived-fields.md). Data Prep は将来的なものに過ぎないので、新しい実装にのみ適しています。 組織の設定に応じて、従来、Data Distillerと派生フィールドを使用して通貨コード値にアクセスできます。

   * Adobe Analytics の [!UICONTROL **通貨の変換と表示**] 「 」フィールドで、データを変換する通貨を選択します。

1. 追加の指標に通貨換算を適用する場合は、これらの手順を繰り返します。



### よくある質問

+++ 通貨換算はどのように実行されますか？

レポート時に、指標の値と元の通貨コードの値が USD に変換され、表示用に設定された通貨に変換されます。 このコンバージョンでは、イベントの時間に適用できる、日別の為替レートが使用されます。

+++

