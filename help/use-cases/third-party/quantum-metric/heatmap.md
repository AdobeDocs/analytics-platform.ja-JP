---
title: Customer Journey Analyticsでの Quantum Metric ヒートマップの使用
description: Quantum Metric ヒートマップデータを使用して、ページレベルのエンゲージメントをより深く理解し、消費者の行動に基づいてページを最適化します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: d861135f-42a4-45ac-8b11-41f151bfce92
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 1%

---

# Customer Journey Analyticsでの Quantum Metric ヒートマップの使用

Quantum Metric ヒートマッピングをCJA データにリンクすると、ページレベルのエンゲージメントをより深く理解し、消費者の行動に基づいてページを最適化できます。 Workspaceを使用すると、消費者のユーザーフローを理解し、ページ間でたどる消費者のパスを確認できます。 次に、ハイパーリンクされたページ URL をクリックして、ユーザーのコンテンツへのエンゲージメント方法を視覚的にヒートマップできます。 Quantum Metric Heatmapping をCJAにリンクすることで、ページレベルのインタラクションをビジネス成果に関連付け、分析を次のレベルに進めることができるようになりました。

この表は、そのセグメント内のすべてのセッションを返します。任意のセッションをクリックすると、QM で詳細を確認できます。  Quantum Metric セッションの再生について詳しくは、https://www.quantummetric.com/platform/session-replayを参照してください。

## 前提条件

Quantum Metric のヒートマップ機能にアクセスするには、Quantum Metric の **UX Ops** パッケージの権利が必要です。

## 手順 1:Workspaceでフリーフォームテーブルを作成し、セッション ID 値が Quantum Metric に直接リンクするように設定します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで **0&rbrace;Workspace&rbrace; を選択します。**
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
1. リンクの 1 つをテストし、Quantum Metric 拡張機能が表示された状態で URL でリンクが開くかどうかを確認します。 これらのリンクは新しいタブで開くので、Workspace プロジェクトは開いたままです。

## 手順 2:Customer Journey Analytics内のリンクをクリックしてヒートマップを表示する

ヒートマッピングを調査するページが見つかったら、目的のパネルに適用できます。 この表は、Quantum Metric を使用してヒートマップ、スクロール深度、インタラクションのキーゾーンを探索できる URL を返します。 詳しくは、[Quantum Metric ヒートマップ製品の概要 ](https://www.quantummetric.com/platform/interaction-heatmaps) を参照してください。 また、Quantum Metric のカスタマーサポート担当者に連絡するか、[Quantum Metric 顧客リクエストポータル ](https://community.quantummetric.com/s/public-support-page) を通じてリクエストを送信することもできます。
