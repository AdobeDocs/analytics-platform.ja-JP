---
description: Customer Journey AnalyticsとAdobe Analyticsでのアラートの違いについて説明します
title: アラート機能の比較Customer Journey AnalyticsとAdobe Analytics
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
TQID: https://experienceleague.adobe.com/NEm3Mu7q6RDKbCyG-PJzOFPrjJF4Y-unHgyBXyKd1HM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: a8b1c240-f315-46e3-b813-f545c4279dd1id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 25%

---

# アラート機能の比較

Adobe Customer Journey Analytics でアラートを使用するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。 ただし、重要な違いがあります。 次のセクションでは、主な違いについて説明します。

## 時間別アラートは利用できません

時間別アラートは&#x200B;**not** Customer Journey Analyticsで利用できますが、時間別アラートはAdobe Analyticsで利用できます。 Customer Journey Analytics では、アラートを日単位、週単位、月単位で設定できます。

Adobe Experience Platformには、さまざまな方法でデータを取り込むことができます。 その結果、1時間の制約の中でデータの完全性と可用性を確実に達成することはできません。  データ取り込みの柔軟性は、不完全なデータの可能性が高いため、毎時間のアラートは実用的ではないことを意味します。 詳しくは、「[ データ取り込み時間が異なる](#data-ingestion-times-vary-in-customer-journey-analytics)」を参照してください。

## データ収集にかかる時間は様々です

データが完成し、Customer Journey Analyticsでレポートを利用できるようになるまでに必要な時間は、組織によって異なります。

その理由は次のとおりです。

* あらゆる種類のデータスキーマとタイプを保持するPlatformの機能

  Adobe Analytics（web データのみに関するレポート）とは異なり、[さまざまな種類のデータをAdobe Experience Platform](/help/data-ingestion/data-ingestion.md)に取り込んでCustomer Journey Analyticsでレポートできます。また、あらゆる種類のデータを順次送信したり、リアルタイムで送信したりすることはできません。

* Platform データセットへのバッチデータの配信の遅延

  一部のデータは、より早くレポートするために利用できる場合がありますが、すべての[ バッチデータはPlatform データセット ](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.)に取り込まれます。通常、データイベント時間から3～9時間経過したデータが取り込まれます。 アラートを正確に実行するには、データの取り込みを完了し、すべてのバッチデータをデータセットに格納する必要があります。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

このため、取り込み可能な様々な種類のイベントデータのデータ取り込みは、データのイベント時間から3～9時間経過した後にのみ完了します。 アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。

この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。

デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。 ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。

遅延の調整方法と、その際に考慮すべき要因について詳しくは、[ アラートの作成](/help/components/c-intelligent-alerts/alert-builder.md)を参照してください。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## アラートの作成

Adobe AnalyticsのAnalysis Workspaceでは、様々な方法で[Analysis Workspaceからアラートを作成できます](https://experienceleague.adobe.com/en/docs/analytics/components/alerts/alert-builder)。 Customer Journey Analyticsでは、フリーフォームテーブルの選択範囲からAnalysis Workspaceで作成できるのは[ アラート ](alert-builder.md)のみです。

Adobe AnalyticsとCustomer Journey Analyticsの両方で、[ アラートマネージャー](alert-manager.md)によるアラートの作成がサポートされています
