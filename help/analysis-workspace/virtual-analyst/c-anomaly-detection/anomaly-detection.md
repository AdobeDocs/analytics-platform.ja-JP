---
description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
title: 異常値検出の概要
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 96%

---


# 異常値検出の概要

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。

[異常値検出（YouTube）](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)（4:53）

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼できる指標（KPI）の予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオバッファーイベントの急増
* ビデオの低ビットレートの下落

異常値検出と[貢献度分析](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)の双方が、Analysis Workspace の主要ワークフローです。毎日の異常値に対して貢献度分析を実行し、Analysis Workspace プロジェクトに結果を埋め込むことができます。

>[!IMPORTANT]
>
>貢献度分析は、Customer Journey Analyticsではまだ使用できません。

Analysis Workspace の異常値検出アルゴリズムには以下が含まれています。

* 既存の毎日の精度に加えて、1 時間ごと、毎週および毎月の精度のサポート
* シーズナリティ（「ブラックフライデー」など）や休日の認識

## 異常値検出をオフにする

列設定に移動して「**[!UICONTROL 異常値]**」をオフにすることで、異常値検出を列レベルでオフにすることができます。

![](assets/turnoff_anomalies.png)
