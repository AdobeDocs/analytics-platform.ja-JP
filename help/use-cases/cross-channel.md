---
title: クロスチャネルジャーニー分析
description: カスタマージャーニー全体を通した顧客とのインタラクションからインサイトを分析および抽出します。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 100%

---

# クロスチャネルジャーニー分析

様々な web、モバイル、オフラインのプロパティのデータを統合することで、様々なチャネルをまたいだ顧客の行動を 1 つの統合ビューで把握できます。 例えば、この統合ビューを使用して、デスクトップとモバイルをまたいで顧客のインタラクションを分析し、顧客の行動を把握し、インサイトを抽出してデジタル顧客体験を最適化できます。 また、チャネルをまたいだ顧客インタラクション（例：サポートのやり取りや店頭購入など、デジタルチャネルとオフラインチャネル）を分析して、カスタマージャーニーをより深く理解し、最適化することもできます。

## アーキテクチャ

![クロスチャネルアーキテクチャ](assets/cross-channel-architecture.svg)

## 実装手順

1. 取り込むデータの [スキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja) します。
1. 取り込むデータの [データセットを作成](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=ja) します。
1. [Experience Platform へのデータの取得](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=ja).
1. データセット間で共通の名前空間 ID を使用するか、 [クロスチャネル分析](/help/connections/cca/overview.md) を使用してユーザーをリンクします。Customer Journey Analytics は、現在、ステッチに Experience Platform プロファイルまたは ID サービスを使用していません。
1. カスタムデータの準備を実行し、時系列データセット間の共通キーが Customer Journey Analytics に取り込まれるようにします。
1. ルックアップデータに、イベントデータのフィールドに結合できるプライマリ ID を指定します。ライセンスの行としてカウントします。
1. プロファイルデータには、イベントデータのプライマリ ID と同じプライマリ ID を設定します。
1. データ接続を設定して、Experience Platform から Customer Journey Analytics にデータを取り込みます。
1. 接続で [データビューを作成](/help/data-views/create-dataview.md) し、ビューに含める特定のディメンションと指標を選択します。アトリビューションと割り当ては、データビューでも設定できます。これらの設定は、レポート時に計算されます。
1. Analysis Workspace 内でダッシュボードとレポートを設定するプロジェクトを作成します。

## 注意点

このワークフローを確立する際は、次の点を考慮してください。

* チャネル間でデータを分析するには、すべてのレコードで同じ ID 名前空間が必要です。
* 異なるデータセットを統合する和集合プロセスには、データセット全体で共通のプライマリパーソン／エンティティキーが必要です。
* セカンダリのキーベースの和集合は、現在サポートされていません。
* フィールドベースの ID ステッチプロセスを使用すると、後続の一時的な ID レコード（認証 ID など）に基づいて行の ID を再入力できます。これにより、複数の異なるレコードを単一の ID に解決し、デバイスや cookie レベルではなく、ユーザーレベルで分析をおこなうことができます。
* 同じ XDM フィールドのオブジェクトとアトリビューションは、Customer Journey Analytics 内で 1 つのディメンションに結合されます。様々なデータセットの複数のアトリビューションを同じ Customer Journey Analytics ディメンションに結合するには、データセットが同じ XDM フィールドまたはスキーマを参照する必要があります。
