---
title: Quantum Metric session replays to data in Customer Journey Analytics
description: Link Quantum Metric セッションでは、CJAデータを使用して再生し、「何」の背後にある「理由」をより深く理解します。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: fcc36457-4ce9-4c93-93e2-de03becfd5da
source-git-commit: 25a2c549c27918f80202bde4cd30e305f4a295f3
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 1%

---

# Quantum Metric session replays to data in Customer Journey Analytics

Quantum Metric セッションの再生をCJAのデータとリンクさせることで、お客様は「何」の背後にある「理由」をより深く理解できます。  Workspaceを使用してフリクションのあるセッションを検出し、ハイパーリンクされたセッション ID をクリックして、Quantum Metric でのセッションの再生を調べることができます。  このデータにより、セッション内の動作を確認し、消費者の摩擦を引き起こす要因をより深く理解できます。  CJAと連動したセッションリプレイを通じて、お客様の行動に関する重要なコンテキストをエクスペリエンスに取り込むことができます。

## 前提条件

以下の手順では、Adobe Experience Platform Data Collection でタグを使用していることを前提としています。 組織でタグを使用しない場合は、これらのデータ収集方法を手動の web SDK実装に適応させることができます。

詳しくは、[Quantum Metric タグ拡張機能 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) のドキュメントを参照してください。

## 手順 1:Quantum Metric タグ拡張機能を使用して Quantum Metric セッション ID を取得する

Adobe Experience Platformに送信するデータに Quantum Metric セッション ID を追加するには、次の手順に従います。

1. タグ UI の Quantum Metric 拡張機能を使用して、Quantum Metric にデータを送信します。
1. 次の 4 つのデータ要素を作成します。
   1. `QuantumMetricSessionID` という名前の Quantum Metric の cookie から Quantum Metric セッション ID をキャプチャするもの
   1. `localStorage` から Quantum Metric セッション ID を抽出するもの。 このデータ要素は、他のデータ要素に設定された Cookie よりも高速に読み込まれる場合があります。
   1. Data Element Assistant またはカスタム JavaScriptを使用して、`localStorage` データ要素から `s` ノードを抽出します。
   1. 最初に cookie データ要素を検索し、見つかった場合は XDM オブジェクトパスに返すロジックを使用するもの。 未定義の場合は、抽出された `localStorage` オブジェクトデータ要素を調べます。
1. 各イベントで送信された XDM オブジェクトに最終的な Quantum Metric セッション ID データ要素を送信します。

>[!NOTE]
>Web SDKは、Quantum Metric コードよりも高速に実行される場合があります。 この場合、セッション ID は後続のヒットで送信されます。 訪問者がバウンスした場合、これらのインスタンスではセッション ID は収集されません。

## 手順 2：含まれるデータセットフィールドを確認する

接続内のデータセットに、目的のデータセットの Quantum Metric セッション ID があることを確認します。

## 手順 3：使用可能なディメンションとしての Quantum Metric セッション ID の追加

既存のデータビューを編集し、セッション ID をCustomer Journey Analyticsで使用可能なディメンションとして追加します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、トップメニューで **[!UICONTROL データビュー]** を選択します。
1. 目的の既存のデータビューを選択します。
1. 左側の Quantum Metric session ID フィールドリストを見つけて、中央のディメンション領域にドラッグします。
1. 右側のウィンドウで、「永続性 [ 設定を ](/help/data-views/component-settings/persistence.md) セッション」に設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## 手順 4：セッション ID ディメンションに対応するようにWorkspaceを設定する

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

各セッション ID は、クリック可能なリンクになりました。 Analysis Workspace ディメンション項目にハイパーリンクを追加する方法について詳しくは、[ フリーフォームテーブルでのハイパーリンクの作成 ](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) を参照してください。

## 手順 5:Customer Journey Analyticsからのセッションの表示

セッションの再生を調べたい魅力的なセグメントが見つかったら、そのセグメントを、セッション ID のリンクを含むパネルに適用し、セグメントでフィルタリングできます。 この表は、そのセグメント内のすべてのセッションを返します。いずれかのセッションをクリックすると、Quantum Metric で詳細を確認できます。

詳しくは、Quantum Metric の [ セッション再生のエンタープライズガイド ](https://www.quantummetric.com/resources/ebook/the-enterprise-guide-to-session-replay) を参照してください。 また、Quantum Metric のカスタマーサポート担当者に連絡するか、[Quantum Metric 顧客リクエストポータル ](https://community.quantummetric.com/s/public-support-page) を通じてリクエストを送信することもできます。
