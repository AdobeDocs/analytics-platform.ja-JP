---
title: アドホックデータの取り込みと使用
description: Customer Journey Analyticsでアドホックを取得して使用する方法
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '1540'
ht-degree: 28%

---


# アドホックデータの取り込みと使用

このクイックスタートガイドでは、アドホックデータをAdobe Experience Platformに取り込んでCustomer Journey Analyticsで使用する方法について説明します。

これには、次の手順を実行する必要があります。

- Experience Platformで **CSV ファイルを使用してデータセットを作成** し、収集するデータのモデル（スキーマ）と、データ（データセット）を収集する場所を定義します。

- Experience Platformで **ソースコネクタを使用** して、設定したデータセットにデータを取り込みます。

- Customer Journey Analytics で、**接続を設定**&#x200B;します。この接続には、（少なくとも）Adobe Experience Platform データセットを含める必要があります。

- Customer Journey Analytics で&#x200B;**データ表示を設定**&#x200B;し、Analysis Workspace で使用する指標とディメンションを定義します。

- Customer Journey Analytics で&#x200B;**プロジェクトを設定**&#x200B;して、レポートとビジュアライゼーションを作成します。



>[!NOTE]
>
>このクイックスタートガイドは、を使用してでアドホックデータをAdobe Experience Platformに取り込み、Customer Journey Analyticsで使用する方法を説明する簡単なガイドです。 参照する際には、追加情報を調べることを強くお勧めします。


## CSV ファイルを使用したデータセットの作成

このクイックスタートでは、ルックアップデータを表し、以下に示すものに類似した情報を含む CSV ファイルを使用します。

| _id | tracking_code | ad_group | campaign_name |
| ---: | :---          | :---        | :---          |
| 1 | abc123 | abc-adgroup | 123 Campaign |
| 2 | def123 | def-adgroup | 123 Campaign |
| 3 | ghi123 | ghi-adgroup | 123 Campaign |
| 4 | abc456 | abc-adgroup | 456 キャンペーン |
| 5 | def456 | def-adgroup | 456 キャンペーン |

>[!NOTE]
>
>レコードベース（ルックアップ、プロファイル）のデータには、アドホックデータセットとスキーマを使用します。 アドホックデータセットとスキーマはあまり適していないので、時系列（イベント、概要）データには考慮しないでください。

アドホックデータ用の XDM スキーマを作成する必要はありません。 Adobe Experience Platformは、CSV ファイルのデータに基づいて以下を行うワークフローをサポートしています。

1. CSV ファイルの列に準拠するアドホックスキーマを作成します。
1. CSV ファイルのデータを含むアドホックスキーマに基づいてデータセットを作成します。

ワークフローを開始するには：

1. Adobe Experience Platform UI の左パネルの「**[!UICONTROL ワークフロー]**」をクリックします。
1. ![DataAdd](/help/assets/icons/DataAdd.svg)**[!UICONTROL CSV ファイルからデータセットを作成]** を選択します。
1. 右側のパネルから **[!UICONTROL ローンチ]** を選択します。
1. **[!UICONTROL ワークフロー]**/**[!UICONTROL CSV ファイルからデータセットを作成]** ウィザードで、次の操作を行います。
   1. **[!UICONTROL データセットを設定]** 手順で、次の操作を行います。
      1. データセットの **[!UICONTROL 名前]** を入力します。 例：`Sample Data From CSV`。
      1. オプションで **[!UICONTROL 説明]** を追加します。 例：`Sample data from a CSV file`。
      1. 1 つ以上のオプションの **[!UICONTROL タグ]** を追加するか、1 つ以上の既存の **[!UICONTROL タグ]** を選択します。

         ![ アドホックデータセットの設定設定 ](assets/adhoc-dataset-configure.png)

      1. 「**[!UICONTROL 次へ]**」を選択します。
   1. **[!UICONTROL データを追加]** 手順で、次の操作を行います。
      1. **[!UICONTROL ファイルを選択]** を選択して、コンピューターまたはネットワークから CSV ファイルを選択します。 または、コンピューターまたはネットワーク上の場所からファイルを **[!UICONTROL ファイルをドラッグ&amp;ドロップ]** にドラッグ&amp;ドロップします。 ファイルがアップロードされ **[!UICONTROL サンプルデータ]** が表示されます。
      1. 環境設定に従って、**[!UICONTROL エラー診断]** と **[!UICONTROL 部分取り込みを有効にする]** を有効または無効にします。 **[!UICONTROL 部分取り込みを有効にする]** 場合、**[!UICONTROL エラーしきい値 %]** を定義できます。

         ![ アドホックデータセットへのデータの追加 ](assets/adhoc-dataset-adddata.png)

      1. 「**[!UICONTROL 完了]**」を選択します。

データが準備され、アップロードされます。 データが正常にアップロードされると、Adobe Experience Platform UI の **[!UICONTROL データセット]** にリダイレクトされます。<br/> ステータスが **[!UICONTROL StatusOrange]**&#x200B;**[!UICONTROL Processing]** の ![CSV からのサンプルデータ ](/help/assets/icons/StatusOrange.svg) データセットの **[!UICONTROL データセットアクティビティ]** が表示されます。

![ アドホックデータのデータセットアクティビティ ](assets/datasets-dataset-activity.png)

アドホックデータを検査するには：

1. Adobe Experience Platform UI の左パネルの「**[!UICONTROL データセット]**」をクリックします。
1. **[!UICONTROL データセット]** の「**[!UICONTROL 参照]**」タブを選択します。 データセットがリストに表示されます。
1. **[!UICONTROL スキーマ]** 列からスキーマの名前を選択します。 例：**[!UICONTROL CSV からのサンプルデータ…]**。

   ![ アドホックデータセットのスキーマを選択 ](assets/adhoc-schema-selection.png)

1. ポップアップで、「**[!UICONTROL スキーマ名]**」を選択します。 例：**[!UICONTROL CSV からのサンプルデータ – アドホックスキーマ - XXXXXXXXXX]**。 **[!UICONTROL スキーマ]**/**[!UICONTROL CSV からのサンプルデータ – アドホックスキーマ - XXXXXXXXXX]** インターフェイスにリダイレクトされます。

