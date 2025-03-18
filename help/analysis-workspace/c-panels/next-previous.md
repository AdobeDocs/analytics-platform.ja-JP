---
description: 特定のディメンションの次または前のディメンション項目を表示するパネル。
title: 次または前の項目パネル
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: 2c28d9658165baf4de9519733c321d47c71f2bda
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 26%

---

# 次または前の項目パネル {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="次または前の項目"
>abstract="パネルを作成して、ユーザーが来訪前にいたディメンションまたはユーザーが次に移動するディメンションを理解します。"

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="次または前の項目"
>abstract="訪問者が来訪前にいた場所または次に移動する場所として最も一般的なものを分析します。ビジュアライゼーションに使用するディメンション、ディメンション項目、方向およびコンテナを指定します。"



<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_この記事は、![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)_**Customer Journey Analytics_ の次または前の項目パネルに関する説明です**_。<br/>_この記事の_![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** バージョンについては、[](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) 次または前の項目パネル _を参照してください。

>[!ENDSHADEBOX]

**[!UICONTROL 次または前の項目]** パネルには、特定のディメンションの次または前のディメンション項目を識別する多数のテーブルおよびビジュアライゼーションが含まれています。 例えば、顧客がホームページを訪問した後に最も頻繁に訪問したページを調べる必要があるとします。

## 使用 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="コンテナ"
>abstract="コンテナを選択して、問い合わせの範囲を決定します。"

**[!UICONTROL 次または前の項目]** パネルを使用するには：

1. **[!UICONTROL 次または前の項目]** パネルを作成します。 パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

[!UICONTROL  次または前の項目 ] パネルは、次の入力設定を使用して設定できます。

![ 次または前の項目パネル ](assets/next-or-previous-item.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL ディメンション]** | 次または前の項目を調査するディメンションを選択します。 |
| **[!UICONTROL ディメンション項目]** | 次/前の問い合わせの中央にある特定のディメンション項目を選択します。 |
| **[!UICONTROL 方向]** | 検索するディメンション項目が [!UICONTROL  次へ ] か [!UICONTROL  前へ ] かを指定します。 |
| **[!UICONTROL コンテナ]** | コンテナ [!UICONTROL  セッション ] または [!UICONTROL  個人 ] （デフォルト）を選択して、問い合わせの範囲を決定します。 |

{style="table-layout:auto"}

**[!UICONTROL ビルド]** を選択して、パネルをビルドします。

### パネル出力

[!UICONTROL  次または前の項目 ] パネルは、豊富なデータとビジュアライゼーションのセットを返し、特定のディメンション項目の後または前の発生件数をより深く理解するのに役立ちます。


![ 次/前のパネル出力 ](assets/next-or-previous-item-output.png)


| ビジュアライゼーション | 説明 |
| --- | --- |
| **[!UICONTROL 横棒グラフ]** | 選択したディメンション項目に基づいて、次の項目（または前の項目）をリストします。 個々のバーの上にマウスポインターを置くと、フリーフォームテーブルの対応する項目がハイライトされます。 |
| **[!UICONTROL 数値の概要]** | 当月（これまで）の次または前のすべてのディメンション項目の発生件数の概要。 |
| **[!UICONTROL フリーフォームテーブル]** | 選択したディメンション項目に基づいて、次の（または前の）項目をテーブル形式でリストします。 例えば、ユーザーがホームページまたは Workspace ページの後（または前）に移動した、最も人気の高いページ（発生件別）です。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[パネルの作成](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
