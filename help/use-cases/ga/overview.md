---
title: Google Analytics から Customer Journey Analytics へのデータ移行
description: Google Analytics から Adobe Experience Platform にデータを移動する方法と Customer Journey Analytics でレポートを表示する方法に関する包括的なワークフローについて説明します。
source-git-commit: 7c195453490499cc42e7d5b2f2d111e2654f918c
workflow-type: ht
source-wordcount: '304'
ht-degree: 100%

---

# Google Analytics から Customer Journey Analytics へのデータ移行

Customer Journey Analytics を初めて使用する場合、組織が Google Analytics などの別の Analytics プラットフォームに既存のデータを持っている可能性があります。これらの包括的な手順に従って、そのデータを Adobe Experience Platform に移動し、Customer Journey Analytics でレポートを表示できるようにします。

ワークフローは、履歴データと現在のデータ収集の両方に対して提供されます。組織のデータニーズに応じて、これらのワークフローのいずれかまたは両方に従うことができます。

## Google Analytics から Adobe Experience Platform に履歴データを取り込む

履歴（バックフィル）データの取り込みには、Google からのデータのエクスポートと、そのデータの Adobe Experience Platform へのインポートが含まれます。[Adobe Experience Platform での Google Analytics データの取り込み](backfill.md)を参照してください。

履歴データを Platform に正常に取り込むと、[現在のデータのストリーミングを設定する](streaming.md)か、[接続を作成する](/help/connections/create-connection.md)ことによって CJA でバックフィルされたデータのレポートをすぐに開始できます。

## Adobe Experience Platform に対する既存の Google Analytics 実装の設定 {#configure}

現在の（ストリーミング）データの取り込みには、Adobe Experience Edge へのデータの送信が含まれ、Adobe Experience Edge はそのデータを Adobe Experience Platform に転送します。[Adobe Experience Platform でのストリーミング Google Analytics データの設定](streaming.md)を参照してください。

## CJA での接続とデータビューの設定

履歴データの取り込みや Adobe Experience Platform へのデータ収集の設定に成功したら、[接続を作成](/help/connections/create-connection.md)して、Customer Journey Analytics がそのデータを参照できるようにします。

接続を使用して、Analysis Workspace で使用する 1 つ以上の[データビュー](/help/data-views/create-dataview.md)を作成します。

## レポートの作成

データビュー内でディメンションと指標を設定したら、Analysis Workspace を使用して必要なレポートを生成できます。[Customer Journey Analytics での Google Analytics データに関するレポート](report.md)を参照してください。
