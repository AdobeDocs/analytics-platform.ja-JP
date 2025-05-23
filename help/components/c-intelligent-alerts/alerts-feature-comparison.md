---
description: Customer Journey AnalyticsとAdobe Analyticsのアラートの違いを説明します
title: アラート機能のCustomer Journey AnalyticsとAdobe Analyticsの比較
feature: Workspace Basics
role: User, Admin
exl-id: 04e819c4-9fb5-4459-9f8b-40d78385ed90
source-git-commit: 53069702055e0adf7abf9061c592fb15772ded73
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 7%

---

# アラート機能の比較

Customer Journey Analytics でアラートを使用するプロセスは、Adobe Analytics でアラートを使用するプロセスとほとんど同じです。 ただし、重要な違いがあります。 以下の節では、主な違いについて説明します。

## Customer Journey Analyticsでは、時間別アラートを使用できません

Adobe Analyticsとは異なり、Customer Journey Analyticsでは 1 時間ごとのアラートは使用できません。 Customer Journey Analytics では、アラートを日単位、週単位、月単位で設定できます。

これは、Customer Journey Analyticsでデータをレポートする前に、データをAdobe Experience Platformに取り込む様々な方法があるためです。 データの完全性と可用性は 1 時間以内には確実に達成できないので、1 時間ごとのアラートは不完全なデータの可能性が高いため、実用的ではありません。 詳しくは、[ データ取り込み時間は様々 ](#data-ingestion-times-vary-in-customer-journey-analytics) を参照してください。

## Customer Journey Analyticsでのデータ取得時間は場合によって異なります

データが完了し、Customer Journey Analyticsでレポートできるようになるまでの時間は、組織によって異なります。

これは、次の理由によるものです。

* あらゆる種類のデータスキーマおよびデータタイプを保持する Platform の機能

  Web データのみをレポートするAdobe Analyticsとは異なり、[Adobe Experience Platformに様々な種類のデータを取り込んでCustomer Journey Analyticsでレポートする ](/help/data-ingestion/data-ingestion.md) ことができ、すべての種類のデータを順番にリアルタイムで送信できるわけではありません。

* Platform データセットへのバッチデータの配信遅延

  一部のデータはより早くレポートできる場合がありますが、すべての [ バッチデータは Platform データセットに取り込まれます ](/help/data-ingestion/data-ingestion.md#ingest-and-use-batch-data.) 通常、データイベント時刻から 3～9 時間後の範囲です。 アラートを正確にするには、データ取り込みが完了し、データセットで使用可能なすべてのバッチデータが揃っている必要があります。<!--3 to 9 hours is a sweet spot, what we are suggesting.  -->

これらの理由から、取り込み可能な様々な種類のイベントデータのデータ取り込みは、通常、データイベント時間から 3～9 時間後に少し遅れて完了します。 アラートを正確にするには、特定のイベント範囲のイベントデータが完全である必要があります。つまり、Adobeは指定されたイベント範囲のイベントデータを受け取らなくなります。

この取り込み時間の遅延を考慮して、アラートを送信するまでのデフォルトの遅延は 9 時間になっています。

デフォルトの 9 時間の遅延は、0 ～ 24 時間の間に調整できます。 ただし、遅延を 9 時間未満に減らすと、不完全なデータに関するレポートを作成していることになり、アラート情報が不正確になる可能性があります。

遅延の調整方法と、調整する際に考慮すべき要因について詳しくは、[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md) を参照してください。

<!-- Starting with "However," the rest of this information should probably go into the actual documentation where we document the option to adjust the delay. -->

## Analysis Workspaceからアラートを作成するオプションは使用できません

Adobe AnalyticsのAnalysis Workspaceでは、以下に示す任意の方法でAnalysis Workspaceからアラートを作成できます。 Customer Journey Analyticsでは、Analysis Workspaceからアラートを作成するオプションはまだ使用できません。 代わりに、「[ アラートの作成 ](/help/components/c-intelligent-alerts/alert-builder.md)」の説明に従って、アラートビルダーにアクセスします。

Adobe Analyticsでは、次のオプションを使用できます。

* フリーフォームテーブルで 1 つ以上の行項目を選択し、右クリックして **[!UICONTROL 選択からアラートを作成]** を選択します。

  これにより、アラートビルダーに即座に事前入力して、正しい指標とセグメントでアラートを作成できます。

* Analysis Workspace でプロジェクトを開き、**[!UICONTROL コンポーネント]**／**[!UICONTROL アラートを作成]**&#x200B;を選択します。

* Analysis Workspaceでプロジェクトを開き、ショートカットキー **[!UICONTROL *ctrl *]**+**[!UICONTROL * shift *]** + **[!UICONTROL *a *]**（Windows）または&#x200B;**[!UICONTROL * cmd *]** + **[!UICONTROL *shift *]**+**[!UICONTROL * a *]** （macOS）を使用します。
