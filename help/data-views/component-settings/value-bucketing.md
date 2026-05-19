---
title: 値のバケット化コンポーネントの設定
description: あるディメンション内の数値を組み合わせます。
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
autotag-review: '2026-05-19T09:10:00.872Z'
TQID: 'https://experienceleague.adobe.com/LHEk3h9utGW73kSo2-SgY5NgKi11uktKR0ucPxw9IcY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 100%

---

# [!UICONTROL 値のバケット化] コンポーネントの設定 {#value-bucketing-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_value_bucketing"
>title="値のバケット化"
>abstract="バケットの値を特定の範囲に収めます。 これらの範囲は、レポートでディメンション項目として表示されます。"

<!-- markdownlint-enable MD034 -->


データビューを作成または編集する際に、値のバケット化を使用すると、範囲に基づいて数値を組み合わせることができます。 整数または倍精度スキーマのデータタイプを使用するディメンションに対してのみ使用できます。

![値のバケット化](../assets/value-bucketing.png)

値のバケット化は、すべての一意の数を個別のディメンション項目として扱うのではなく、範囲をグループ化する場合に役立ちます。 例えば、「5 ～ 10」のバケットは、Analysis Workspace では行項目「5 ～ 10」として表示されます。

グループディメンションと非グループディメンションの両方に関するレポートを柔軟に作成する場合は、コンポーネントの 2 つのコピーを使用可能なディメンションリストにドラッグします。 一方のディメンションでバケット化を有効にし、もう一方のディメンションでバケット化を無効にします。

| 設定 | 説明 |
| --- | --- |
| [!UICONTROL バケットの値] | バケット化を有効にするためのチェックボックス。 |
| [!UICONTROL より小さい] | 1 つ目のディメンションバケットの上限。 |
| [!UICONTROL 含む] [!UICONTROL およびより小さい] | 後続のバケットの境界。 |
| [!UICONTROL 以上] | 最後のディメンションバケットの下限。 |
| [!UICONTROL バケットを追加] | 数値ディメンションバケットに別のバケットを追加できます。 1 つのディメンションに最大 20 個のバケットを追加できます。 |

{style="table-layout:auto"}
