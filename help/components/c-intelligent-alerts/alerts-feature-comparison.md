---
description: Customer Journey AnalyticsとAdobe Analyticsのアラートの違いを説明します
title: アラート機能のCustomer Journey AnalyticsとAdobe Analyticsの比較
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 1891f73f4326a178b293e7c3763d0d1dbc000a25
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 23%

---

# アラート機能の比較

Adobe Customer Journey Analytics でアラートを使用するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。ただし、重要な違いがあります。 以下の節では、主な違いについて説明します。

## 時間別アラートは使用できません

1 時間ごとのアラートはCustomer Journey Analyticsで使用でき **せんが** Adobe Analyticsでは使用できます。 Customer Journey Analytics では、アラートを日単位、週単位、月単位で設定できます。

様々な方法でAdobe Experience Platformにデータを取り込むことができます。 その結果、1 時間の制約内でデータの完全性と可用性を確実に達成することはできません。  データ取り込みの柔軟性は、不完全なデータの可能性が高いため、1 時間ごとのアラートは実用的でないことを意味します。 詳しくは、[ データ取り込み時間は様々 ](#data-ingestion-times-vary-in-customer-journey-analytics) を参照してください。

## データ取り込み時間は様々です

データが完了し、Customer Journey Analyticsでレポートできるようになるまでの時間は、組織によって異なります。

これは、次の理由によるものです。

* あらゆる種類のデータスキーマおよびデータタイプを保持する Platform の機能

  Web データのみをレポートするAdobe Analyticsとは異なり、[Adobe Experience Platformに様々な種類のデータを取り込んでCustomer Journey Analyticsでレポートする ](/help/data-ingestion/data-ingestion.md) ことができ、すべての種類のデータを順番にリアルタイムで送信できるわけではありません。

* Platform データセットへのバッチデータの配信遅延

  一部のデータはより早くレポートできる場合がありますが、すべての [ バッチデータは Platform データセットに取り込まれます ](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) 通常、データイベント時刻から 3～9 時間後の範囲です。 アラートを正確にするには、データ取り込みが完了し、データセットで使用可能なすべてのバッチデータが揃っている必要があります。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

これらの理由から、取り込み可能な様々な種類のイベントデータのデータ取り込みは、通常、データイベント時間から 3～9 時間後に少し遅れて完了します。 アラートを正確にするには、特定のイベント範囲のイベントデータを完全にする必要があります。つまり、アドビでは指定されたイベント範囲のイベントデータを受信しなくなります。

この取り込み時間の遅延を考慮して、アラートを送信する前にデフォルトで 9 時間の遅延が設定されます。

デフォルトの 9 時間の遅延を 0～24 時間の間で調整できます。ただし、遅延を 9 時間未満に短縮すると、不完全なデータをレポートすることになり、アラート情報が不正確になる場合があります。

遅延の調整方法と、調整する際に考慮すべき要因について詳しくは、[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md) を参照してください。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Analysis Workspaceからのアラートの作成は使用できません

Adobe AnalyticsのAnalysis Workspaceでは、以下に示す任意の方法でAnalysis Workspaceからアラートを作成できます。 Customer Journey Analyticsでは、Analysis Workspaceからアラートを作成するオプションはまだ使用できません。 代わりに、「[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md)」の説明に従って、アラートビルダーにアクセスします。

Adobe Analyticsでは、次のオプションを使用できます。

* フリーフォームテーブルで 1 つ以上の行項目を選択し、右クリックして **[!UICONTROL 選択からアラートを作成]** を選択します。

  これにより、アラートビルダーに即座に事前入力して、正しい指標とセグメントでアラートを作成できます。

* Analysis Workspace でプロジェクトを開き、**[!UICONTROL コンポーネント]**／**[!UICONTROL アラートを作成]**&#x200B;を選択します。

* Analysis Workspaceでプロジェクトを開き、ショートカットキー **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**（Windows）または&#x200B;**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** （macOS）を使用します。
