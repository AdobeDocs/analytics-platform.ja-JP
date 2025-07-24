---
title: 派生フィールド
description: 派生フィールドは、一連の使用可能な関数および関数テンプレートを使用して、スキーマフィールドや標準コンポーネントのレポート時の操作を指定します。
solution: Customer Journey Analytics
feature: Derived Fields
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 1b81b0fb81119132b6568726761e9897c2b4e47c
workflow-type: tm+mt
source-wordcount: '1178'
ht-degree: 29%

---


# 派生フィールド（限定的なテスト）{#derived-fields}

{{release-limited-testing}}

>[!IMPORTANT]
>
>このドキュメントは、まだ一般公開されていない新しい派生フィールド関数に関する暫定的なドキュメントです。 新しい派生フィールド関数については、この情報を参照してください。 このドキュメントは変更される可能性があり、この記事の現在のバージョンから引き出される法的義務はありません。
>><br/>派生フィールドの一般的な機能と、現在リリースされている関数および関数テンプレートについて詳しくは、[ 派生フィールド ](derived-fields.md) を参照してください。
>

## 関数リファレンス

{{select-package}}

サポートされている各関数について、次の点で詳細を確認してください。

- 仕様：
   - 入力データタイプ：サポートされるデータのタイプ、
   - 入力：入力に使用可能な値、
   - 含まれる演算子：この関数でサポートされる演算子（ある場合）、
   - 制限事項：この特定の関数に適用される制限事項、
   - 出力。

- 次のようなユースケース：
   - （オプション）派生フィールドを定義する前のデータ。
   - 派生フィールドの定義方法、
   - （任意）派生フィールドを定義した後のデータ。

- 制約（該当する場合）。



<!-- DATE MATH -->

### 日付計算 {#datemath}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_datemath"
>title="日付計算"
>abstract="この関数には、2 つの日付フィールドまたは日時フィールドの違いを返す機能があります。"

2 つの日付または 2 つの日時フィールドの差を返します。

+++ 詳細

## 仕様 {#datemath-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| <ul><li>日付</li><li>Date-time</li></ul> | <ul><li>[!UICONTROL 範囲]<ul><li>イベント</li><li>セッション</li><li>ユーザー</li></ul></li><li>[!UICONTROL 値]：<ul><li>日付</li><li>Date-Time</li><li>静的な日付（ユーザーが入力）</li><li>静的な日時（ユーザーが入力）</li><li>動的日付<ul><li>Today</li></ul></li><li>ダイナミック日時<ul><li>Now</li></ul></li></ul></li><li>[!UICONTROL  精度 ]:<ul><li>Seconds</li><li>Minutes</li><li>時間</li><li>Days</li><li>Weeks</li><li>Months</li><li>四半期</li><li>年</li></ul></li><li>日付または日時の戻り値ごとに、次の操作を行います。<ul><li>最初（セッションまたはユーザー内）</li><li>最終（セッションまたはユーザー内）</li></ul></li></ul> | <p>該当なし</p> | <p>派生フィールドごとに 2 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース 1 {#datemath-uc1}

ホテル会社のマーケティングアナリストとして、顧客のチェックイン日と先週の予約日の日数の違いを理解したいと考えています。


### 派生フィールド {#datemath-uc1-derivedfield}

`Days between booking and check-in` の派生フィールドを定義します。[!UICONTROL DATE MATH] 関数を使用して、[!UICONTROL Booking Date] と [!DNL Person]Check-in Date[!UICONTROL  の間にある ] 範囲  の日数を計算するルールを定義します。 [!UICONTROL  日 ] を [!UICONTROL  出力精度 ] として選択します。 また、[!UICONTROL  予約日 ] と  チェックイン日 [!UICONTROL  の両方で「最終結果を返す ] を選択して、最後のユーザースコープ値が計算で使用されるようにします。

![ 日付計算ルールのスクリーンショット ](assets/datemath-1.png)


## ユースケース 2 {#datemath-uc2}

実店舗のマーケティングアナリストとして、顧客が店舗に最後に訪問したのは何日前かを把握する必要があります。 モバイルアプリとショップのビーコンでジオロケーション機能を使用して、顧客の物理的な訪問をキャプチャします。

