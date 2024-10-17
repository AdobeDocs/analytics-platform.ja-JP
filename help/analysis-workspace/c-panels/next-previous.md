---
description: 特定のディメンションの次または前のディメンション項目を表示するパネル。
title: 次または前の項目パネル
feature: Panels
role: User, Admin
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 31%

---

# 次または前の項目パネル {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_button"
>title="次または前の項目"
>abstract="パネルを作成して、ユーザーが来訪前にいたディメンションまたはユーザーが次に移動するディメンションを理解します。"

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_nextorpreviousitem_panel"
>title="次または前の項目"
>abstract="訪問者が来訪前にいた場所または次に移動する場所として最も一般的なものを分析します。<br/><br/>**ディメンション**：ディメンションを選択します。例：**ページ**。<br/>**ディメンション項目**：特定のディメンション項目を選択します。例：**ホームページ**。<br/>**方向**：「**次へ**」を選択すると、選択したディメンション項目の直後のディメンション項目が表示されます。「**前へ**」を選択すると、選択したディメンション項目に至るまでのディメンション項目が表示されます。<br/>**コンテナ**：「**セッション**」を選択して同じセッション内の次／前のディメンション項目を表示するか、「**ユーザー**」を選択して同じユーザーの次／前のディメンション項目を表示します。"

<!-- markdownlint-enable MD034 -->



**[!UICONTROL 次または前の項目]** パネルには、特定のディメンションの次または前のディメンション項目を識別する多数のテーブルおよびビジュアライゼーションが含まれています。 例えば、顧客がホームページを訪問した後に最も頻繁に訪問したページを調べる必要があるとします。

## 用途

**[!UICONTROL 次または前の項目]** パネルを使用するには：

1. **[!UICONTROL 次または前の項目]** パネルを作成します。 パネルの作成方法について詳しくは、[ パネルの作成 ](panels.md#create-a-panel) を参照してください。

1. パネルの [ 入力 ](#panel-input) を指定します。

1. パネルの [output](#panel-output) を確認します。

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
>[ パネルを作成 ](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>