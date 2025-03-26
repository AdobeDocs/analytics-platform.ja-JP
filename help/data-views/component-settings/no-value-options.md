---
title: 値なしオプションコンポーネントの設定
description: ディメンションが空の場合の処理方法を決定します。
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 1a696662f10fddd42f3bbdbb79a6e735bf203bdf
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 53%

---

# 値なしオプションコンポーネントの設定 {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="値オプションなし"
>abstract="ディメンションに値がない場合のデフォルトの動作を設定します。"

<!-- markdownlint-enable MD034 -->


[!UICONTROL  値オプションなし ] を使用すると、データセット内のイベントに指標が含まれているが、ディメンションに値が含まれていない場合に、Analysis Workspaceがどのように処理するかを指定できます。 このディメンション項目の名前を選択したり、完全に非表示にしたり、実際の値として扱ったりできます。

![値オプションなし](../assets/no-value-options.png)

## 設定 {#settings}

| 設定 | 説明 |
| --- | --- |
| **[!UICONTROL 表示された場合は「値なし」を呼び出す]** | **[!UICONTROL 値なし]** ディメンション項目の名前を別の項目に変更できるテキストフィールド。 |
| **[!UICONTROL デフォルトで「値なし」を表示しない]** | レポートでこの値を表示しません。このディメンションに結び付けられていない指標の回数は、レポートに表示されません。 |
| **[!UICONTROL デフォルトで「値なし」を表示する]** | この値をレポートに表示します。 |
| **[!UICONTROL 「値なし」を値として扱う]** | （数値次元ではサポートされていません）データ内の空白の値を「表示された場合は「値なし」を呼び出す [!UICONTROL  で指定したテキストに置き換えます ]。 例えば、モバイルデバイスのタイプをディメンションとして指定した場合、「 **[!UICONTROL 値なし]** 」項目の名前を「デスクトップ」に変更できます。 このフィールドをカスタム値に変更すると、そのカスタム値は正当な文字列値として扱われます。したがって、このフィールドに「Red」と入力した場合、データそのものに「Red」という文字列が出現すると、指定した同じ行項目に分類されます。 |

## 数値ディメンションでの「値なし」のサポート {#numeric}

数値をディメンションとして使用する場合、次のことができます

* データビューで「値なし」オプションを設定します。 **[!UICONTROL 「値なし」を値として扱う」を除き、上記のすべての設定がサポートされていることに注意してください]**。
* Workspaceのフリーフォームテーブルの数値ディメンションには、**[!UICONTROL 「値を含めない」]** を使用します。
* フィルタービルダーで、数値ディメンションを持つ **[!UICONTROL exists]** または **[!UICONTROL does not exists]** 演算子を使用します。


>[!MORELIKETHIS]
>
>以下は、[Customer Journey Analyticsでの「値なし」の処理 ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/handling-quot-no-value-quot-in-customer-journey-analytics/ba-p/597339) に関する関連ブログ投稿です。

