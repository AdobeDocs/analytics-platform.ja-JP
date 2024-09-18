---
description: アラートを使用すると、通知をきめ細かく制御したり、異常値検出と統合したりできます。
title: アラートの概要
feature: Workspace Basics
role: User, Admin
source-git-commit: def8b074ea468e409e340415d5e96f75d6b69312
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 28%

---

# アラートの概要

Customer Journey Analyticsのアラートを使用すると、変更された割合や特定のデータポイントに基づいて通知を受け取ることができます。

Customer Journey Analyticsパッケージによっては、異常値のしきい値に基づいてアラートをトリガーすることもできます。 これらのアラート（「インテリジェントアラート」とも呼ばれます）は、[ 異常値検出 ](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md) と統合され、最も必要なときにトリガーされる詳細なコントロールを提供します。

アラートを使用すると、次のことができます。

* アラートがトリガーされる頻度のプレビュー
* 自動生成される Analysis Workspace プロジェクトへのリンクが記載された電子メールまたは SMS によるアラートの送信
* 1 つのアラートで複数の指標を示す「積み重ね」アラートの作成
* 異常値（90%、95%、99%、99.75%、99.9% のしきい値、変化率 %、上/下）に基づいてアラートを作成できます（Select、Prime または Ultimate パッケージを利用しているお客様のCustomer Journey Analyticsでのみ利用可能）。

次のビデオチュートリアルでは、アラートの基本的な概要を説明します。[ アラート ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/intelligent-alerts.html?lang=ja) （5:34）

## Adobe AnalyticsとのCustomer Journey Analyticsにおけるアラートの違いについて

Customer Journey Analyticsでアラートを使用するプロセスは、Adobe Analyticsでアラートを使用するプロセスとほとんど同じです。 ただし、重要な違いがあります。

詳しくは、[ アラート機能の比較：Customer Journey AnalyticsとAdobe Analytics](/help/components/c-intelligent-alerts/alerts-feature-comparison.md) を参照してください。

## アラートの異常値ルックバック

>[!NOTE]
>
>異常値検出を使用したアラート（_インテリジェントアラート_ とも呼ばれます）は、Customer Journey Analyticsの Select、Prime または Ultimate パッケージを使用している組織でのみ使用できます。

異常値検出を使用するアラートの場合、トレーニング期間は、アラートに選択した精度に応じて異なります。

* 月単位の精度：15 ヶ月 + 前年の同じ時間範囲
* 週単位の精度：15 週 + 前年の同じ時間範囲
* 日単位の精度：35 日 + 前年の同じ時間範囲
* 時間単位の精度：336 時間

詳しくは、[ 異常値検出で使用される統計的手法 ](/help/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) を参照してください。

## アラートの作成

Customer Journey Analyticsでアラートを作成する方法について詳しくは、[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md) を参照してください。

>[!IMPORTANT]
>
>タイムスタンプ付きデータを使用してアラートを作成すると、アラートが誤って起動される可能性があります。Adobeでは、アラートにタイムスタンプのないデータを使用することをお勧めします。

## アラートの管理

アラートマネージャーでは、既存のアラートを管理できます。 タグ付け、名前の変更、削除など、アラートに対して様々な管理タスクを実行できます。

Customer Journey Analyticsで既存のアラートを管理する方法について詳しくは、「[ アラートの管理 ](/help/components/c-intelligent-alerts/alert-manager.md)」を参照してください。