**[!UICONTROL スキーマ]**/**[!UICONTROL CSV からのサンプルデータ – アドホックスキーマ - XXXXXXXXXX]** インターフェイスで、

- **[!UICONTROL スキーマ]**/**[!UICONTROL CSV からのサンプルデータ – アドホックスキーマ - XXXXXXXXXX]** の下にある最上位のテナント名オブジェクトを選択して、オブジェクト内のフィールドを表示します。 オブジェクト内のフィールドは、CSV ファイルの構造を表します。 アドホックデータのアップロードに基づいて、スキーマが自動的に作成されます。

  ![ アドホックスキーマ ](dataset/../assets/adhoc-schema.png)



## 接続の設定

Customer Journey AnalyticsでAdobe Experience Platform データセットを使用するには、ワークフローから生成されたアドホックデータを含む接続を作成します。

接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。これらのデータセットに関するレポートを作成するには、まずAdobe Experience PlatformとWorkspaceのデータセット間で接続を確立する必要があります。

接続を作成するには：

1. Customer Journey Analytics UI で、必要に応じて **[!UICONTROL データ管理]** から「**[!UICONTROL 接続]**」を選択します。

1. 「**[!UICONTROL 新しい接続を作成]**」を選択します。

1. **[!UICONTROL 名称未設定の接続]**&#x200B;画面で、次の手順を実行します。

   1. 「**[!UICONTROL 接続設定]**」で接続に名前を付けて説明します。

   1. **[!UICONTROL データ設定]**&#x200B;の&#x200B;**[!UICONTROL サンドボックス]**&#x200B;リストから適切なサンドボックスを選択し、**[!UICONTROL 毎日のイベントの平均数]**&#x200B;リストから日次イベントの数を選択します。

      ![接続設定](./assets/cja-connections-1.png)

   1. 「**[!UICONTROL データセットを追加]**」を選択します。

1. 「**[!UICONTROL データセットを追加]**」の「**[!UICONTROL データセットを選択]**」手順で、次の操作を行います。

   1. 前に作成したデータセット（例：**[!UICONTROL CSV からのサンプルデータ]**、および接続に含める他のデータセット）を選択します。

      ![データセットを追加](./assets/cja-connections-adhoc-2.png)

   1. 「**[!UICONTROL 次へ]**」を選択します。

1. 「**[!UICONTROL データセットを追加]**」の「**[!UICONTROL データセット設定]**」手順で、次の操作を行います。

   アドホックデータセットの場合：

   1. アドホックデータセットのタイプを選択します。 例：**[!UICONTROL Lookup]**。
   1. アドホックスキーマで定義された使用可能なキーから **[!UICONTROL キー]** を選択します。
   1. 接続の一部として追加したイベントデータセットから **[!UICONTROL 一致するキー]** を選択します。
   1. **[!UICONTROL データソースタイプ]**&#x200B;リストから正しいデータソースを選択します。「**[!UICONTROL その他]**」を指定している場合は、データソースの説明を追加します。

   1. 必要に応じて&#x200B;**[!UICONTROL すべての新しいデータを読み込み]**&#x200B;および&#x200B;**[!UICONTROL データセットの既存データのバックフィル]**&#x200B;を選択します。

      ![データセットの設定](./assets/cja-connections-3-adhoc.png)

   1. 「**[!UICONTROL データセットを追加]**」を選択します。

   1. 「**[!UICONTROL 保存]**」を選択します。

