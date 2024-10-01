---
title: 概要データグループコンポーネントの設定
description: 概要データについて適切にレポートできるようにするためのデータセットからのディメンションの設定方法に関する詳細と方法。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: c39ee568-97f6-4925-ae18-3d4a9dfdb6f5
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 17%

---

# [!UICONTROL  概要データグループ ] コンポーネント設定 {#summary-data-group-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_dimension_summarydatagroup"
>title="概要データグループ"
>abstract="概要データグループは、グループ内のすべてのディメンション間の関連付けを作成します。これを使用すると、レポート用に概要データセットのディメンションを他のディメンションと組み合わせることができます。"

<!-- markdownlint-enable MD034 -->


概要データグループは、グループ内のすべてのディメンション間の関連付けを作成します。これを使用すると、レポート用に概要データセットのディメンションを他のディメンションと組み合わせることができます。

![ 概要データグループコンポーネントの設定 ](/help/data-views/assets/summary-data-group.png)

次元のグループ化を作成する手順は、次のとおりです：

1. ディメンションを選択します。
1. ![ChevronDown](/help/assets/icons/ChevronDown.svg)**[!UICONTROL Summary データグループ]** を選択します。
1. **[!UICONTROL グループ化を作成]** を有効にします。
1. 最初の手順で選択したディメンションでグループ化するディメンションを ]**0} 「Dimension」ドロップダウンリストから選択します。**[!UICONTROL &#x200B;データビューに既に追加したディメンションのみが、ドロップダウンリストから使用できます。
1. 必要に応じて、**[!UICONTROL レポートで非表示にする]** を有効にして、グループ化されたディメンションをレポートから非表示にします。 このオプションを有効にすると、グループ化されたディメンションに対して個別に **[!UICONTROL レポートで非表示にする]** を設定するのと同様です。 詳しくは、[ コンポーネント設定 ](overview.md) を参照してください。
1. オプションで、グループ化にディメンションを追加するには、「![ 追加 ](/help/assets/icons/Add.svg)**[!UICONTROL グループにディメンションを追加]**」を選択します。<br/> 概要データグループのディメンションは 10 個に制限されているので、最大 9 個のディメンションを追加できます。

## 同じコンポーネント設定

ディメンションをグループ化する場合は、グループに含まれる各ディメンションの [!UICONTROL  部分文字列 ]、[!UICONTROL  動作（小文字） ] および [!UICONTROL  除外値を含める ] の設定が同じであることを確認する必要があります。 そうしないと、グループ化の前に、グループの各ディメンションが異なる結果を返す可能性があります。
次に例を示します。

1. `campaign_code` （概要データの一部）と `tracking_code` （イベントデータの一部）の概要データグループを作成しました。
1. [!UICONTROL  動作（小文字） ] を `campaign_code` に適用しましたが、`tracking_code` のディメンションには適用していません。

`tracking_code` の値は、`campaign_code` とは異なって表示される場合があります。

>[!IMPORTANT]
>
>次元のグループ化は、1 つの次元からのみ行い、複数の次元からグループ化を適用しないでください。 たとえば、`campaign_name` 次元を `tracking_code` 次元に追加してグループ化を作成する場合、`campaign_name` 次元のグループ化も作成しないでください。
>
