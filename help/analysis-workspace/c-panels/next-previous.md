---
description: 特定のディメンションの次または前のディメンション項目を表示するパネル。
title: 次または前の項目パネル
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: ht
source-wordcount: '457'
ht-degree: 100%

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

_この記事では、_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_ の次の項目または前の項目パネルについて説明します。<br/>_この記事の_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** バージョンについては、[次の項目または前の項目パネル](https://experienceleague.adobe.com/ja/docs/analytics/analyze/analysis-workspace/panels/next-previous)を参照してください。_

>[!ENDSHADEBOX]

**[!UICONTROL 次または前の項目]**&#x200B;パネルには、特定のディメンションの次または前のディメンション項目を識別する多数のテーブルおよびビジュアライゼーションが含まれています。例えば、顧客がホームページを訪問した後に、どのページを最も頻繁に訪問したかを探索する必要があるとします。

## 使用 {#use}

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_container"
>title="コンテナ"
>abstract="コンテナを選択して、問い合わせの範囲を決定します。"

**[!UICONTROL 次または前の項目]**&#x200B;パネルを使用するには：

1. **[!UICONTROL 次または前の項目]**&#x200B;パネルを作成します。パネルの作成方法について詳しくは、[パネルの作成](panels.md#create-a-panel)を参照してください。

1. パネルの[入力](#panel-input)を指定します。

1. パネルの[出力](#panel-output)を確認します。

### パネル入力

次の入力設定を使用して、[!UICONTROL 次または前の項目]パネルを設定できます。

![次または前の項目パネル](assets/next-or-previous-item.png)

| 入力 | 説明 |
| --- | --- |
| **[!UICONTROL ディメンション]** | 次または前の項目を探索するディメンションを選択します。 |
| **[!UICONTROL ディメンション項目]** | 次／前のお問い合わせの中心となる特定のディメンション項目を選択します。 |
| **[!UICONTROL 方向]** | [!UICONTROL 次]または[!UICONTROL 前]のどちらのディメンション項目を検索するかを指定します。 |
| **[!UICONTROL コンテナ]** | 問い合わせの範囲を決定するために、コンテナ（**[!UICONTROL グローバルアカウント]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL アカウント]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 購買グループ]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL 商談]** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}、**[!UICONTROL セッション]**&#x200B;または&#x200B;**[!UICONTROL ユーザー]**）を選択します。 |

{style="table-layout:auto"}

「**[!UICONTROL 作成]**」を選択して、パネルを作成します。

### パネル出力

[!UICONTROL 次または前の項目]パネルでは、豊富なデータとビジュアライゼーションのセットが返されるので、特定のディメンション項目の前後の発生件数をより深く理解できます。


![次／前のパネル出力](assets/next-or-previous-item-output.png)


| ビジュアライゼーション | 説明 |
| --- | --- |
| **[!UICONTROL 横棒グラフ]** | 選択したディメンション項目に基づいて、次の（または前の）項目を一覧表示します。個々のバーの上にポインタを合わせると、フリーフォームテーブル内の対応する項目がハイライト表示されます。 |
| **[!UICONTROL 数値の概要]** | 今月（これまで）のすべての次または前のディメンション項目の発生件数の概要。 |
| **[!UICONTROL フリーフォームテーブル]** | 選択したディメンション項目に基づいて、次の（または前の）項目を表形式で一覧表示します。例えば、ホームページまたはワークスペースページの後（または前）にその人物が訪問した一番人気のページ（発生ごと）。 |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[パネルの作成](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
