---
title: データをGoogle AnalyticsからCustomer Journey Analyticsに移行
description: Google AnalyticsからAdobe Experience Platformにデータを移動する方法、およびCustomer Journey Analyticsでのレポートの表示に関する包括的なワークフローについて説明します。
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# データをGoogle AnalyticsからCustomer Journey Analyticsに移行

Customer Journey Analyticsを初めておこなう場合は、組織が別の Analytics プラットフォーム (Google Analyticsなど ) に既にデータを持っている可能性があります。 次の包括的な手順に従って、そのデータをAdobe Experience Platformに移動し、レポートをCustomer Journey Analyticsで表示できます。

ワークフローは、履歴データと現在のデータ収集の両方に対して提供されます。 組織のデータニーズに応じて、これらのワークフローのどちらかまたは両方を実行できます。

## Google Analyticsの履歴データをAdobe Experience Platformに取り込む

履歴（バックフィル）データを取り込むには、Googleからデータをエクスポートし、そのデータをAdobe Experience Platformに読み込みます。 詳しくは、 [Adobe Experience PlatformでのGoogle Analyticsデータの取り込み](backfill.md).

履歴データを Platform に正常に取り込んだら、次のいずれかを実行できます。 [現在のデータのストリーミングの設定](streaming.md)または、CJA でバックフィルしたデータに関するレポートをすぐに開始できます。その際には、次のようにします。 [接続の作成](/help/connections/create-connection.md).

## Adobe Experience Platformの既存のGoogle Analytics実装の設定 {#configure}

現在の（ストリーミング）データを取り込むには、Adobe Experience Edge にデータを送信する必要があります。その後、Adobe Experience Edge はそのデータをAdobe Experience Platformに転送します。 詳しくは、 [Adobe Experience PlatformでのストリーミングGoogle Analyticsデータの設定](streaming.md).

## CJA での接続とデータビューの設定

履歴データの取り込みやAdobe Experience Platformへのデータ収集の設定が完了したら、 [接続の作成](/help/connections/create-connection.md) を使用して、Customer Journey Analyticsがそのデータを参照できるようにします。

接続を使用して 1 つ以上の [データビュー](/help/data-views/create-dataview.md) Analysis Workspaceで使用します。

## レポートの作成

データビュー内でディメンションと指標を設定したら、Analysis Workspaceを使用して目的のレポートを生成できます。 詳しくは、 [Customer Journey AnalyticsのGoogle Analyticsデータのレポート](report.md).
