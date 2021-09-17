---
title: クロスチャネルジャーニー分析
description: カスタマージャーニー全体を通した顧客とのインタラクションからインサイトを分析および抽出します。
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# クロスチャネルジャーニー分析

様々なWeb、モバイル、オフラインのプロパティのデータを統合することで、様々なチャネルにわたる顧客の行動を1つの統合ビューで把握できます。 例えば、この統合ビューを使用して、デスクトップとモバイルをまたいで顧客のインタラクションを分析し、顧客の行動を把握し、インサイトを抽出してデジタル顧客体験を最適化できます。 また、サポートインタラクションや店頭購入などのデジタルチャネルとオフラインチャネルを含むチャネルをまたいで顧客インタラクションを分析し、カスタマージャーニーをより深く理解し、最適化することもできます。

## アーキテクチャ

![クロスチャネルのアーキテクチャ](assets/cross-channel-architecture.svg)

## 実装手順

1. [取得す](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja) るデータのスキーマを作成します。
1. [取り込](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) むデータのデータセットを作成します。
1. [Experience Platform へのデータの取得](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. データセット間で共通の名前空間IDを使用するか、[クロスチャネル分析](/help/connections/cca/overview.md)を使用してユーザーをリンクします。 Customer Journey Analyticsは、現在、ステッチにExperience PlatformプロファイルまたはIDサービスを使用していないことに注意してください。
1. カスタムデータの準備を実行し、時系列データセット間で共通のキーがCustomer Journey Analyticsに取り込まれるようにします。
1. ルックアップデータに、イベントデータのフィールドに結合できるプライマリIDを指定します。 ライセンスの行としてカウントします。
1. プロファイルデータに対しては、イベントデータのプライマリIDと同じプライマリIDを設定します。
1. データ接続を設定して、データをExperience PlatformからCustomer Journey Analyticsに取り込みます。
1. [接続でデータビ](/help/data-views/create-dataview.md) ューを作成し、ビューに含める特定のディメンションと指標を選択します。アトリビューションと割り当ての設定は、データビューでも設定できます。 これらの設定は、レポート時に計算されます。
1. Analysis Workspace内でダッシュボードとレポートを設定するプロジェクトを作成します。

## 注意点

このワークフローを確立する際は、次の点を考慮してください。

* チャネル間でデータを分析するには、すべてのレコードで同じID名前空間が必要です。
* 異なるデータセットを統合する和集合プロセスには、データセット全体で共通のプライマリ個人/エンティティキーが必要です。
* セカンダリのキーベースの和集合は、現在サポートされていません。
* フィールドベースのIDステッチプロセスを使用すると、後続の一時的なIDレコード（認証IDなど）に基づいて行のIDを再入力できます。 これにより、異なる複数のレコードをデバイスやCookieレベルではなく、個人レベルでの分析用に単一のIDに解決できます。
* 同じXDMフィールドのオブジェクトと属性が、Customer Journey Analytics内で1つのディメンションに結合されます。 様々なデータセットの複数の属性を同じCustomer Journey Analyticsディメンションに結合するには、データセットは同じXDMフィールドまたはスキーマを参照する必要があります。
