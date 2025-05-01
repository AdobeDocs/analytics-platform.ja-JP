---
title: 概要データグループコンポーネント設定
description: 概要データについて適切にレポートできるようにするためのデータセットからのディメンションの設定方法について説明します。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 89%

---

# [!UICONTROL 概要データグループ] コンポーネント設定 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup"
>title="概要データグループ"
>abstract="概要データグループは、グループ内のすべてのディメンション間の関連付けを作成します。これを使用すると、レポート用に概要データセットのディメンションを他のディメンションと組み合わせることができます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_summarydatagroup_hideinreporting"
>title="レポートで非表示"
>abstract="このオプションを選択すると、そのディメンションの&#x200B;**[!UICONTROL レポートでコンポーネントを非表示]**&#x200B;が有効になり、Analysis Workspace やその他の Customer Journey Analytics レポートツールにコンポーネントが表示されなくなります。"

<!-- markdownlint-enable MD034 -->



概要データグループは、グループ内のすべてのディメンション間の関連付けを作成します。これを使用すると、レポート用に概要データセットのディメンションを他のディメンションと組み合わせることができます。

![概要データグループコンポーネント設定](/help/data-views/assets/summary-data-group.png)

ディメンションのグループ化を作成には：

1. ディメンションを選択します。
1. ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL 概要データグループ]**&#x200B;を選択します。
1. **[!UICONTROL グループ化を作成]**&#x200B;を有効にします。
1. 最初の手順で選択したディメンションとグループ化するディメンションを ]**0}Dimension} ドロップダウンメニューから選択します。**[!UICONTROL &#x200B;データビューに既に追加したディメンションのみが、ドロップダウンメニューから使用できます。
1. オプションで、**[!UICONTROL レポートで非表示]**&#x200B;を有効にして、グループ化されたディメンションをレポートから非表示にします。このオプションを有効にすることは、グループ化されたディメンションで個別に&#x200B;**[!UICONTROL レポートで非表示]**&#x200B;を設定することと類似しています。詳しくは、[コンポーネント設定](overview.md)を参照してください。
1. オプションで、グループに追加のディメンションを追加するには、![追加](/help/assets/icons/Add.svg) **[!UICONTROL グループにディメンションを追加]**&#x200B;を選択します。<br/>概要データグループには 10 個のディメンションの制限があるので、最大 9 個のディメンションを追加できます。

## 同じコンポーネント設定

ディメンションをグループ化する際、グループに含まれる各ディメンションの[!UICONTROL 部分文字列]、[!UICONTROL 動作（小文字）]および[!UICONTROL 値を含む／除外]の設定が同じであることを確認する必要があります。そうしないと、グループ化の前に、グループの各ディメンションが異なる結果を返す場合があります。
例：

1. `campaign_code`（概要データの一部）と `tracking_code`（イベントデータの一部）の概要データグループを作成しました。
1. `campaign_code` には[!UICONTROL 動作（小文字）]を適用しましたが、`tracking_code` ディメンションには適用していません。

`tracking_code` の値は、`campaign_code` とは異なる値として表示される場合があります。

>[!IMPORTANT]
>
>ディメンションのグループ化は 1 つのディメンションからのみ実行し、複数のディメンションからのグループ化は適用しないでください。例えば、`campaign_name` ディメンションを `tracking_code` ディメンションに追加してグループ化を作成する場合は、`campaign_name` ディメンションのグループ化も作成しないでください。
>
