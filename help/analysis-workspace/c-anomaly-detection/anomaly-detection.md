---
description: Analysis Workspace でのデータ異常値検出について説明します。
title: 異常値検出の概要
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
source-git-commit: e07b901f66a59aba1a7a517443eec73387d23c57
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 44%

---

# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。

[ 異常値検出のビデオチュートリアル ](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=ja) （4:53）

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出を使用すると、「真のシグナル」と「ノイズ」を分離し、これらのシグナルや異常に貢献した潜在的な要因を特定できます。 つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼性の高い指標（KPI）予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の大幅な低下
* 売上高の少ない注文の急増
* 体験版登録の急増または減少
* ランディングページビューが削除されます
* ビデオバッファーイベントのスパイク
* ビデオのビットレートが急激に低下する

Analysis Workspaceの異常値検出アルゴリズムには、次のものが含まれます

* 既存の日単位の精度に加えて、時間単位、週単位、月単位の精度をサポートします。
* 季節性（「ブラックフライデー」など）と休日の認識。
