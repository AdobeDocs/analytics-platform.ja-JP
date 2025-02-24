---
title: クロスチャネルジャーニー分析
description: カスタマージャーニー全体を通した顧客とのインタラクションからインサイトを分析および抽出します。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 51%

---

# クロスチャネル分析 {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="接続へのデータセットの追加"
>abstract="Adobe Experience Platformのデータセットにデータを追加したら、そのデータセットをCustomer Journey Analyticsの接続に追加できます。 他のチャネルのデータを追加する場合は、組織が使用するスキーマに準拠していることを確認してください。<br><br> 追加する各データセットには、膨大な作業が必要です。特に、すべてのイベントに一意の ID が存在することと、包括的なデータ構造が組織のカスタムスキーマに準拠していることを確認することに関連する作業が必要です。 このワークフローの確立には、数か月にわたる組織内の多くのチーム間の調整が必要になる場合があります。"

<!-- markdownlint-enable MD034 -->

クロスチャネル分析では、様々な web、モバイル、オフラインのプロパティのデータを統合することで、様々なチャネルをまたいだ顧客の行動を 1 つの統合ビューで把握できます。 例えば、この統合ビューを使用して、デスクトップとモバイルをまたいで顧客のインタラクションを分析し、顧客の行動を把握し、インサイトを抽出してデジタル顧客体験を最適化できます。 また、チャネルをまたいだ顧客インタラクション（例：サポートのやり取りや店頭購入など、デジタルチャネルとオフラインチャネル）を分析して、カスタマージャーニーをより深く理解し、最適化することもできます。

## 実装手順

![ この節で説明する実装ステップのフロー。](../assets/cca-architecture.png)

1. 取り込むデータの [スキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja) します。
1. 取り込むデータの [データセットを作成](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=ja) します。
1. [Experience Platformへのデータの取り込み ](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=ja):
   1. Edge Networkまたは Analytics ソースコネクタを介した web サイトまたはモバイルアプリからのイベントベースのデータ ![ イベント ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg)。
   2. プロファイルデータ ![ プロファイル ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) （CRM システム、コールセンターアプリケーション、ロイヤルティアプリケーションからなど）。
   3. 参照データ ![ 参照 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) （製品名、製品情報システムからのカテゴリなど）。

1. データセット間で共通の名前空間 ID を使用します。 [ ステッチ ](../../stitching/overview.md) を使用して、各行に共通の ID を指定するという点で、イベントベースのデータセット ![ データ更新 ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) を昇格します。 Customer Journey Analytics は、現在、ステッチに Experience Platform プロファイルまたは ID サービスを使用していません。
1. カスタムデータの準備を実行し、時系列データセット間の共通キーが Customer Journey Analytics に取り込まれるようにします。
1. ルックアップデータに、イベントデータのフィールドに結合できるプライマリ ID を指定します。ライセンスの行としてカウントします。
1. プロファイルデータには、イベントデータのプライマリ ID と同じプライマリ ID を設定します。
1. [ 接続を作成 ](../../connections/overview.md)：関連するデータセットをExperience PlatformからCustomer Journey Analyticsに取り込みます。
1. 接続で [データビューを作成](/help/data-views/create-dataview.md) し、ビューに含める特定のディメンションと指標を選択します。アトリビューションと割り当ては、データビューでも設定できます。これらの設定は、レポート時に計算されます。
1. [ プロジェクトを作成 ](/help/analysis-workspace/home.md) して、Analysis Workspace内でダッシュボードとレポートを設定します。

## 注意点

このワークフローを確立する際は、次の点を考慮してください。

* チャネル間でデータを分析するには、すべてのレコードで同じ ID 名前空間が必要です。
* 異なるデータセットを統合する和集合プロセスには、データセット全体で共通のプライマリパーソン／エンティティキーが必要です。
* セカンダリのキーベースの和集合は、現在サポートされていません。
* ステッチプロセスでは、同じ永続 ID を共有するレコードの一時的な ID （認証 ID など）情報に基づいて、行の ID を再入力できます。これにより、異なるレコードを単一のステッチ ID に解決して、デバイスや Cookie レベルではなく、人物レベルで分析できます。
* 同じ XDM フィールドのオブジェクトとアトリビューションは、Customer Journey Analytics 内で 1 つのディメンションに結合されます。様々なデータセットの複数のアトリビューションを同じ Customer Journey Analytics ディメンションに結合するには、データセットが同じ XDM フィールドまたはスキーマを参照する必要があります。

