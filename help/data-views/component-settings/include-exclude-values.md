---
title: 値を含む／除外コンポーネントの設定
description: ディメンション項目を、値に応じて条件付きで含めるか除外します。
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 100%

---

# 値を含む／除外コンポーネントの設定 {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_includeexcludevalues"
>title="値を含む／除外"
>abstract="特定の条件に合致する値のみをカウントするように指標をフィルタリングします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_includeexcludevalues"
>title="値を含む／除外"
>abstract="特定の条件に合致する値のみを含めるようにディメンションを絞り込みます。含めるおよび除外は、レポートの配分およびフィルターの前に行われます。指定したフィルターロジックで大文字と小文字を区別するかどうかを決定します。"

<!-- markdownlint-enable MD034 -->

「値を含む／除外」を使用すると、ディメンション項目の値に依存するルールを作成できます。設定した条件を満たさない値は、基になるデータセットにまだデータが存在しているにもかかわらず、存在していないものとして Analysis Workspace で処理されます。

![値を含む／除外をハイライト表示するデータビューウィンドウ](../assets/include-exclude.png)

| 設定 | 説明／使用例 |
| --- | --- |
| [!UICONTROL 「値を含める / 除外」を設定] | データビューに含まれる値の条件を有効にするためのチェックボックス。 |
| [!UICONTROL 大文字と小文字を区別] | 文字列スキーマのデータタイプで表示されます。デフォルトではオンになっています。この設定は、結果の値ではなく、 [!UICONTROL 値を含む／除外] ロジックにのみ適用されます。 ルールで大文字と小文字を区別するかどうかを指定できます。 |
| [!UICONTROL 次に一致] | アトリビューションとフィルターの前にレポート対象として考慮する値を指定できます（例：「エラー」というフレーズを含む値のみを使用する）。 **[!UICONTROL すべての条件を満たしている場合]**&#x200B;または&#x200B;**[!UICONTROL いずれかの条件を満たしている場合]**&#x200B;を指定できます。それぞれの値をスペースで区切ります。 |
| [!UICONTROL 条件] | 特定のフィルタールールに適用する一致ロジックを指定できます。<ul><li>**文字列**：[!UICONTROL フレーズを含む]、[!UICONTROL いずれかの語句を含む]、[!UICONTROL すべての語句を含む]、[!UICONTROL いずれの語句も含まない]、[!UICONTROL フレーズを含まない]、[!UICONTROL 次と等しい]、[!UICONTROL 次と等しくない]、[!UICONTROL 次で始まる]、[!UICONTROL 次で終わる]</li><li>**倍精度整数／整数**：[!UICONTROL 次と等しい]、[!UICONTROL 次と等しくない]、[!UICONTROL 次よりも大きい]、[!UICONTROL 次よりも小さい]、[!UICONTROL 次よりも大きいか等しい]、[!UICONTROL 次よりも小さいか等しい]</li><li>**日付**：[!UICONTROL 次と等しい]、[!UICONTROL 次と等しくない]、[!UICONTROL 次より後]、[!UICONTROL 次より前]、[!UICONTROL 次の範囲で発生]</li></ul> |
| [!UICONTROL 一致オペランド] | 一致演算子の適用対象となる一致オペランドを指定できます。<ul><li>**文字列**：テキストフィールド</li><li>**倍精度整数 / 整数**：上向き／下向き矢印付きの数値用テキストフィールド</li><li>**日付**：日の精度の選択（カレンダー）</li><li>**日時**：日付と時間の精度の選択</li></ul> |
| [!UICONTROL ルールを追加] | 追加の一致演算子およびオペランドを指定できます。 |

{style="table-layout:auto"}
