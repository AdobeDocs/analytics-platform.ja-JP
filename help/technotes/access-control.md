---
title: Customer Journey Analytics のアクセス制御
description: Customer Journey Analyticsにアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 1a470345a6a2748b992263c3ad25e4cd7d3daa9e
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 42%

---

# Customer Journey Analytics のアクセス制御

Customer Journey Analyticsは、3 つのアクセスレベル（3 つの役割）によって管理されます。製品管理者の役割、製品プロファイル管理者の役割、ユーザーレベルのアクセスです。 このトピックでは、これらの役割について詳しく説明します。

さらに、Workspaceのキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## 製品管理者の役割

製品管理者の役割が割り当てられたユーザーには、デフォルトでCustomer Journey Analytics内のほとんどのタスクを実行するために必要な権限が付与されます。 ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. [Admin Console](https://adminconsole.adobe.com/enterprise/) に移動します。

1. [!UICONTROL **Customer Journey Analytics**] / [!UICONTROL **管理者**] タブ / [!UICONTROL **管理者を追加**] を選択します。

   追加したユーザーには [ 製品管理者のデフォルトの権限 ](#product-admin-default-permissions) が付与されます。 必要に応じて、これらのユーザーに [ 追加の権限 ](#product-admin-additional-permissions) を付与することもできます。

### 製品管理者のデフォルトの権限

Customer Journey Analytics管理者には、製品内のほとんどのタスクを実行する権限があります。

製品管理者には、デフォルトで次のタスクを実行するために必要な権限が付与されます。

* データビューの作成、更新、削除
* 他のユーザーが作成したプロジェクト、フィルター、計算指標、オーディエンス、注釈、フィルターの更新と削除を行います。
* Workspace プロジェクトをすべてのユーザーと共有する
* [ レポートアクティビティマネージャー ](/help/reporting-activity-manager/reporting-activity-overview.md) でレポートアクティビティを管理
* Analysis Workspaceからの [ 完全なテーブルを書き出し ](/help/analysis-workspace/export/export-cloud.md)

### 製品管理者の追加権限

Customer Journey Analytics管理者として **製品プロファイル**[ 製品 ](https://adminconsole.adobe.com/enterprise/) に追加されるだけでなく、Customer Journey Analytics内で次のタスクを実行するために別のAdmin Consoleが必要となります。

* データの作成、更新、削除 [ 接続 ](/help/connections/overview.md)

  このタスクを実行するには、次のアクセス許可を提供する **Experience Platform製品プロファイル** に属している必要があります：
   * データモデリング：ビュースキーマ、スキーマの管理
   * データ管理：ビューデータセット，データセットの管理
   * データ取り込み：ソースの管理
   * ID 名前空間の表示

     Experience Platform の権限について詳しくは、[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home)を参照してください。

* クラウドへのデータセットの書き出し [ 宛先 ](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html?lang=ja)

  このタスクを実行するには、次のExperience Platform権限が必要です。

   * 宛先の管理
   * 宛先のアクティブ化

     宛先のExperience Platformの権限について詳しくは、[ 宛先の概要 ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/home) を参照してください。

* [BI 拡張機能の使用 ](../data-views/bi-extension.md)

  BI 拡張機能を使用するユーザー向けに、製品管理者

   * ユーザーのExperience Platform権限に、クエリの管理およびクエリサービス統合の管理オプションを備えたクエリサービスリソースを持つロールが含まれていることを確認する必要があります。 [ 製品プロファイルの権限の管理 ](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/permissions) を参照してください。
   * 次のユーザーに対する適切なCustomer Journey Analytics権限を確認する必要があります。
      * 関連するデータビューにアクセスする権限。 [Admin ConsoleのCustomer Journey Analytics権限 ](#customer-journey-analytics-permissions-in-admin-console) のデータビューを参照してください。
      * cja BI 拡張機能にアクセスする権限。 [Admin ConsoleのCustomer Journey Analytics権限 ](#customer-journey-analytics-permissions-in-admin-console) のデータビューツールを参照してください。

## 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。製品プロファイル管理者が実行できる操作

* 個々の製品プロファイルを作成および管理します。 例えば、新規ユーザーの追加や、ユーザーグループとそれらに関連する製品プロファイルの管理などです。

* Customer Journey Analyticsで、管理する製品プロファイルの一部であるデータビューを編集します。 新しいデータビューを作成することはできません。

## ユーザーレベルのアクセス

次のマトリックスに、製品管理者以外のユーザーとCustomer Journey AnalyticsCustomer Journey Analytics管理者の様々な製品機能に対する主なアクセス権の概要を示します。 これらの権限を理解すると、組織内での自分の役割と責務に基づいてCustomer Journey Analyticsを効果的に移動および使用できます。

| 製品機能 | 製品管理者以外（ユーザー） | 製品管理者 |
| --- | --- | --- |
| **データビュー** | 表示/更新/作成/削除できない | 作成/更新/削除可能 |
| **接続** | 表示/更新/作成/削除できない | 作成/更新/削除可能 |
| **フィルター** | 作成可能 | 作成可能 |
| **プロジェクト** | 作成可能 | 作成/更新/削除可能 |
| **オーディエンス** | Admin Consoleで特別な権限を持つを作成できる | 作成可能 |
| **計算指標** | Admin Consoleで特別な権限を持つを作成できる | 作成可能 |

{style="table-layout:auto"}

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、フィルター、日付範囲）の制限方法、キュレーションがどのようにデータビューに結び付いているかについて詳しくは、[ プロジェクトのキュレーション ](/help/analysis-workspace/curate-share/curate.md) を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは [ データビュー ](/help/data-views/data-views.md) で変更できるので、Customer Journey Analyticsが変化する可能性があります。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

会社が連携するサードパーティには、製品プロファイル管理者になれるチームリードがいます。この管理者は、会社のチームのユーザーをこの製品プロファイルに追加できます。 この管理者は、特定のデータビューへのアクセス権を付与し、この製品プロファイルに他のユーザーを追加できます。また、チームのニーズに合わせて制御可能なデータビューを変更することもできます。

### 行レベルのアクセス制御

例えば、ユーザーに 1 日に限りデータへのアクセス権を付与するとします。アクセスを特定の行に制限する方法を次に示します。

1. Customer Journey Analyticsでフィルターを作成します。ここでの **[!UICONTROL 日]** は、データアクセスを付与する日付となります。
1. [!UICONTROL データビュー]／[!UICONTROL 設定]をクリックし、そのフィルターをデータビューに追加します。
1. データビューを保存し、フィルターをデータセットに自動適用します。フィルター定義に適合しない行は、編集されたデータビューから自動的に除外されるようになります。
1. Admin Console で新しい製品プロファイルを作成し、ユーザーを追加して、このデータビューへのアクセスを制限します。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。管理者は、データビューで[機能の包含／除外](/help/data-views/component-settings/include-exclude-values.md)を使用して、例えば、特定のディメンション値をデータビューから除外します。

医療関連の例を次に示します。例えば、このデータを含むデータセットから、データビューで「高血圧」と呼ばれる指標を作成したとします。指標であるということは、この指標の総値を確認できますが、その指標に該当する個々の患者は確認できません。

## Admin ConsoleのCustomer Journey Analytics権限

「**[!UICONTROL 権限]**」タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。Customer Journey Analytics固有の権限を次に示します。

![Admin Console 権限](assets/permissions.png)

| 権限 | 定義 |
| --- | --- |
| **[!UICONTROL データビュー]** | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| **[!UICONTROL レポートツール]**： |   |
| **[!UICONTROL 監査ログへのアクセス]** | この権限は、[API](https://www.adobe.io/cja-apis/docs/endpoints/auditlogs/) と今後の監査ログ UI に対する権限チェックを実施します。 |
| **[!UICONTROL Analysis Workspace アクセス]** | ユーザーがCustomer Journey AnalyticsでAnalysis Workspaceにアクセスできるようにする。 |
| [!UICONTROL **ガイド付き分析へのアクセス**] | ユーザーが [ ガイド付き分析プロジェクト ](/help/guided-analysis/overview.md) を作成できるようにする |
| [!UICONTROL **予測**] | ユーザーがAnalysis Workspaceの予測機能にアクセスできるようにする |
| **[!UICONTROL レポート使用状況の管理]** | ユーザーが会社で実行しているレポートを表示および削除できるようにします。 |
| **[!UICONTROL レポート使用状況のビュー]** | ユーザーが同時レポートリクエストをすべて表示できるようにします。 |
| [!UICONTROL **テーブル全体のエクスポート**] | ユーザー [ 完全なテーブルをクラウドに書き出す ](/help/analysis-workspace/export/export-cloud.md) を許可します。 |
| **[!UICONTROL 計算指標の作成]** | ユーザーが [ 計算指標 ](/help/components/calc-metrics/calc-metr-overview.md) を作成できるようにする |
| **[!UICONTROL フィルターの作成]** | ユーザーが [ フィルター ](/help/components/filters/filters-overview.md) を作成できるようにします。 |
| **[!UICONTROL Labs のアクセス]** | ユーザーがCustomer Journey Analyticsの「[Labs](/help/labs/labs.md)」タブにアクセスできるようにします。 |
| **[!UICONTROL 注釈の作成]** | ユーザーが [ 注釈 ](/help/components/annotations/overview.md) を作成できるようにする |
| **[!UICONTROL オーディエンスの作成]** | ユーザーが [ オーディエンス ](/help/components/audiences/audiences-overview.md) を作成できるようにする |
| **[!UICONTROL オーディエンスの表示]** | ユーザーが [ オーディエンス ](/help/components/audiences/audiences-overview.md) を表示できるようにする |
| [!UICONTROL **任意のユーザーとプロジェクトリンクを共有**] | ユーザーが [ 任意のユーザーとプロジェクトを共有 ](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) できるようにする |
| **[!UICONTROL データ表示ツール]**: |   |
| [!UICONTROL **テーブル全体のエクスポート**] | ユーザー [ 完全なテーブルをクラウドに書き出す ](/help/analysis-workspace/export/export-cloud.md) を許可します。 |
| **[!UICONTROL [!UICONTROL CJA BI 拡張機能]]** | ユーザーが [BI 拡張機能 ](../data-views/bi-extension.md) を使用できるようにする |

{style="table-layout:auto"}
