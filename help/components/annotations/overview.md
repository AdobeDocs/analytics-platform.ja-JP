---
title: 注釈の概要
description: ワークスペースで注釈を使用する方法。
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 30%

---

# 注釈の概要

注釈を使用すると、コンテキストデータのニュアンスとインサイトを、組織の他の関係者に効果的に伝えることができます。 注釈を使用すると、カレンダーイベントを特定のディメンションと指標に関連付けることができます。 日付や日付範囲に、既知のデータの問題、祝日、キャンペーン開始などの注釈を付けることで、次に、イベントをグラフィカルに表示し、キャンペーンやその他のイベントがサイトトラフィック、モバイルアプリの使用状況、収益、その他の指標に影響を与えているかどうかを確認できます。

例えば、プロジェクトを組織と共有しているとします。 受け入れられるオファーが大幅に減少した場合は、**無効なオファー** 注釈を作成して、データビュー全体でスコープを設定できます。 その日付を含んだデータセットをユーザーが表示すると、データと共に、プロジェクト内の注釈が表示されます。

![注釈がハイライト表示された折れ線グラフ。](assets/annotation-example.png)

注釈は次の場所に適用できます。

* 単一の日付または日付範囲。

* データセット全体、または特定の指標、ディメンション、フィルター。

* 注釈が作成されるプロジェクト（デフォルト）またはすべてのプロジェクト。

* 注釈が作成されるデータビュー（デフォルト）、またはすべてのデータビュー。

注釈の作成に使用できる様々なオプションについては、[ 注釈の作成 ](/help/components/annotations/create-annotations.md) を参照してください。 その後、[ 注釈ビルダー ](create-annotations.md#annotation-builder) で注釈を作成、変更および保存します。

注釈を管理するには、[ 注釈マネージャー ](manage-annotations.md) を使用します。

## 注釈のオンまたはオフ

注釈は、複数のレベルでオンまたはオフにできます。

| レベル | 方法… |
|---|---|
| **ビジュアライゼーション** | ![ 設定 ](/help/assets/icons/Setting.svg)/**[!UICONTROL 設定]**/**[!UICONTROL 注釈を表示]** を有効または無効にします。<br/>![ ビジュアライゼーションの注釈の無効化 ](/help/components/annotations/assets/annotations-visualization.png) |
| **プロジェクト** | Workspace プロジェクトメニューから、**[!UICONTROL プロジェクト]** / **[!UICONTROL プロジェクト情報および設定]** を選択し、「注釈を表示 **[!UICONTROL を有効または無効に]** ます。<br/>![ プロジェクトの注釈を無効にする ](/help/components/annotations/assets/annotations-project.png) |
| **ユーザー** | **[!UICONTROL コンポーネント]** タブから **[!UICONTROL 環境設定]** を選択するか、Workspace プロジェクトメニューから **[!UICONTROL プロジェクト]**/**[!UICONTROL ユーザー環境設定]** を選択します。 <br/>**[!UICONTROL 環境設定]** で「**[!UICONTROL プロジェクトと分析]**」を選択します。 左側のタブバーから、「**[!UICONTROL データ]**」を選択します。 下部で、「フリーフォームテーブル **[!UICONTROL 見出しの下にある]** 注釈を表示 **[!UICONTROL を有効または無効に]** ます。<br/>![ ユーザーの注釈の無効化 ](/help/components/annotations/assets/annotations-user.png) |