アドホックデータセットで使用できる設定について詳しくは、[ アドホックデータセット設定 ](/help/connections/create-connection.md#adhoc-dataset) を参照してください。

>[!IMPORTANT]
>
>時系列データにアドホックデータセットとスキーマを使用しないことを一般的に推奨する上で、時系列データには **CSV からのデータセットを作成** ワークフローを使用 **[!UICONTROL ない]** でください。 アドホックスキーマを生成するワークフローでは、すべてのフィールドを文字列型に定義しますが、後で変更することはできません。 時系列ベースのデータセット（イベントまたは概要）を接続に追加する場合、このタイプのデータセットには、DateTime タイプのフィールドが少なくとも 1 つ定義されている必要があります。 <br/> アドホック時系列データを使用する必要がある場合は、[API を使用してアドホックスキーマを作成 ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/ad-hoc#token_type=bearer&expires_in=43197438) してから、[ スキーマからデータセットを作成 ](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/user-guide#schema) ワークフローを使用することを検討する必要があります。


[ 接続 ](/help/connections/overview.md) を作成したら、[ データセットの選択と組み合わせ ](/help/connections/combined-dataset.md)、[ 接続のデータセットのステータスとデータ取り込みのステータスの確認 ](/help/connections/manage-connections.md) など、様々な管理タスクを実行できます。

## データ表示の設定

データ表示は、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。Analysis Workspace で使用可能なすべてのディメンションと指標、およびこれらのディメンションと指標からデータを取得する列を指定します。データ表示は、Analysis Workspace でレポートの準備を行う際に定義します。

データ表示を作成するには：

1. Customer Journey Analytics UI で、必要に応じて **[!UICONTROL データ管理]** から「**[!UICONTROL データビュー]**」を選択します。

1. 「**[!UICONTROL 新しいデータ表示を作成]**」を選択します。

1. **[!UICONTROL 設定]**&#x200B;手順で、次の操作を行います。

   1. [ 接続 ](#set-up-a-connection) リストから **[!UICONTROL 接続]** を選択します。

   1. 接続に名前を付け、（オプションで）説明します。

      ![データ表示の設定](./assets/cja-dataview-1.png)

   1. 「**[!UICONTROL 保存して続行]**」を選択します。

1. **[!UICONTROL コンポーネント]**&#x200B;手順で、次の操作を行います。

   1. **[!UICONTROL 指標]** または **[!UICONTROL ディメンション]** コンポーネントボックスに含めるアドホックスキーマフィールドや標準コンポーネントを追加します。
   1. 必要に応じて、[ 派生フィールド ](/help/data-views/derived-fields/derived-fields.md) を使用して、デフォルトの文字列タイプおよび形式から別のタイプまたは形式にアドホックフィールドを変更します。

   1. 「**[!UICONTROL 保存して続行]**」を選択します。

1. **[!UICONTROL 設定]**&#x200B;手順で、次の操作を行います。

   設定をそのままにし、「**[!UICONTROL 保存して終了]**」を選択します。

データビューの作成および編集方法について詳しくは、[ データビューの概要 ](../data-views/data-views.md) を参照してください。 および、データビューで使用できるコンポーネントと、セグメントとセッションの設定の使用方法について説明します。


## プロジェクトの設定

Analysis Workspaceは、分析をすばやく構築し、データに基づいてインサイトを共有できる、柔軟なブラウザーツールです。 ワークスペースプロジェクトでは、データコンポーネント、テーブル、およびビジュアライゼーションを組み合わせて、分析を作成し、組織内の任意のユーザーと共有できます。

プロジェクトを作成するには：

1. Customer Journey Analytics UI で、上部メニューの「**[!UICONTROL プロジェクト]**」をクリックします。

1. 左側のナビゲーションの「**[!UICONTROL プロジェクト]**」を選択します。

1. 「**[!UICONTROL プロジェクトを作成]**」を選択します。

1. 「**[!UICONTROL 空のプロジェクト]**」を選択します。

1. リストから [ データビュー ](#set-up-a-data-view) を選択します。

1. 最初のレポートを作成するには、[!UICONTROL &#x200B; パネル &#x200B;] の [!UICONTROL &#x200B; フリーフォームテーブル &#x200B;] でディメンションと指標のドラッグ&amp;ドロップを開始します。 アドホックデータに基づいてこれらの指標やディメンションを含めます。

コンポーネント、ビジュアライゼーション、パネルを使用してプロジェクトを作成し、分析を構築する方法について詳しくは、[Analysis Workspace の概要](../analysis-workspace/home.md)を参照してください。

>[!SUCCESS]
>
>すべての手順が完了しました。まず、収集するアドホックデータ（CSV ファイル）を定義します。 ワークフローを使用して、その CSV ファイルからアドホックデータセットとスキーマを作成しました。 取り込んだアドホックデータと他のデータを使用するように、Customer Journey Analyticsで接続を定義しました。 データ表示の定義では、使用するディメンションと指標を指定でき、最後に、最初のプロジェクトを作成し、データを視覚化および分析します。
