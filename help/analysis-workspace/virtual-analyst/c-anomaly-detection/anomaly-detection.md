---
description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
title: 異常値検出の概要
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 95b8022db4c173b27327469fe8c34afa1ea27796
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 92%

---


# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。

[異常値検出のビデオチュートリアル](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html) (4:53)

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼できる指標（KPI）の予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオバッファーイベントの急増
* ビデオの低ビットレートの下落

Analysis Workspace の異常値検出アルゴリズムには以下が含まれています。

* 既存の毎日の精度に加えて、1 時間ごと、毎週および毎月の精度のサポート
* シーズナリティ（「ブラックフライデー」など）や休日の認識
