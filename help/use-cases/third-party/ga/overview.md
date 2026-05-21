---
title: Google Analytics からデータを移行
description: Google Analytics から Adobe Experience Platform にデータを移動する方法と Customer Journey Analytics でレポートを表示する方法に関する包括的なワークフローについて説明します。
exl-id: 10c485c9-66ab-4925-a357-a66a374d4c6f
feature: Use Cases
role: Admin
TQID: https://experienceleague.adobe.com/C9rt1pyuM6ykLUlXCHc0ITwGeGcuLw6qisXnJxwX4uU
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 303
ht-degree: 79%

---

# Google Analytics からデータを移行

Customer Journey Analytics を初めて使用する場合、組織が Google Analytics などの別の Analytics プラットフォームに既存のデータを持っている可能性があります。 これらの包括的な手順に従って、そのデータを Adobe Experience Platform に移動し、Customer Journey Analytics でレポートを表示できるようにします。

ワークフローは、履歴データと現在のデータ収集の両方に対して提供されます。 組織のデータニーズに応じて、これらのワークフローのいずれかまたは両方に従うことができます。

## Google Analytics から Adobe Experience Platform に履歴データを取り込む

履歴（バックフィル）データの取り込みには、Google からのデータのエクスポートと、そのデータの Adobe Experience Platform へのインポートが含まれます。 [Adobe Experience Platform での Google Analytics データの取り込み](backfill.md)を参照してください。

履歴データをPlatformに正常に取り込んだら、[現在のデータのストリーミングを設定](streaming.md)するか、[接続を作成](/help/connections/create-connection.md)することによってCustomer Journey Analyticsでバックフィルされたデータのレポートをすぐに開始できます。

## Adobe Experience Platform に対する既存の Google Analytics 実装の設定 {#configure}

現在の（ストリーミング）データの取り込みには、Adobe Experience Platform Edge Networkにデータを送信し、そのデータをAdobe Experience Platformに転送する必要があります。 [Adobe Experience Platform でのストリーミング Google Analytics データの設定](streaming.md)を参照してください。

## Customer Journey Analyticsでの接続とデータビューの設定

履歴データの取り込みや Adobe Experience Platform へのデータ収集の設定に成功したら、[接続を作成](/help/connections/create-connection.md)して、Customer Journey Analytics がそのデータを参照できるようにします。

接続を使用して、Analysis Workspace で使用する 1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成します。

## レポートの作成

データビュー内でディメンションと指標を設定したら、Analysis Workspace を使用して必要なレポートを生成できます。 [Customer Journey Analytics での Google Analytics データに関するレポート](report.md)を参照してください。
