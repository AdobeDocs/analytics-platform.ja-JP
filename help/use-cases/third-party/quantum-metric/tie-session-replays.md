---
title: Quantum Metric session replays to data in Customer Journey Analytics
description: Link Quantum Metric セッションでは、CJAデータを使用して再生し、「何」の背後にある「理由」をより深く理解します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: d722e88d163dd99aa7b98c6fa6cd75028d7d9e6f
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 1%

---

# Quantum Metric session replays to data in Customer Journey Analytics

Quantum Metric セッションの再生をCJAのデータとリンクさせることで、お客様は「何」の背後にある「理由」をより深く理解できます。  Workspaceを使用してフリクションのあるセッションを検出し、ハイパーリンクされたセッション ID をクリックして、Quantum Metric でのセッションの再生を調べることができます。  このデータにより、セッション内の動作を確認し、消費者の摩擦を引き起こす要因をより深く理解できます。

## 前提条件

このユースケースでは、残りの実装と共に Quantum Metric のセッション ID を収集する必要があります。 実装の変更方法については、[Customer Journey Analyticsでの Quantum Metric セッション ID の収集 ](collect-session-id.md) を参照してください。

## 手順 1：セッション ID ディメンションに対応するようにWorkspaceを設定する

Workspaceでフリーフォームテーブルを作成し、セッション ID 値が Quantum Metric に直接リンクするように設定します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで ]**0}Workspace} を選択します。**[!UICONTROL 
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) を作成します。
1. セッション ID ディメンションをWorkspace キャンバスにドラッグします。
1. ディメンション列ヘッダーを右クリックし、「**[!UICONTROL すべてのディメンション項目のハイパーリンクを作成]**」を選択します。
1. **[!UICONTROL カスタム URL の作成]** を選択します。
1. 次の URL 構造を貼り付けます。

   ```
   https://adobe.quantummetric.com/#/replay/cookie:$value
   ```

1. 「**[!UICONTROL 作成]**」をクリックします。

各セッション ID は、クリック可能なリンクになりました。 これらのリンクを使用すると、新しいタブで Quantum Metric に移動し、その特定のセッションをより詳細に分析できます。 Analysis Workspace ディメンション項目にハイパーリンクを追加する方法について詳しくは、[ フリーフォームテーブルでのハイパーリンクの作成 ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) を参照してください。

## 手順 2 Customer Journey Analyticsからのセッションの表示

クリック可能なリンクを含んだWorkspace レポートを作成したら、Customer Journey Analyticsのフィルターを使用して、Quantum Metric で詳細に分析できる興味深いセッションを特定できます。
この表は、そのセグメント内のすべてのセッションを返します。任意のセッションをクリックすると、QM で詳細を確認できます。  Quantum Metric セッションの再生について詳しくは、https://www.quantummetric.com/platform/session-replayを参照してください。