### 派生フィールド {#datemath-uc2-derivedfield}

新しい `Days Since Visit To Shop` の派生フィールドを定義します。[!UICONTROL DATE MATH] 関数を使用すると、[!UICONTROL Date] で指定したカスタム日時と（イベントデータセットの [!UICONTROL placeContext] フィールドグループから [!UICONTROL  ローカル時間 ] の間の日数を、[!UICONTROL Person] の [!UICONTROL  重複排除範囲 ] で計算するルールを定義できます。 [!UICONTROL  最後を返す ] を選択して、[!UICONTROL  現地時間 ] の最後のユーザースコープ値が計算で使用されるようにします。 「日」を [!UICONTROL  出力の精度 ] として選択します。

![ 日付計算ルール 2 のスクリーンショット ](assets/datemath-2.png)


## ユースケース 3 {#datemath-uc3}

セッション内の顧客が注文を行うまでの検索時間（分単位）を把握する場合。

2 つの `Time Between Search And Order In Minutes`CASE WHEN[[!UICONTROL  関数の結果である新しい ] 派生フィールドを定義して ](#case-when)[!UICONTROL  検索時間 ] と [!UICONTROL  注文時間 ] の値を定義します。
次に、これら 2 つの値を使用して、[!UICONTROL  範囲 ] を [!UICONTROL  セッション ] に設定した [!UICONTROL DATE MATH] 関数、[!UICONTROL  検索時間 ] と [!UICONTROL  注文時間 ] に設定した値、および [!UICONTROL  出力精度 ] を [!UICONTROL  分 ] に設定した関数で差分を計算します。 両方の値について、「[!UICONTROL  最初のを返す ]」を選択して、最初の [!UICONTROL  検索時間 ] と [!UICONTROL  注文時間 ] が返されるようにします。

![ 日付計算ルール 3 のスクリーンショット ](assets/datemath-3.png)



<!--
| Visitor ID | Marketing Channel | Events |
|----|---|---:|
| ABC123 | paid search | 1 |
| DEF123 | email | 1 |
| JKL123 | natural search | 1 |

{style="table-layout:auto"}

-->

+++



<!-- DEPTH -->

### Depth {#depth}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_depth"
>title="Depth"
>abstract="この関数は、イベント深度の標準コンポーネントの機能と同様に、任意のフィールドの深度を返す機能を提供します。"

フィールドの深さを返します。これは、標準の [ イベントの深さディメンション ](/help/components/dimensions/overview.md#standard-dimensions) で可能なことと同様です。

+++ 詳細

## 仕様 {#depth-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 制限事項 | 出力 |
|---|---|---|---|---|
| いずれか | 任意のフィールド | 該当なし | 派生フィールドごとに 3 つの関数 | 新しい派生フィールド |

{style="table-layout:auto"}


<!--
## Example Data {#depth-example}

| event# | page name | search | product view | cart add  | order |
|:---:|---|:---:|:---:|:---:|:---:|
| 1 |  home page        |  0  | 0  | 0  | 0 |
| 2 |  search page      |  1  | 0  | 0  | 0 |
| 3 |  product page     |  0  | 0  | 0  | 0 |
| 4 |  cart page        |  0  | 0  | 1  | 0 |
| 5 |  confirmation     |  0  | 0  | 0  | 1 |

-->

## ユースケース {#depth-uc1}

検索深度（を検索回数と解釈することもできます）を把握したい場合。 そのため、後でその検索深度を使用して、特定の検索深度に関連付けられた検索語句を検索できます。


### 派生フィールド {#depth-uc1-derivedfield}

新しい `Search Depth` の派生フィールドを定義します。[!UICONTROL DEPTH] 関数を使用して、[!UICONTROL  検索 ] の深度を取得し、新しい派生フィールドに保存するルールを定義します。

![ 深度ルールのスクリーンショット ](assets/depth-1.png)

+++


<!-- TYPECASE -->

### Typecast {#typecast}

>[!CONTEXTUALHELP]
>id="dataview_derivedfields_typecast"
>title="Typecast"
>abstract="この関数は、フィールドタイプをその場で変更して、Customer Journey Analytics 内で追加の変換にフィールドを使用できるようにする機能を提供します。"

フィールドのフィールドタイプを変更して、Customer Journey Analytics内の追加の変換で使用できるようにします。

+++ 詳細

## 仕様 {#typecast-io}

| 入力データタイプ | 入力 | 含まれる演算子 | 上限 | 出力 |
|---|---|---|---|---|
| <ul><li>数値</li><li>日付</li><li>Date-time</li><li>文字列</li></ul> | <ul><li>[!UICONTROL フィールド] | <p><ul><li>整数<ul><li>文字列 <strong> に変換（必須） </strong></li></ul></li><li>Double<ul><li>文字列 <strong> に変換（必須） </strong><ul><li>継承する小数点以下の桁数を含める（最大 5 桁）</li></ul></li><li>整数 <strong> （Should）へ </strong></li></ul></li><li>Byte<ul><li>文字列 <strong> に変換（必須） </strong></li></ul></li><li>Long<ul><li>文字列 <strong> に変換（必須） </strong></li></ul></li><li>日付<ul><li>文字列 <strong> に変換（必須） </strong><ul><li>出力形式を定義する機能の提供</li></ul></li><li>例<ul><li>日付（2025 年 1 月 7 日の例）<ul><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、01-07-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM-DD-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、01-07-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、07-01-25</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">DD-MM-YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、07-01-2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、25-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY-MM-DD<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、2025-01-07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、2025/1/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MM/DD/YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、01/07/2025</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YYYY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、2025/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">YY/MM/DD<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、25/01/07</li></ul></li><li data-stringify-indent="1" data-stringify-border="0">MMM DD、YYYY<ul><li data-stringify-indent="2" data-stringify-border="0">例えば、2025年1月7日（PT）</li></ul></li></ul></li></ul></li></ul></li><li>Date-time<ul><li>文字列 <strong> に変換（必須） </strong><ul><li>出力形式を定義する機能の提供</li></ul></li><li>例<ul><li data-stringify-indent="0" data-stringify-border="0">日時（2025 年 1 月 7 日 1:30pm52 秒の例）<ul><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、01-07-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM-DD-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、01-07-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、07-01-25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">DD-MM-YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、07-01-2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、25-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY-MM-DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、2025-01-07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、01/07/25 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MM/DD/YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、01/07/2025 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YYYY/MM/DD hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、2025/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">YY/MM/DD hh:mm :ss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、25/01/07 13:30:52</li></ul></li><li data-stringify-indent="2" data-stringify-border="0">MMM DD、YYYY hhmmss<ul><li data-stringify-indent="3" data-stringify-border="0">例えば、2025 年 1 月 7 日 13:30:52</li></ul></li></ul></li></ul></li><li>文字列<ul><li><strong> を数値に変換 </strong><ul><li>本質的に数値でない値がある場合、null が返されます。</li><li>精度と使用するロケールを入力する必要があります。 </li></ul></li></ul></li></ul></li></ul></p> | <p>派生フィールドごとに 3 つの関数</p> | <p>新しい派生フィールド</p> |

{style="table-layout:auto"}


## ユースケース 1 {#typecast-uc1}

文字列ベースのディメンションとして使用する整数フィールド、画面の高さ（例：イベントデータセットの device.screenHeight）があります。


### 派生フィールド {#typecast-uc1-derivedfield}

`Screen Height` の派生フィールドを定義します。[!UICONTROL  画面の高さ ] フィールドに [!UICONTROL Typecast to] [!UICONTROL String] というルールを定義し、それを新しい派生フィールドに格納するには、[!UICONTROL TYPECAST] 関数を使用します。

![ タイプキャストルール 1 のスクリーンショット ](assets/typecast-1.png)



## ユースケース 2 {#typecast-uc2}

コホートテーブル（整数のみをサポート）で売上高を使用したいが、「売上高」フィールドには Double タイプがある。

![ タイプキャストルール 2 のスクリーンショット ](assets/typecast-2.png)


### 派生フィールド {#typecast-uc2-derivedfield}

`Revenue (integer)` の派生フィールドを定義します。[!UICONTROL Revenue] フィールドに [!UICONTROL Typecast to] [!UICONTROL Integer] というルールを定義し、それを新しい派生フィールドに保存するには、[!UICONTROL TYPECAST] 関数を使用します。


+++
