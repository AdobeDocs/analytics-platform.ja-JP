---
title: 形式コンポーネントの設定
description: 指標の形式を設定します。
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: a3fea05ac95407c7f3bee723a267ae0bc03d334a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 32%

---

# 形式コンポーネントの設定

形式を使用すると、特定の指標の表示方法を指定できます。

![形式設定](../assets/format-settings.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 形式]** | 指標の書式を、10 進数、時間、パーセント、通貨の形式で指定できます。 |
| **[!UICONTROL 小数点以下の桁数]** | 整数スキーマのデータタイプには表示されません。指標で表示する小数点以下の桁数を指定できます。 |
| **[!UICONTROL 日付]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 日時]** | レポートでディメンションとして使用する際に、日時のフィールドをどのように表示するかを決定できます。[詳細情報](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL 通貨]** | 指標の表示に使用する通貨を決定できます。詳しくは、 [通貨](#currency) 詳細を表示します。 |
| **[!UICONTROL 上昇傾向を次の形式で表示]** | この指標の上昇傾向を良い（緑）と見なすか、悪い（赤）と見なすかを指定できます。 |
| **[!UICONTROL True 値]** と **[!UICONTROL False 値]** | ブールスキーマのデータタイプでのみ表示されます。`true` 値と `false` 値のディメンション項目ラベルをカスタマイズできます。 |

{style="table-layout:auto"}


## 通貨

次を選択した場合： **[!UICONTROL 通貨]** を [!UICONTROL 形式] 指標の場合、通貨の表示と換算の方法を決定できます。

### 通貨を表示

指標の通貨を表示するには：

1. 数を入力 **[!UICONTROL 小数点以下の桁数]**.

2. 通貨を **[!UICONTROL 通貨の表示単位]** リスト。


### 通貨の変換と表示

[!BADGE 新機能]{type=Positive}

{{release-limited-testing-section}}

指標の通貨の換算を有効にするには、次の手順に従います。

- 通貨指標を含む各イベントの通貨コードディメンションを保持する 1 つ以上のイベントデータセットを含むように CJA 接続を設定します。 その通貨コードディメンションは、 [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) 通貨を表すための標準。 例えば、$の場合は USD、€の場合は EUR、£の場合は GBP です。

- （オプションで） [!UICONTROL 通貨コード] データセットで使用できる通貨コードを定義する 1 つ以上のディメンションのコンテキストラベル。

  次の手順で [!UICONTROL 通貨コード] コンテキストラベル、内 [!UICONTROL コンポーネント] タブに表示されます。

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. 通貨コードを保持するデータセットの 1 つからディメンションを選択します。 例： [!UICONTROL 通貨コード].

   2. 選択 **[!UICONTROL 通貨コード]** から [!UICONTROL コンテキストラベル] リスト。

  通貨換算に使用する通貨コードを保持するディメンションが他にある場合は、これらの手順を繰り返します。

>[!NOTE]
>
>通貨換算に選択する指標のタイプは、数値（倍精度、長さ、整数、短さ、バイト）である必要があります。


指標の通貨の変換および表示方法を定義するには：

1. 数を入力 **[!UICONTROL 小数点以下の桁数]**.

2. 選択 **[!UICONTROL 同時実行の変換]**.

3. 適用されたコンテキストラベルに基づいて、 **[!UICONTROL 通貨コードディメンション]** リストが自動的に選択されます。 通貨コードのコンテキストラベルを追加で適用したディメンションを含む、他のディメンションも選択できます。

4. 通貨を **[!UICONTROL 通貨の変換と表示]** リスト。

### よくある質問

+++ 通貨換算はどのように実行されますか？

レポート時に、指標の値と元の通貨コードの値が USD に変換され、表示用に設定された通貨に変換されます。 このコンバージョンでは、イベントの時間に適用できる、日別の為替レートが使用されます。

+++

