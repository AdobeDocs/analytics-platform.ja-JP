---
description: 主要指標の概要ビジュアライゼーションを使用すると、2 つのタイムラインにわたる指標のパフォーマンスを比較できます。
title: 主要指標の概要
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: 24c2ab4a49b87b11046317a40882dde72a2a49c1
workflow-type: tm+mt
source-wordcount: '642'
ht-degree: 85%

---

# 主要指標の概要

この[!UICONTROL 主要指標の概要]ビジュアライゼーションを使用すると、1 つの期間内で重要な指標のトレンドを確認できます。また、2 つの期間にわたる指標のパフォーマンスを比較することもできます。次のような複数のビジュアライゼーションが 1 つのビジュアライゼーションに統合されるメリットがあります。

* プライマリ日付範囲と比較日付範囲での指標のトレンドを表示する&#x200B;**[!UICONTROL 折れ線グラフ]**&#x200B;ビジュアライゼーション

* プライマリ日付範囲と比較日付範囲の間の指標の増減を示す&#x200B;**[!UICONTROL 変化率の概要]**

* 指標の現在の合計値（[!UICONTROL **数値概要**]）

## ユースケース

このビジュアライゼーションは、次のような様々な一般的なユースケースに対応しています。

* アナリストは前年の同じ期間と比較して今月の機会創出の様相を把握しようとしています。

* マーケターは特定のリードタイプのリードジェネレーションが今月から先月にかけてどのように変化したかを調べています。

* エグゼクティブは新規予約が今四半期から前四半期にどのように変化したかを理解したいと考えています。

## 主要指標の概要の設定

1. 左側のパネルの&#x200B;**[!UICONTROL ビジュアライゼーション]**&#x200B;メニューから&#x200B;**[!UICONTROL 主要指標の概要]**&#x200B;ビジュアライゼーションをパネルにドラッグします。

1. 指標、プライマリ日付範囲、比較日付範囲および（必要に応じて）フィルターを選択して、ビジュアライゼーションを設定します。

   ![ 指標、プライマリ日付範囲、比較日付範囲およびセグメントのオプションを示す主要指標の設定。](assets/key-metric-config.png)

   | 設定 | 定義 |
   | --- | --- |
   | **[!UICONTROL 指標]** | 調査の対象となる指標を選択します。すべての指標がサポートされています。 |
   | **[!UICONTROL プライマリ日付範囲]** | フリーフォームテーブルの現在の日付範囲。 |
   | **[!UICONTROL 比較日付範囲]** | プライマリ日付範囲の比較対象となる日付範囲。 |
   | **[!UICONTROL フィルター（オプション）]** | この概要で特に関心のあるフィルター。 |

   {style="table-layout:auto"}

1. 「**[!UICONTROL 作成]**」をクリックします。

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

## 出力の表示

![ 指標、変更概要、数値概要、折れ線グラフを示す主要指標の出力。](assets/key-metric-output.png)

注意：

* **[!UICONTROL 前の期間]**&#x200B;の折れ線グラフ（常にグレーで表示）は、設定手順の&#x200B;**[!UICONTROL 比較日付範囲]**&#x200B;に対応しています。

* 比較日付範囲が設定時に指定されていない場合やビジュアライゼーション設定で非表示になっている場合は、プライマリ日付範囲の折れ線グラフのみが表示されます。 変更の概要は非表示になります。

* ここから、折れ線グラフの上にマウスポインターを置くと、個々の日の統計情報を表示できます。

![ 訪問統計 ](assets/key-metric-output2.png)

## ビジュアライゼーション設定

主要指標の概要には柔軟な設定が複数用意されているので、重要な指標に関するレポートとコミュニケーションを改善できます。設定にアクセスするには、ビジュアライゼーションの右上隅にある歯車アイコンを使用します。

![ 概要表示タイプ、一般、表示オプションを示す主要指標の概要設定。](assets/key-metric-settings.png)

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 変化率を強調]** | ビジュアライゼーションの中央に目立つ太字で変更概要を表示します |
| **[!UICONTROL 数値を強調]** | ビジュアライゼーションの中央に目立つ太字で数値概要を表示します |
| **[!UICONTROL 凡例を表示]** | ビジュアライゼーションの下部に凡例を表示または非表示にします |
| **[!UICONTROL 注釈を表示]** | 管理者に追加された注釈を表示または非表示にします |
| **[!UICONTROL スパークラインを表示]** | グラフの下部に折れ線グラフを表示または非表示にします。 非表示にすると、凡例は、折れ線を視覚的に参照しなくなります |
| **[!UICONTROL スパークラインに最小値と最大値を表示]** | プライマリ折れ線グラフと比較折れ線グラフの最小値と最大値を表示または非表示 |
| **[!UICONTROL 比較を表示]** | 比較データを表示または非表示にします。 非表示の場合、比較折れ線グラフと変更概要オブジェクトの両方が非表示になります。 |
| **[!UICONTROL 合計数を表示]** | 数値概要を表示または非表示 |
| **[!UICONTROL 生の差異を表示]** | プライマリ日付範囲とセカンダリ日付範囲の指標の合計値の生の差異を表示または非表示 |
| **[!UICONTROL 値を短縮]** | 数値を短縮して、伝えるインサイト（20,000～20,000 など）を簡素化する |

## ビジュアライゼーションの編集

ビジュアライゼーションを作成した後でも、元の設定を編集できます。

1. ビジュアライゼーションの右上隅（設定の歯車アイコンの横）にある鉛筆アイコンをクリックします。

   ![ ビジュアライゼーション編集アイコン ](assets/edit-icon.png)

   元の設定ビューに戻ります。

1. 必要に応じて、指標、プライマリ日付範囲、比較日付範囲またはフィルターを変更します。
