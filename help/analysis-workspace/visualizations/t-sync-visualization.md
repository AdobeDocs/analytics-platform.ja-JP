---
description: ビジュアライゼーションをフリーフォームテーブルデータソースにリンクする方法を説明します。
keywords: Analysis Workspace;ビジュアライゼーションとデータソースの同期
title: Analysis Workspaceでのビジュアライゼーションデータソースの管理
feature: Visualizations
exl-id: f9e89bef-0e78-49c7-8b7b-1fefd709c0cd
role: User
autotag-review: '2026-05-19T08:30:43.942Z'
TQID: 'https://experienceleague.adobe.com/UU1RlISeu-NOFAttolNcjV-p2EgtxBPFy3w7ZrLz-vY'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
  - id: bee1d787-7e5f-52f2-a27b-db3204cbc423
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
source-git-commit: f7d853a3b658328f952b675f838ce314b7c30fb1
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# データソースの管理 {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="選択をロック"
>abstract="この設定を有効にすると、ビジュアライゼーションがデータソースで選択した位置または選択した項目にロックされます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="テーブルの表示"
>abstract="**[!UICONTROL テーブルを表示]**&#x200B;を選択すると、元のデータソースとは別に、現在のビジュアライゼーション用に新しいデータソースが生成されます。"

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="テーブルの表示"
>abstract="「**[!UICONTROL テーブルを表示]**」を選択して、元のデータソースとは別に、現在のビジュアライゼーション用の新しいデータソースを生成します。"

Analysis Workspaceの各ビジュアライゼーションは、データソース（通常はフリーフォームテーブル）に基づいています。 ビジュアライゼーションを同期すると、どのフリーフォームテーブルまたはデータソースがビジュアライゼーションに対応するか、ビジュアライゼーションがそのテーブル内の特定の行にロックされたままであるかどうかを制御できます。

>[!TIP]
>
>ビジュアライゼーションのタイトルの横の ![StatusOrange](/help/assets/icons/StatusOrange.svg) の色で、どのビジュアライゼーションが関連しているかがわかります。 色が一致していると、ビジュアライゼーションが同じデータソースに基づいていることを意味します。
>

## データソースの設定 {#configure}

1. Analysis Workspaceで、設定するデータソースまたはロック設定のビジュアライゼーションに移動します。

1. ビジュアライゼーションにカーソルを合わせ、**[!UICONTROL 設定]** アイコン ![設定](/help/assets/icons/Setting.svg)を選択します。

1. 「**[!UICONTROL データソース]**」タブを選択します。

   ![&#x200B; データソース、リンクされたビジュアライゼーション、およびロック選択設定を示す「データソース」タブ。](assets/lock-selection.png)

1. 次のいずれかの設定を行います。

   | 設定 | 説明 |
   | --- | --- |
   | **[!UICONTROL データソース]** | ビジュアライゼーションの基となるデータソースを選択します。 |
   | **[!UICONTROL リンクされたビジュアライゼーション]** | データソース（フリーフォームテーブル）にリンクされているすべてのビジュアライゼーションを一覧表示します。 |
   | **[!UICONTROL データソースを表示]** | ビジュアライゼーションに対応するデータソース（フリーフォームテーブル）を表示または非表示にします。 |
   | **[!UICONTROL 選択範囲をロック]** | データソースで現在選択されている行にビジュアライゼーションをロックしてから、**[!UICONTROL 選択した位置]**&#x200B;または&#x200B;**[!UICONTROL 選択した項目]**&#x200B;を選択します。 [選択範囲をロック &#x200B;](#lock-selection)を参照してください。 |

## 選択をロック {#lock-selection}

選択範囲をロックすると、テーブルが変更されたときでも、データソース内で選択した行に焦点を当てたビジュアライゼーションが維持されます。 例えば、並べ替えやフィルタリング、日付範囲の変更、セグメントの適用などを行うと、テーブルが変更されます。 ロックされたビジュアライゼーションには、タイトルの横に![LockClosed](/help/assets/icons/LockClosed.svg)が表示されます。

データソース内のセグメント、ディメンションまたは指標が変更され、ロックされたデータが表示されなくなった場合は、**[!UICONTROL テーブルを表示]**&#x200B;を選択して、元のデータソースとは別に、ビジュアライゼーション用の新しいデータソースを生成します。

選択範囲をロックする場合は、次のいずれかのオプションを選択します。

| オプション | 説明 |
| --- | --- |
| **[!UICONTROL 選択した職位]** | ビジュアライゼーションを、データソースで選択された行の&#x200B;**位置**&#x200B;にロックします。 それらの位置は、項目が変更されても、引き続き視覚化されます。 例えば、どのキャンペーンであるかに関係なく、データソースの上位5つのキャンペーン名を常に表示するには、このオプションを選択します。<br><br>分類の行をロックし、それらの行がテーブルに存在しなくなった場合、ビジュアライゼーションは表示されません。 もう一度表示するには、テーブル（日付範囲、セグメント、フィルターなど）を更新するか、ロック選択を更新します。 |
| **[!UICONTROL 選択した項目]** | データソースで選択された特定の&#x200B;**項目**&#x200B;にビジュアライゼーションをロックします。 テーブル内のランキングが変更されても、それらの項目は引き続き可視化されます。 例えば、ランクに関係なく、常に同じ5つのキャンペーン名を表示するには、このオプションを選択します。 |
