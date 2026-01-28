---
title: Customer Journey Analytics のアクセス制御
description: Customer Journey Analyticsにアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 22%

---

# アクセス制御

Customer Journey Analyticsには、製品管理者ロール、製品プロファイル管理者ロール、ユーザーレベルアクセスの 3 つのアクセスレベルまたは 3 つのロールがあります。 このトピックでは、これらの役割について詳しく説明します。

さらに、Workspaceのキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## 役割ベースのアクセス制御

役割に基づくアクセス制御レベルには、次のものがあります。

### 製品管理者の役割

製品管理者の役割が割り当てられたユーザーには、Customer Journey Analytics内のほとんどのタスクを実行するために必要な権限がデフォルトで付与されます。 ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. [Admin Console](https://adminconsole.adobe.com/enterprise/) に移動します。

1. [!UICONTROL **Customer Journey Analytics**] / [!UICONTROL **管理者**] タブ / [!UICONTROL **管理者を追加**] を選択します。

   追加したユーザーには [&#x200B; 製品管理者のデフォルトの権限 &#x200B;](#product-admin-default-permissions) が付与されます。 必要に応じて、これらのユーザーに [&#x200B; 追加の権限 &#x200B;](#product-admin-additional-permissions) を付与することもできます。

#### 製品管理者のデフォルトの権限

製品管理者には、Customer Journey Analytics内のほとんどのタスクを実行する権限があります。

製品管理者には、次のタスクを実行するために必要な権限がデフォルトで付与されます。

* 他のユーザーが作成したプロジェクト、セグメント、計算指標、オーディエンス、注釈、セグメントの更新および削除
* Workspace プロジェクトをすべてのユーザーと共有する
* [&#x200B; レポートアクティビティマネージャー &#x200B;](/help/reporting-activity-manager/reporting-activity-overview.md) でレポートアクティビティを管理
* Analysis Workspaceからの [&#x200B; 完全なテーブルを書き出し &#x200B;](/help/analysis-workspace/export/export-cloud.md)

#### 製品管理者の追加の権限

**Admin Console&rbrace; で** Customer Journey Analytics製品プロファイル [&#x200B; 製品管理者として追加される以外に、Customer Journey Analytics内の次のタスクを実行するには &#x200B;](https://adminconsole.adobe.com/enterprise/) 追加の権限が必要です。

* [&#x200B; データビュー &#x200B;](/help/data-views/data-views.md) を作成、更新、削除します。
* [&#x200B; 接続 &#x200B;](/help/connections/overview.md) を作成、更新、削除

  このタスクを実行するには、ユーザーが次の権限を提供する **Experience Platform製品プロファイル** に属している必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL サンドボックス] | [!UICONTROL &#x200B; 少なくとも 1 つ &#x200B;] | 接続に関連するサンドボックスへのアクセス。 |
  | [!UICONTROL データモデリング] | [!UICONTROL スキーマの表示] | スキーマおよび関連リソースへの読み取り専用アクセス |
  | [!UICONTROL データモデリング] | [!UICONTROL スキーマの管理] | 各スキーマと関連リソースへの読み取り、作成、編集および削除アクセス |
  | [!UICONTROL データ管理] | [!UICONTROL データセットの表示] | データセットおよびスキーマへの読み取り専用アクセス |
  | [!UICONTROL ID 管理] | [!UICONTROL ID 名前空間の表示] | ID 名前空間への読み取り専用アクセス |

  Experience Platformの権限について詳しくは、[&#x200B; 製品プロファイルの権限の管理 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions) を参照してください。


* Journey OptimizerがJourney Optimizer Connections が存在するCustomer Journey Analyticsと統合されている場合は、接続にアクセスするためのジャーニー権限も追加する必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーイベント、データソース、アクションの表示 &#x200B;] | ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーイベント、データソース、アクションの管理 &#x200B;] | イベント、ソース、アクションの読み取り、作成、編集、削除。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーの表示 &#x200B;] | ジャーニーへの読み取り専用アクセス。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーの管理 &#x200B;] | ジャーニーの読み取り、作成、編集、削除。 |

* [&#x200B; 宛先 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets) へのデータセットの書き出し

  このタスクを実行するには、ユーザーが次の権限を提供する **Experience Platform製品プロファイル** に属している必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL 宛先] | [!UICONTROL 宛先の管理] | 宛先接続および宛先アカウントの読み取り、作成および削除へのアクセス。 |
  | [!UICONTROL 宛先] | [!UICONTROL 宛先のアクティブ化] | ユーザーが既存の宛先に対してセグメントをアクティブ化できるようにします。 アクティブ化ワークフローのマッピングステップを有効にします。また、この権限の場合は、宛先に対してデータをアクティブ化するユーザーに宛先の表示権限を付与する必要があります。 |

  Experience Platformの権限について詳しくは、[&#x200B; 製品プロファイルの権限の管理 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions) を参照してください。

* [BI 拡張機能の使用 &#x200B;](../data-views/bi-extension.md)

  ユーザーが BI 拡張機能を使用する場合、製品管理者

   * ユーザーのExperience Platform権限に、クエリの管理およびクエリサービス統合の管理オプションを備えたクエリサービスリソースを持つロールが含まれていることを確認する必要があります。 Experience Platformの権限について詳しくは、[&#x200B; 製品プロファイルの権限の管理 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions) を参照してください。

     | カテゴリ | 権限 | 説明 |
     |---|---|---|
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリの管理] | Platform データの構造化 SQL クエリの読み取り、作成、編集、および削除へのアクセス。 |
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリサービス統合の管理] | クエリサービスアクセスの有効期限が切れていない資格情報を作成、更新、削除するためのアクセス。 |

   * 次のユーザーに対する適切なCustomer Journey Analytics権限を確認する必要があります。
      * 関連するデータビューにアクセスする権限。 [!UICONTROL &#x200B; ユーザーレベルアクセス &#x200B;] の [&#x200B; データビュー &#x200B;](#user-level-access) を参照してください。
      * Customer Journey Analytics BI 拡張機能にアクセスする権限。 [!UICONTROL &#x200B; ユーザーレベルアクセス &#x200B;] の [&#x200B; データ表示ツール &#x200B;](#user-level-access) を参照してください。

### 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。製品管理者は、製品プロファイルを作成し、製品プロファイル管理者を割り当てて、1 つ以上の製品プロファイルを管理できます。 製品プロファイル管理者は、次の操作を実行できます。

* 割り当てられた製品プロファイルを管理します。 ユーザーやユーザーグループの追加や削除など、製品プロファイルの権限の変更。

* Customer Journey Analyticsで、割り当てられた製品プロファイルの一部であるデータビューを編集します。 製品プロファイル管理者が、新しいデータビューを作成できない。

### ユーザーレベルのアクセス

次の表に、関連するユーザーに設定できる様々なCustomer Journey Analytics機能の主なアクセス権限の概要を示します。 製品プロファイルを通じて、様々なレベルのユーザーアクセスを管理できます。 製品プロファイルは、多数の権限を組み合わせたものであり、個別のユーザーやユーザーグループに割り当てることができます。

**[!UICONTROL 権限]** タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。

![Admin Console 権限](assets/permissions.png)

| カテゴリ | 権限 | 説明 |
| --- | --- | ---|
| [!UICONTROL データビュー] | *データビュー名* | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL Analysis Workspace アクセス] | ユーザーに [Analysis Workspace](/help/analysis-workspace/home.md) へのアクセスを許可します。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL &#x200B; ガイド付き分析へのアクセス &#x200B;] | ユーザーを [&#x200B; ガイド付き分析 &#x200B;](/help/guided-analysis/overview.md) にアクセスさせる。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 計算指標の作成] | ユーザーが [&#x200B; 計算指標 &#x200B;](/help/components/calc-metrics/calc-metr-overview.md) を作成できるようにする ユーザーは、作成した計算指標または共有された計算指標に対してのみ、タグ付け、共有、削除、名前変更、承認、未承認の操作を行うことができます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL セグメントの作成] | ユーザーが [&#x200B; セグメント &#x200B;](/help/components/segments/seg-overview.md) を作成できるようにする ユーザーは、作成したセグメントまたは共有されたセグメントにのみ、タグ付け、共有、削除、名前変更、承認または承認解除を行うことができます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL Labs のアクセス] | ユーザーがCustomer Journey Analyticsの「[Labs](/help/labs/labs.md)」タブにアクセスできるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 注釈の作成] | ユーザーが [&#x200B; 注釈 &#x200B;](/help/components/annotations/overview.md) を作成できるようにする ユーザーは、作成した注釈または共有された注釈にのみ、タグ付け、共有、削除および名前変更を行えます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL オーディエンスの表示] | ユーザーが [&#x200B; オーディエンス &#x200B;](/help/components/audiences/audiences-overview.md) を表示できるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL オーディエンスの作成] | ユーザーが [&#x200B; オーディエンス &#x200B;](/help/components/audiences/audiences-overview.md) を作成できるようにする Adobe Experience Platformに [&#x200B; セグメントの管理 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home) が必要です。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL &#x200B; データstorytelling] | ユーザーが [Workspace プロジェクトに基づいてスライドプレゼンテーションを作成 &#x200B;](/help/analysis-workspace/curate-share/generate-slides.md) できるようにします。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 監査ログへのアクセス] | [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) と監査ログ UI に対して権限チェックを実施します。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL &#x200B; 任意のユーザーとプロジェクトリンクを共有 &#x200B;] | ユーザーが [&#x200B; 任意のユーザーとプロジェクトを共有 &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) できるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 予測] | ユーザーがAnalysis Workspaceの [&#x200B; 予測機能 &#x200B;](../analysis-workspace/c-forecast/forecasting.md) アクセスできるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL AI アシスタント：製品に関する知識 &#x200B;] | ユーザーが [AI アシスタント &#x200B;](../ai-assistant.md) にアクセスして、製品に関する知識を得ることができるようにします。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL インテリジェントキャプション] | ユーザーが [&#x200B; インテリジェントキャプション &#x200B;](/help/analysis-workspace/visualizations/intelligent-captions.md) にアクセスできるようにする |
| [!UICONTROL &#x200B; データ表示ツール &#x200B;] | [!UICONTROL &#x200B; テーブル全体のエクスポート &#x200B;] | ユーザー [&#x200B; 完全なテーブルをクラウドに書き出す &#x200B;](/help/analysis-workspace/export/export-cloud.md) を許可します。 |
| [!UICONTROL &#x200B; データ表示ツール &#x200B;] | [!UICONTROL CJA BI 拡張機能 &#x200B;] | ユーザーが [BI 拡張機能 &#x200B;](../data-views/bi-extension.md) を使用できるようにする |

{style="table-layout:auto"}

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションがどのようにデータビューに結び付いているかについて詳しくは、[プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md)を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは [&#x200B; データビュー &#x200B;](/help/data-views/data-views.md) で変更できるので、Customer Journey Analyticsで変更される可能性があります。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

製品プロファイル管理アクセス権を、会社が勤務するサードパーティのチームリードに付与できます。 この管理者は、会社のチームのユーザーをこの製品プロファイルに追加できます。 この製品プロファイル管理者は、特定のデータビューへのアクセス権を付与し、サードパーティ内の他のユーザーをこの製品プロファイルに追加できます。 製品プロファイル管理者は、サードパーティチームの要件に合わせてデータビューを変更できます。

### 行レベルのアクセス制御

ユーザーに 1 日からのデータへのアクセス権のみを付与したい。 アクセスを特定の行に制限する方法を次に示します。

1. 特定のデータビューの [!UICONTROL &#x200B; 設定 &#x200B;] でセグメントを作成します。ここで [!UICONTROL &#x200B; 日 &#x200B;] は、データアクセスを付与する日付と等しくなります。 詳しくは [&#x200B; データビューの作成 &#x200B;](/help/data-views/create-dataview.md#settings-filters) を参照してください。
1. データビューを保存します。これにより、基になる接続のデータセットのデータ部分にセグメントが適用されます。 セグメント定義に適合しない行はデータビューから自動的に除外され、このデータビューを使用する際にAnalysis Workspaceで使用できなくなります。
1. Admin Consoleで新しい [&#x200B; 製品プロファイル &#x200B;](#product-profile-admin-role) を作成し、製品プロファイルにユーザーを追加して、この特定のデータビューのみを製品プロファイルに含めます。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。 管理者は、データビューで [&#x200B; 含める/除外する機能 &#x200B;](/help/data-views/component-settings/include-exclude-values.md) または [&#x200B; 値のバケット化 &#x200B;](../data-views/component-settings/value-bucketing.md) コンポーネント設定を使用して、データビューから特定のディメンション値を除外または集計できます。

例えば、データセットの個々の患者データを含むコンポーネントから、データビューで *高血圧* と呼ばれる指標を作成します。 値のバケット化を使用して、バケット化された値へのアクセスのみを提供し、データのユーザーが個々の患者データを表示しないようにします。
