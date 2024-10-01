---
title: 値を含む／除外コンポーネントの設定
description: ディメンション項目を、値に応じて条件付きで含めるか除外します。
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 94%

---

# 値を含む／除外コンポーネントの設定 {#include-exclude-values-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_includeexcludevalues"
>title="値を含める / 除外"
>abstract="特定の条件に合致する値のみをカウントするように指標をフィルタリングします。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_includeexcludevalues"
>title="値を含める / 除外"
>abstract="特定の条件に合致する値のみを含めるようにディメンションを絞り込みます。インクルージョンおよび除外は、配分およびレポートのフィルターの前に行われます。<br/><br/>**パラメーター&#x200B;**<br/>**大文字と小文字を区別**：以下のフィルターロジックで大文字と小文字を区別するかどうかを決定します。"

<!-- markdownlint-enable MD034 -->



「値を含む／除外」を使用すると、ディメンション項目の値に依存するルールを作成できます。設定した条件を満たさない値は、基になるデータセットにまだデータが存在しているにもかかわらず、存在していないものとして Analysis Workspace で処理されます。

![ 除外値を含めるをハイライト表示したデータ・ビュー・ウィンドウ ](../assets/include-exclude.png)

| 設定 | 説明／使用例 |
| --- | --- |
| [!UICONTROL 「値を含める / 除外」を設定] | データビューに含まれる値の条件を有効にするためのチェックボックス。 |
| [!UICONTROL 大文字と小文字を区別] | 文字列スキーマのデータタイプで表示されます。デフォルトではオンになっています。この設定は、結果の値ではなく、 [!UICONTROL 値を含む／除外] ロジックにのみ適用されます。 ルールで大文字と小文字を区別するかどうかを指定できます。 |
| [!UICONTROL 次に一致] | アトリビューションとフィルターの前にレポート対象として考慮する値を指定できます（例：「エラー」というフレーズを含む値のみを使用する）。 「**[!UICONTROL すべての条件が満たされた場合]**」または「**[!UICONTROL いずれかの条件が満たされた場合]**」を指定できます。 |
| [!UICONTROL 条件] | 特定のフィルタールールに適用する一致ロジックを指定できます。<ul><li>**文字列**：「フレーズを含む」、「任意の語句を含む」、「すべての語句を含む」、「いずれも語句を含まない」、「フレーズを含まない」「次と等しい」、「次と等しくない」、「次の語句で始まる」、「次の語句で終わる」</li><li>**重複 / 整数**：等しい、等しくない、次より大きい、次より小さい、次よりも大きいか等しい、次よりも小さいか等しい</li><li>**日付**：等しい、等しくない、より後、より前、次の範囲内で発生</li></ul> |
| [!UICONTROL 一致オペランド] | 一致演算子の適用対象となる一致オペランドを指定できます。<ul><li>**文字列**：テキストフィールド</li><li>**倍精度整数 / 整数**：上向き／下向き矢印付きの数値用テキストフィールド</li><li>**日付**：日の精度の選択（カレンダー）</li><li>**日時**：日付と時間の精度の選択</li></ul> |
| [!UICONTROL ルールを追加] | 追加の一致演算子およびオペランドを指定できます。 |

{style="table-layout:auto"}
