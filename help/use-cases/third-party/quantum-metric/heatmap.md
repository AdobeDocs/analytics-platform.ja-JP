---
title: Customer Journey Analyticsでの Quantum Metric ヒートマップの使用
description: Quantum Metric ヒートマップデータを使用して、ページレベルのエンゲージメントをより深く理解し、消費者の行動に基づいてページを最適化します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: a0f82948895f3eac86cf00df1dec8abc2f723fc2
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Customer Journey Analyticsでの Quantum Metric ヒートマップの使用

Quantum Metric ヒートマッピングをCJA データにリンクすると、ページレベルのエンゲージメントをより深く理解し、消費者の行動に基づいてページを最適化できます。 Workspaceを使用すると、消費者のユーザーフローを理解し、ページ間でたどる消費者のパスを確認できます。 次に、ハイパーリンクされたページ URL をクリックして、ユーザーのコンテンツへのエンゲージメント方法を視覚的にヒートマップできます。

この表は、そのセグメント内のすべてのセッションを返します。任意のセッションをクリックすると、QM で詳細を確認できます。  Quantum Metric セッションの再生について詳しくは、https://www.quantummetric.com/platform/session-replayを参照してください。

## 前提条件

このユースケースでは、残りの実装と共に Quantum Metric のセッション ID を収集する必要があります。 実装の変更方法については、[Customer Journey Analyticsでの Quantum Metric セッション ID の収集 ](collect-session-id.md) を参照してください。

Quantum Metric のヒートマップ機能にアクセスするには、Quantum Metric の **UX Ops** パッケージの権利が必要です。

## Workspaceでフリーフォームテーブルを作成し、セッション ID 値が Quantum Metric に直接リンクするように設定します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで ]**0}Workspace} を選択します。**[!UICONTROL 
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) を作成します。
1. ページ URL ディメンションをWorkspace キャンバスにドラッグします。
1. ディメンション列ヘッダーを右クリックし、「**[!UICONTROL すべてのディメンション項目のハイパーリンクを作成]**」を選択します。
1. **[!UICONTROL カスタム URL の作成]** を選択します。
1. 次の URL 構造を貼り付けます。

   ```
   $value?qm-visible=true
   ```

1. 「**[!UICONTROL 作成]**」をクリックします。

1. 「作成」をクリックし、リンクの 1 つをテストして、QM 拡張機能が開いた状態で URL が開くかどうかを確認します。 メモ – 作業内容が失われないように、別のタブで開きます。


## Customer Journey Analytics内のリンクをクリックした場合のヒートマップの表示

ヒートマッピングの調査対象となるページが見つかったら、URL が含まれるパネルに適用できます。 このテーブルは、対象のページのヒートマップ、スクロールの深さ、インタラクションのキーゾーンを探索できる URL を返します。  Quantum Metric ヒートマップについて詳しくは、https://www.quantummetric.com/platform/interaction-heatmapsを参照してください。


