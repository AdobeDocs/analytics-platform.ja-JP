---
description: Adobe AnalyticsとのCustomer Journey Analyticsにおけるインテリジェントアラートの違いについて説明します
title: インテリジェントアラート機能の比較Customer Journey AnalyticsとAdobe Analytics
feature: Workspace Basics
role: User, Admin
source-git-commit: 74ad39f6ccc6436f7c8540b7d8b69b20b93d2b5c
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# インテリジェントアラート機能の比較：Customer Journey AnalyticsとAdobe Analytics

{{release-limited-testing}}

Customer Journey Analytics でインテリジェントアラートを使用するプロセスは、Adobe Analytics でインテリジェントアラートを使用するプロセスとほとんど同じです。ただし、重要な違いがあります。

以下の節では、主な違いについて説明します。

## 時間別アラートは、Customer Journey Analyticsでは使用できません

Adobe Analyticsとは異なり、時間別アラートはCustomer Journey Analyticsでは使用できません。 Customer Journey Analyticsとして、アラートを日単位、週単位、月単位で設定できます。

これは、Customer Journey Analyticsでデータがレポートされる前に、データをAdobe Experience Platformに取り込む様々な方法があるためです。 データの完全性と可用性は 1 時間以内には確実に達成できないので、1 時間ごとのアラートは不完全なデータの可能性が高いため、実用的ではありません。 詳しくは、[ データ取り込み時間は様々 ](#data-ingestion-times-vary-in-customer-journey-analytics) を参照してください。

## データ取り込み時間のCustomer Journey Analyticsは様々です

データが完了し、Customer Journey Analyticsでレポートできる状態になるまでの時間は、組織によって異なります。

これは、次の理由によるものです。

* あらゆる種類のデータスキーマおよびデータタイプを保持する Platform の機能

  Web データのみをレポートするAdobe Analyticsとは異なり、[ 様々な種類のデータをAdobe Experience Platformに取り込んでCustomer Journey Analyticsでレポートする ](/help/data-ingestion/data-ingestion.md) ことができ、すべての種類のデータを順番にリアルタイムで送信できるわけではありません。

* Platform データセットへのバッチデータの配信遅延

  一部のデータはより早くレポートできる場合がありますが、すべての [ バッチデータは Platform データセットに取り込まれます ](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) 通常、データイベント時刻から 3～9 時間後の範囲です。 アラートを正確にするには、データ取り込みが完了し、データセットで使用可能なすべてのバッチデータが揃っている必要があります。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

これらの理由から、取り込み可能な様々な種類のイベントデータのデータ取り込みは、通常、データイベント時間から 3～9 時間後に少し遅れて完了します。 アラートを正確にするには、特定のイベント範囲のイベントデータが完全である必要があります。つまり、Adobeは指定されたイベント範囲のイベントデータを受け取らなくなります。

この取り込み時間の遅延を考慮して、アラートを送信するまでのデフォルトの遅延は 9 時間になっています。

デフォルトの 9 時間の遅延は、0 ～ 24 時間の間に調整できます。 ただし、遅延を 9 時間未満に減らすと、不完全なデータに関するレポートを作成していることになり、アラート情報が不正確になる可能性があります。

遅延の調整方法と、調整する際に考慮すべき要因について詳しくは、<!--add link --> を参照してください。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->





