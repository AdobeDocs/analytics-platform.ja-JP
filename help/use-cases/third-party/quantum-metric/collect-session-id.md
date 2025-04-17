---
title: Customer Journey Analyticsでの Quantum Metric セッション ID の収集
description: 実装を変更してセッション ID を含めると、Customer Journey Analyticsで分析できるようになります。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: cfe4bafd-afe6-4738-94f1-30882893b3b6
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---

# Customer Journey Analyticsでの Quantum Metric セッション ID の収集

[Quantum Metric セッションの再生を結び付ける ](tie-session-replays.md) または [Quantum Metric ヒートマップを使用する ](heatmap.md) などのユースケースでは、Quantum Metric セッション ID を収集するように実装を変更する必要があります。 このページでは、そのデータを既存の実装に正常に取り込むためのプロセスの概要を説明します。

## 前提条件：

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
1. Customer Journey Analyticsに移動し、必要に応じて ]**データ管理**[!UICONTROL  から **[!UICONTROL データビュー]** を選択します。
1. 目的の既存のデータビューを選択します。
1. 左側の Quantum Metric session ID フィールドリストを見つけて、中央のディメンション領域にドラッグします。
1. 右側のウィンドウで、「永続性 [ 設定を ](/help/data-views/component-settings/persistence.md) セッション」に設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。


