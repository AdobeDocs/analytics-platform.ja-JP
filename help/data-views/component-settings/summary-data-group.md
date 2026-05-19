---
title: 概要データグループコンポーネント設定
description: 概要データについて適切にレポートできるようにするためのデータセットからのディメンションの設定方法について説明します。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
autotag-review: '2026-05-19T09:00:37.763Z'
TQID: 'https://experienceleague.adobe.com/t1TH-tkHBNCfmC8hgk-IntYmYdRrS0enf2YEyRExCo4'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d00e9f03-e50b-4162-b143-0c0817c937c2id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 378
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
1. 最初の手順で選択したディメンションでグループ化するディメンションを&#x200B;**[!UICONTROL Dimension]** ドロップダウンメニューから選択します。 データビューに既に追加したディメンションのみが、ドロップダウンメニューから使用できます。
1. オプションで、**[!UICONTROL レポートで非表示]**&#x200B;を有効にして、グループ化されたディメンションをレポートから非表示にします。 このオプションを有効にすることは、グループ化されたディメンションで個別に&#x200B;**[!UICONTROL レポートで非表示]**&#x200B;を設定することと類似しています。 詳しくは、[コンポーネント設定](overview.md)を参照してください。
1. オプションで、グループに追加のディメンションを追加するには、![追加](/help/assets/icons/Add.svg) **[!UICONTROL グループにディメンションを追加]**&#x200B;を選択します。<br/>概要データグループには 10 個のディメンションの制限があるので、最大 9 個のディメンションを追加できます。

## 同じコンポーネント設定

ディメンションをグループ化する際、グループに含まれる各ディメンションの[!UICONTROL 部分文字列]、[!UICONTROL 動作（小文字）]および[!UICONTROL 値を含む／除外]の設定が同じであることを確認する必要があります。 そうしないと、グループ化の前に、グループの各ディメンションが異なる結果を返す場合があります。
次に例を示します。

1. `campaign_code`（概要データの一部）と `tracking_code`（イベントデータの一部）の概要データグループを作成しました。
1. `campaign_code` には[!UICONTROL 動作（小文字）]を適用しましたが、`tracking_code` ディメンションには適用していません。

`tracking_code` の値は、`campaign_code` とは異なる値として表示される場合があります。

>[!IMPORTANT]
>
>ディメンションのグループ化は 1 つのディメンションからのみ実行し、複数のディメンションからのグループ化は適用しないでください。 例えば、`campaign_name` ディメンションを `tracking_code` ディメンションに追加してグループ化を作成する場合は、`campaign_name` ディメンションのグループ化も作成しないでください。
>
