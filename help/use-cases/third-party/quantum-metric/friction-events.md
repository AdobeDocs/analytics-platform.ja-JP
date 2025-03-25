---
title: Quantum Metric friction イベントのCustomer Journey Analyticsへの追加
description: Quantum Metric で収集されたフリクションイベントを使用して、Customer Journey Analyticsでインサイトに深みを加えます。
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 10a70743d292e50ca5aea3225897e7097fa4fc8a
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# Quantum Metric friction イベントのCustomer Journey Analyticsへの追加

Quantum Metric は、ページ読み込み速度の低下、ページ読み込みエラー、レイジクリック数などの摩擦イベントを収集します。 これらのイベントは、ユーザージャーニーで補完的なイベントとしてCustomer Journey Analyticsに渡すことができます。 この結合データを使用すると、ダウンストリーム指標に対する摩擦の影響をより深く理解できます。

## 前提条件：

このユースケースには次の 2 つの要件があります。

* Quantum Metric の **Dev Ops** パッケージを利用できる権限が必要です。
* Adobe Experience Platform Data Collection でタグを使用する必要があります。

## 手順 1:Quantum Metric タグ拡張機能を使用して摩擦イベントをキャプチャする

Quantum Metric CSM チームは、追加する適切なスキーマ要素を判断するのに役立ち、Customer Journey Analyticsで使用する目的のデータを収集するように実装を変更するように指示します。 詳しくは、Quantum Metric カスタマーサクセスマネージャーにお問い合わせください。

最終的には、フィールドで摩擦イベント名のトラッキングを開始する必要があります。

## 手順 2：含まれるデータセットフィールドを確認する

接続内のデータセットに、目的のデータセットの Quantum Metric セッション ID があることを確認します。

## 手順 3:Customer Journey Analyticsのデータビューへの 1 つ以上のディメンションと指標の追加

既存のデータビューを編集し、セッション ID をCustomer Journey Analyticsで使用可能なディメンションとして追加します。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、トップメニューで **[!UICONTROL データビュー]** を選択します。
1. 目的の既存のデータビューを選択します。
1. 左側の量子指標の摩擦イベントフィールドリストを見つけて、中央の指標領域にドラッグします。
1. 右側のペインで、「[ 値を含める/除外 ](/help/data-views/component-settings/include-exclude-values.md)」設定を、追跡する摩擦イベントに設定します。 複数の摩擦イベントを同じ指標に追加して、それらを組み合わせることができます。 また、摩擦イベントフィールドの別のコピーを指標領域にドラッグして、他の摩擦イベントを別の指標として追跡することもできます。
1. 必要なディメンションと指標をすべて作成したら、「**[!UICONTROL 保存]**」をクリックします。

## 手順 4:Analysis Workspaceで、残りのデータと共にディメンションおよび指標を使用する

残りの訪問者データと共に収集された Quantum Metric friction event データを使用すると、Customer Journey Analyticsの他のディメンションや指標とまったく同じように使用できます。

1. [experience.adobe.com](https://experience.adobe.com) にログインします。
1. Customer Journey Analyticsに移動し、上部のメニューで ]**0}Workspace} を選択します。**[!UICONTROL 
1. 既存のプロジェクトを選択するか、プロジェクトを作成します。
1. [ フリーフォームテーブル ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) を作成します。
1. 分析に必要なディメンションと指標をWorkspace キャンバスにドラッグします。

考えられる分析アイデアは次のとおりです。

* 摩擦イベントデータの経時的なトレンド
* フォールアウトまたはファネルビジュアライゼーションで、Customer Journey Analytics イベントを一部のステップとして追加し、Quantum Metric friction イベントを他のステップとして追加します。 このレポートを使用すると、訪問者が最も頻繁にトラブルに巻き込まれる場所を確認できます。
* 摩擦イベントが発生した訪問者にフィルターを作成して適用し、より深く分析できます
