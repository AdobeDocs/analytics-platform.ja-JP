---
description: Analysis Workspace でのデータ異常値検出について説明します。
title: 異常値検出の概要
feature: Anomaly Detection
exl-id: f706cdb9-bc80-42b9-9450-4f68bdb3fd85
role: User
TQID: https://experienceleague.adobe.com/beFLMQfzXJUoCbg6fSLpFqcbaB7GSuo6SHroSS6V5wI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: aff2ef09-fc60-4018-9197-e2befd623064
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 83%

---

# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。

[異常値検出のビデオチュートリアル &#x200B;](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace.html?lang=ja) （4:53）

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。 つまり、どの統計的変動が重要で、どの統計的変動が重要でないかを特定することができます。 そして、真の異常値の根本原因を特定することができます。 さらに、信頼性の高い指標（KPI）予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上高の低い注文数のスパイク
* 体験版登録数のスパイクまたは下落
* ランディングページビュー数の下落
* ビデオバッファーイベント数のスパイク
* 低ビデオビットレートのスパイク

Analysis Workspace の異常値検出アルゴリズムには、次の機能が含まれます

* 既存の日単位の精度に加えて、時間単位、週単位、月単位の精度のサポート。
* 季節性（「Black Friday」など）や休日の認識。
