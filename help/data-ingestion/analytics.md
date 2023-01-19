---
title: 従来のAdobe Analyticsからのデータの取り込みと使用
description: 従来のAdobe Analyticsからデータを取り込む方法を説明する
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: 5cbfa922-6d6e-453a-9558-abfcfb80449d
source-git-commit: 3331f41590509ef38cb67802335414ca3de5ff94
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 11%

---

# 従来のAdobe Analyticsからのデータの取り込みと使用

このクイックスタートガイドでは、Adobe Analyticsが収集したデータをCustomer Journey Analyticsで使用する方法について説明します。

>[!PREREQUISITES]
>
>ドキュメントに記載された実装方法のいずれかを使用して、Adobe Analyticsがライセンスを取得し、1 つ以上の Web サイトにデプロイしている。
>
>- [Analytics Edge を使用した Experience Platform の実装](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/overview.html?lang=ja)
>
>- [Adobe Analytics拡張機能を使用した Analytics の実装](https://experienceleague.adobe.com/docs/analytics/implementation/launch/overview.html?lang=ja)
>
>- [JavaScript を使用した Analytics の実装](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en)


これをおこなうには、次の操作が必要です。

- **Adobe Analyticsソースコネクタの設定** Adobe Experience Platform これにより、現在のAdobe AnalyticsデータをAdobe Experience Platformのデータセットに取り込みます。

- **接続の設定** Customer Journey Analytics この接続には、少なくともAdobe Experience Platformデータセットを含める必要があります。

- **データビューの設定** 「 」Customer Journey Analyticsで、Analysis Workspaceで使用する指標とディメンションを定義します。

- **プロジェクトの設定** ( レポートおよびビジュアライゼーションを作成するためのCustomer Journey Analytics)


>[!NOTE]
>
>これは、Adobe Analyticsソースコネクタを使用してデータを取り込み、Customer Journey Analyticsで使用する方法に関するシンプルなガイドです。 を参照する際に、追加情報を調べることを強くお勧めします。


## Adobe Analyticsソースコネクタの設定

Adobe Analyticsソースコネクタを使用すると、Adobe AnalyticsレポートスイートデータをAdobe Experience Platformに取り込むことができます。

Adobe Analyticsソースコネクタを作成するには：

1. Platform UI で、「 **[!UICONTROL ソース]**（左側のレールから）

2. 選択 **[!UICONTROL Adobe]** リストから [!UICONTROL カテゴリ].

3. 選択 **[!UICONTROL 設定]** または **[!UICONTROL データを追加]** Adobe Analyticsタイル内。

   ![ソース](./assets/sources-overview.png)

4. 選択 **[!UICONTROL レポートスイート]**. レポートスイートのリストから、使用するレポートスイートを選択します。

   ![レポートスイート](./assets/report-suites.png)

   「**[!UICONTROL 次へ]**」を選択します。

5. 選択 **[!UICONTROL デフォルトのスキーマ]** を [!UICONTROL ターゲットスキーマ]. Adobe Experience Platformは、選択したAdobe Analyticsレポートスイートのすべての標準フィールドをマッピングするために、スキーマと対応するデータセットを自動的に作成します。

   ![デフォルトのスキーマ](./assets/default-schema.png)

   「**[!UICONTROL 次へ]**」を選択します。

6. データフローに名前を付け、（オプションで）説明を入力します。

   ![データフローの詳細](./assets/dataflow-detail.png)

   「**[!UICONTROL 次へ]**」を選択します。

7. 接続を確認し、「 」を選択します。 **[!UICONTROL 完了]**.

   ![レビュー](./assets/review.png)


接続が作成されると、データフローが自動的に作成され、最大 13 か月分の履歴データの取り込みなど、レポートスイートのAdobe Analyticsデータがデータセットに入力されます。

初回の取り込みが完了すると、Adobe AnalyticsレポートスイートのデータがCustomer Journey Analyticsで使用できる状態になります。

詳しくは、 [UI でのAdobe Analyticsソース接続の作成](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=ja) を参照してください。


## 接続の設定

Adobe Experience PlatformデータをCustomer Journey Analyticsで使用するには、スキーマ、データセット、ワークフローの設定によって生成されたデータを含む接続を作成します。

接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。これらのデータセットに関するレポートを作成するには、まずAdobe Experience Platformと Workspace のデータセット間で接続を確立する必要があります。

接続を作成するには：

1. Customer Journey AnalyticsUI で、 **[!UICONTROL 接続]** 」をクリックします。

2. 選択 **[!UICONTROL 新しい接続を作成]**.

3. 内 [!UICONTROL 無題の接続] 画面：

   で接続に名前を付け、説明します。 [!UICONTROL 接続設定].

   次の中から適切なサンドボックスを選択します。 [!UICONTROL サンドボックス] リスト [!UICONTROL データ設定] 「 」で、「 [!UICONTROL 毎日のイベントの平均数] リスト。

   ![接続設定](./assets/cja-connections-1.png)

   選択 **[!UICONTROL データセットを追加]**.

   内 [!UICONTROL データセットを選択] 足を踏み入れる [!UICONTROL データセットを追加]:

   - Adobe Analyticsソースコネクタによって自動的に作成されたデータセットと、接続に含める他のデータセットを選択します。

      ![データセットを追加](./assets/cja-connections-2a.png)

   - 「**[!UICONTROL 次へ]**」を選択します。
   内 [!UICONTROL データセット設定] 足を踏み入れる [!UICONTROL データセットを追加]:

   - 各データセットに対して、次の操作を実行します。

      - を選択します。 [!UICONTROL 人物 ID] Adobe Experience Platformのデータセットスキーマで定義された使用可能な id から。

      - 次の中から正しいデータソースを選択します： [!UICONTROL データソースタイプ] リスト。 次を指定した場合： **[!UICONTROL その他]**&#x200B;次に、データソースの説明を追加します。

      - 設定 **[!UICONTROL すべての新しいデータをインポート]** および **[!UICONTROL データセットの既存データのバックフィル]** 好みに応じて。

      ![データセットの設定](./assets/cja-connections-3.png)

   - 選択 **[!UICONTROL データセットを追加]**.
   「**[!UICONTROL 保存]**」を選択します。

詳しくは、 [接続の概要](../connections/overview.md) 接続を作成および管理する方法、およびデータセットを選択して組み合わせる方法に関する詳細。

## データビューの設定

データビューは、Customer Journey Analytics に特有のコンテナで、接続からデータを解釈する方法を決定できます。Analysis Workspace で使用可能なすべてのディメンションと指標、およびこれらのディメンションと指標からデータを取得する列を指定します。データビューは、Analysis Workspace でのレポート作成の準備の際に定義します。

データビューを作成するには：

1. Customer Journey AnalyticsUI で、 **[!UICONTROL データビュー]** 」をクリックします。

2. 選択 **[!UICONTROL 新しいデータビューを作成]**.

3. 内 [!UICONTROL 設定] 手順：

   接続を [!UICONTROL 接続] リスト。

   接続に名前を付け、（オプションで）説明します。

   ![データビューの設定](./assets/cja-dataview-1.png)

   選択 **[!UICONTROL 保存して続行]**.

4. 内 [!UICONTROL コンポーネント] 手順：

   に含めるスキーマフィールドや標準コンポーネントを追加します。 [!UICONTROL 指標] または [!UICONTROL Dimension] コンポーネントボックス

   ![データビューコンポーネント](./assets/cja-dataview-2.png)

   選択 **[!UICONTROL 保存して続行]**.

5. 内 [!UICONTROL 設定] 手順：

   ![データビュー設定](./assets/cja-dataview-3.png)

   設定をそのままにし、「 」を選択します。 **[!UICONTROL 保存して終了]**.

詳しくは、 [データビューの概要](../data-views/data-views.md) データビューの作成および編集方法、データビューで使用できるコンポーネント、フィルターおよびセッションの設定の使用方法に関する詳細。


## プロジェクトの設定

Analysis Workspaceは、データに基づいて分析をすばやく構築し、インサイトを共有できる、柔軟なブラウザーツールです。 Workspace プロジェクトを使用して、データのコンポーネント、テーブルおよびビジュアライゼーションを組み合わせ、分析を作成し、組織内の任意のユーザーと共有します。

プロジェクトを作成するには：

1. Customer Journey AnalyticsUI で、 **[!UICONTROL プロジェクト]** 」をクリックします。

2. 選択 **[!UICONTROL プロジェクト]** をクリックします。

3. 選択 **[!UICONTROL プロジェクトを作成]**.

   ![Workspace プロジェクト](./assets/cja-projects-1.png)

   選択 **[!UICONTROL 空のプロジェクト]**.

   ![Workspace — 空のプロジェクト](./assets/cja-projects-2.png)

4. リストからデータビューを選択します。

   ![Workspace データビューを選択](./assets/cja-projects-3.png).

5. ディメンションと指標のドラッグ&amp;ドロップを [!UICONTROL フリーフォームテーブル] 内 [!UICONTROL パネル] をクリックして最初のレポートを作成します。 例えば、 `Program Points Balance` および `Page View` 指標として `email` をディメンションとして使用すると、Web サイトを訪問し、ロイヤルティポイントを収集するロイヤルティプログラムの一部であるプロファイルの概要をすばやく把握できます。

   ![Workspace — 最初のレポート](./assets/cja-projects-5.png)

詳しくは、 [Analysis Workspaceの概要](../analysis-workspace/home.md) プロジェクトの作成方法、およびコンポーネント、ビジュアライゼーション、パネルを使用した分析の構築方法に関する詳細。


>[!SUCCESS]
>
>すべての手順が完了しました。 まず、Adobe Analyticsデータソースコネクタを設定し、レポートスイート用にそのコネクタを設定すると、Adobe AnalyticsデータがAdobe Experience Platformに自動的にアップロードされます。 取り込んだAdobe Analyticsデータや他のデータを利用するためにCustomer Journey Analyticsで接続を定義しました。 データビュー定義では、使用するディメンションと指標を指定でき、最後に、最初のプロジェクトを作成し、データを視覚化および分析します。

