---
title: クロスチャネルジャーニー分析
description: カスタマージャーニー全体を通した顧客とのインタラクションからインサイトを分析および抽出します。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: ht
source-wordcount: '581'
ht-degree: 100%

---

# クロスチャネル分析 {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="接続へのデータセットの追加"
>abstract="Adobe Experience Platform のデータセットにデータを追加したら、そのデータセットを Customer Journey Analytics の接続に追加できます。他のチャネルからデータを追加する際は、組織で使用しているスキーマに準拠している必要があります。<br><br>追加するデータセットごとに、特にすべてのイベントに一意の ID が存在することと、包括的なデータ構造が組織のカスタムスキーマに準拠していることを確認することなど、膨大な作業が必要になります。このワークフローを確立するには、数か月にわたって組織内の多くのチーム間で調整が必要になる場合があります。"

<!-- markdownlint-enable MD034 -->

クロスチャネル分析では、様々な web、モバイル、オフラインのプロパティからのデータを統合することで、様々なチャネルをまたいだ顧客の行動を 1 つの統合ビューで把握できます。例えば、この統合ビューを使用して、デスクトップとモバイルをまたいで顧客のインタラクションを分析し、顧客の行動を把握し、インサイトを抽出してデジタル顧客体験を最適化できます。 また、チャネルをまたいだ顧客インタラクション（例：サポートのやり取りや店頭購入など、デジタルチャネルとオフラインチャネル）を分析して、カスタマージャーニーをより深く理解し、最適化することもできます。

## 実装手順

![この節で説明する実装手順のフロー。](../assets/cca-architecture.png)

1. 取り込むデータの [スキーマを作成](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja) します。
1. 取り込むデータの [データセットを作成](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=ja) します。
1. [Experience Platform へのデータの取り込み](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=ja)：
   1. Edge Network または Analytics ソースコネクタを介した web サイトまたはモバイルアプリからのイベントベースのデータの![イベント](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg)。
   2. プロファイルデータの![プロファイル](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg)（例：CRM システム、コールセンターアプリケーション、ロイヤルティアプリケーションから）。
   3. ルックアップデータの![ルックアップ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)（例：製品情報システムからの製品名、カテゴリ）。

1. データセットをまたいで共通の名前空間 ID を使用します。[ステッチ](../../stitching/overview.md)を使用すると、各行に共通 ID を指定するという点で、イベントベースのデータセットの![データ更新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg)を向上させることができます。 Customer Journey Analytics は、現在、ステッチに Experience Platform プロファイルまたは ID サービスを使用していません。
1. カスタムデータの準備を実行し、時系列データセット間の共通キーが Customer Journey Analytics に取り込まれるようにします。
1. ルックアップデータに、イベントデータのフィールドに結合できるプライマリ ID を指定します。ライセンスの行としてカウントします。
1. プロファイルデータには、イベントデータのプライマリ ID と同じプライマリ ID を設定します。
1. Experience Platform から Customer Journey Analytics に関連データセットを取り込むには、[接続を作成します](../../connections/overview.md)。
1. 接続で [データビューを作成](/help/data-views/create-dataview.md) し、ビューに含める特定のディメンションと指標を選択します。アトリビューションと割り当ては、データビューでも設定できます。これらの設定は、レポート時に計算されます。
1. Analysis Workspace 内でダッシュボードとレポートを設定するには、[プロジェクトを作成します](/help/analysis-workspace/home.md)。

## 注意点

このワークフローを確立する際は、次の点を考慮してください。

* チャネル間でデータを分析するには、すべてのレコードで同じ ID 名前空間が必要です。
* 異なるデータセットを統合する和集合プロセスには、データセット全体で共通のプライマリパーソン／エンティティキーが必要です。
* セカンダリのキーベースの和集合は、現在サポートされていません。
* ステッチプロセスでは、同じ永続 ID を共有するレコードからの一時 ID（認証 ID など）情報に基づいて、行内の ID をキー更新できます。これにより、デバイスレベルや cookie レベルではなく、ユーザーレベルでの分析用に、単一のステッチ ID に対する異なるレコードを解決できます。
* 同じ XDM フィールドのオブジェクトとアトリビューションは、Customer Journey Analytics 内で 1 つのディメンションに結合されます。様々なデータセットの複数のアトリビューションを同じ Customer Journey Analytics ディメンションに結合するには、データセットが同じ XDM フィールドまたはスキーマを参照する必要があります。

