---
title: Customer Journey Analytics を使い始める
description: Customer Journey Analytics を実装するのに必要な前提条件およびワークフローについて把握します。
exl-id: cab218c0-009c-4669-9dfb-f8872a7f066b
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 366fc232fad278f6a6448d68cda6d0e1f05718f3
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 58%

---

# Customer Journey Analytics を使い始める

Customer Journey Analytics を実装するには、次のワークフローに従う必要があります。初期タスクの中には、Adobe Experience Platform で実行されるものと、Customer Journey Analytics で実行されるものがあります。

## 前提条件

Customer Journey Analytics を利用できる人物は次のとおりです。

* [Adobe Experience Platform](https://www.adobe.com/jp/experience-platform.html) 用にプロビジョニングされている
* Customer Journey Analytics SKU を購入している。

## ワークフロー

| タスク | 詳細 |
| --- | --- |
| **手順 1:Adobe AnalyticsからCustomer Journey Analyticsに移行する場合：移行パスを選択し、データをAdobe Experience Platformに送信します** | Adobe AnalyticsからCustomer Journey Analyticsへの移行に使用できるパスは様々です。 考えられる移行パスにはそれぞれ独自のメリットとデメリットがあり、ある組織に適したパスが別の組織には意味を持たない場合があります。 <p>Adobe AnalyticsからCustomer Journey Analyticsへの移行を開始するには、以下を参照してください [Customer Journey Analyticsへの移行の概要](/help/getting-started/cja-migration/cja-migration-getstarted.md). <!-- [Utilizing Adobe Analytics report suite data in Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md) --> </p> |
| **手順 2：他のデータを Adobe Experience Platform に取り込む** | この手順は、Adobe Experience Platform で実行され、いくつかのサブ手順が必要となります。<ul><li>**手順 2a：データスキーマの準備**：[Adobe Experience Data Model（XDM）](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用して顧客体験データを標準化し、顧客体験管理の[スキーマを定義](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=ja)します。</li><li>**手順 2b：スキーマに基づいたデータセットの作成**：Platform 内のデータは、メールデータセット、CRM データセット、POS データセット、Adobe Analytics データセットなどのデータセットで構成されます。各データセットは、データのスキーマとバッチで構成されます。[Experience Platform でデータセットを作成](https://experienceleague.adobe.com/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/create-datasets.html?lang=ja)できます。</li><li>**手順 2c：Experience Platform へのデータの取り込み**：いくつかのオプションがあります。</li></ul> |
| **手順 3：プラットフォームデータセットと Customer Journey Analytics 間の接続の作成** | 接続を使用すれば、Adobe Experience Platform のデータセットをワークスペースに統合できます。Experience Platform データセットに関するレポートを作成するには、まず Experience Platform とワークスペースのデータセット間で接続を確立する必要があります。<br>詳しくは、[接続の作成または編集](/help/connections/create-connection.md)を参照してください。 |
| **手順 4：データビューの作成** | データ表示は、データの「フィルタリングされた」表示です。同じ接続に対して異なるデータビューを作成し、訪問のタイムアウト、アトリビューションなどに関する設定を変えることができます。1 つのデータセットに対して複数のデータビューを作成できます。<br>[データビューの作成](/help/data-views/create-dataview.md)を参照してください。 |
| **手順 5：レポート API の使用状況の移植**</br> Adobe Analyticsからの移行時にのみ適用されます | Customer Journey Analyticsレポート API は同じ形式ですが、異なるエンドポイントを使用しています。 レポート API の使用状況をAdobe Analytics レポート API からCustomer Journey Analyticsレポート API に移植します。 |
| **手順 6：データフィードとData Warehouseのユースケースの説明**</br> Adobe Analyticsからの移行時にのみ適用されます | Adobe Analyticsで使用していたデータフィードとData Warehouse機能を最適にレプリケートするために、Customer Journey Analyticsで使用可能な書き出しオプションの使用方法を決定します。 <!-- link to docs Rob is creating --> |
| **手順 7：プロジェクトとコンポーネントを移行する**</br> Adobe Analyticsからの移行時にのみ適用されます | Adobe Analyticsのコンポーネント移行領域を使用すると、プロジェクトとその関連コンポーネントをAdobe AnalyticsからCustomer Journey Analyticsに移行できます。<p>移行プロセスには、次が含まれます。</p><ul><li>Customer Journey Analytics で Adobe Analytics プロジェクトを再作成する。</li><li>Adobe Analytics レポートスイートのディメンションと指標を、Customer Journey Analytics データビューのディメンションと指標へマッピングする。</li></ul><p>移行を開始する前に、まず[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行する準備をします](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration.html?lang=ja)。</p><p>必要な準備をすべて整えたら、[コンポーネントとプロジェクトを Adobe Analytics から Customer Journey Analytics に移行](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/component-migration/component-migration.html?lang=ja)できます。</p> |
| **手順 8：ユーザーのオンボーディングの計画** | Adobe Analyticsと同様、Analysis WorkspaceはCustomer Journey Analyticsの主要なユーザーフェイシングツールです。 ただし、Customer Journey AnalyticsでAnalysis Workspaceを使用する際には、注意が必要ないくつかの重要な違いがあります。<p>Customer Journey AnalyticsにおけるAnalysis Workspaceの主な違いを理解できるように、ユーザーに十分な時間（3 ～ 6 か月）を与える必要があります。</p><p>Adobe AnalyticsとCustomer Journey Analyticsの主な違いについては、次を参照してください。 [Adobe Analytics ユーザー向けユーザーガイド](/help/getting-started/aa-to-cja-user.md).</p> |
| **手順 9：ワークスペースでのクロスチャネルデータのレポート** | 接続とデータビューを作成した後、Analysis Workspace の機能と柔軟性を使用して、取得したデータを分析します。<br>[基本分析の実行](/help/analysis-workspace/perform-basic-analysis.md)および[詳細分析の実行](/help/analysis-workspace/perform-adv-analysis.md)を参照してください。 |

## クイックスタートガイド

[データ取り込み](../data-ingestion/data-ingestion.md)の節では、上記のワークフローに関するクイックスタートガイドを提供しています。これらのクイックスタートガイドでは、Adobe Experience Platform で様々なソース（Adobe Analytics など）のデータを取り込んで Customer Journey Analytics で使用する方法について説明しています。
