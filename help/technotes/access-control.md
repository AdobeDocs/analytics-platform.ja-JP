---
title: Customer Journey Analytics のアクセス制御
description: Customer Journey Analyticsにアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: ea699bcacd985d9da1e3895f7770290dc77da537
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 23%

---

# アクセス制御

Customer Journey Analyticsには、製品管理者ロール、製品プロファイル管理者ロール、ユーザーレベルアクセスの 3 つのアクセスレベルまたは 3 つのロールがあります。 このトピックでは、これらの役割について詳しく説明します。

さらに、Workspaceのキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## ロールベースのアクセス制御

次の役割ベースのアクセス制御レベルを使用できます。

### 製品管理者役割

製品管理者の役割が割り当てられたユーザーには、Customer Journey Analytics内のほとんどのタスクを実行するために必要な権限がデフォルトで付与されます。 ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. [Admin Console](https://adminconsole.adobe.com/enterprise/)に移動します。

1. 「 [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **Admins**] タブ > [!UICONTROL **追加 Admin**] を選択します。

   追加したユーザーには [製品管理者のデフォルトの権限](#product-admin-default-permissions)が付与されます。 必要に応じて [追加の権限](#product-admin-additional-permissions) を付与することもできます。

#### 製品管理者のデフォルトの権限

製品管理者には、Customer Journey Analytics 内のほとんどのタスクを実行する権限があります。

製品管理者には、デフォルトで次のタスクを実行するために必要な権限が付与されます。

* 他のユーザーが作成したプロジェクト、セグメント、計算指標、オーディエンス、注釈またはセグメントを更新および削除する
* Workspace プロジェクトをすべてのユーザーと共有する
* [レポートアクティビティマネージャーでレポートアクティビティを管理する](/help/reporting-activity-manager/reporting-activity-overview.md)
* [Analysis Workspaceから](/help/analysis-workspace/export/export-cloud.md) 完全なテーブル書き出し

#### 製品管理者の追加権限

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

  Experience Platform権限について詳しくは、 [製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。


* Journey Optimizer が、Journey Optimizer 接続が存在する Customer Journey Analytics と統合されている場合、接続にアクセスするには、Journeys の権限も追加する必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL ジャーニー] | [!UICONTROL 表示ジャーニーイベント、データソース、アクション] | ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス権。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーイベント、データソース、アクションを管理] | イベント、ソースまたはアクションの読み取り、作成、編集および削除 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーの表示 &#x200B;] | ジャーニーへの読み取り専用アクセス。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーを管理] | ジャーニーの読み取り、作成、編集、削除。 |

* [&#x200B; 宛先 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets) へのデータセットの書き出し

  このタスクを実行するには、ユーザーが次の権限を提供する **Experience Platform製品プロファイル** に属している必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL 宛先] | [!UICONTROL 宛先の管理] | 宛先接続と宛先アカウントの読み取り、作成、削除へのアクセス。 |
  | [!UICONTROL 宛先] | [!UICONTROL 宛先のアクティブ化] | ユーザーが既存の宛先へのセグメントをアクティブ化できるようにします。 アクティブ化ワークフローのマッピングステップを有効にします。また、この権限では、宛先へのデータをアクティブ化するユーザーに表示宛先権限を付与する必要があります。 |

  Experience Platform権限について詳しくは、 [製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

* [BI 拡張機能の使用](../data-views/bi-extension.md)

  ユーザーが BI 拡張機能を使用するには、製品管理者

   * ユーザーのExperience Platformアクセス許可に、[クエリの管理] オプションと [クエリサービスの統合の管理] オプションを持つクエリ サービス リソースを持つ役割が含まれていることを確認する必要があります。 Experience Platform権限について詳しくは、 [製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

     | カテゴリ | 権限 | 説明 |
     |---|---|---|
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリの管理] | Platform データの構造化 SQL クエリの読み取り、作成、編集、および削除へのアクセス。 |
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリサービス統合の管理] | クエリサービスアクセスの有効期限が切れていない資格情報を作成、更新、削除するためのアクセス。 |

   * 次のユーザーに対する適切なCustomer Journey Analytics権限を確認する必要があります。
      * 関連するデータビューにアクセスする権限。 [!UICONTROL ユーザーレベルアクセス]の[データビュー](#user-level-access)を参照してください。
      * Customer Journey Analytics BI 拡張機能にアクセスする権限。 [!UICONTROL ユーザーレベルアクセス]の[データ表示ツール](#user-level-access)を参照してください。

### 製品プロファイル管理者役割

製品プロファイルは、一連の権限です。製品管理者は、製品プロファイルを作成し、製品プロファイル管理者に 1 つ以上の製品プロファイル管理を割り当てることができます。 製品プロファイル管理者は、次の操作を実行できます。

* 割り当てられた製品プロファイルを管理します。 例えば、ユーザーやユーザーグループの追加または削除や、製品プロファイルの権限の変更などを行うことができます。

* Customer Journey Analytics で、割り当てられた製品プロファイルの一部であるデータ ビューを編集します。 製品プロファイル管理者は新しいデータ表示を作成できません。

### ユーザーレベルのアクセス

次の表に、関連するユーザーに対して構成できるさまざまなCustomer Journey Analytics機能の主なアクセス許可の概要を示します。 製品プロファイルを使用して、さまざまなレベルのユーザーアクセス管理できます。 製品プロファイルは、多数の権限を組み合わせたものであり、個別のユーザーやユーザーグループに割り当てることができます。

**[!UICONTROL 権限]** タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。

![Admin Console 権限](assets/permissions.png)

| カテゴリ | 権限 | 説明 |
| --- | --- | ---|
| [!UICONTROL データビュー] | *data 表示 name* | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL Analysis Workspace アクセス] | ユーザーが [Analysis Workspace](/help/analysis-workspace/home.md) にアクセスできるようにします。 |
| [!UICONTROL レポートツール] | [!UICONTROL ガイド付き分析へのアクセス] | ユーザーが [ガイド付き分析](/help/guided-analysis/overview.md)にアクセスできるようにします。 |
| [!UICONTROL レポートツール] | [!UICONTROL 計算指標の作成] | ユーザーが [&#x200B; 計算指標 &#x200B;](/help/components/calc-metrics/calc-metr-overview.md) を作成できるようにする ユーザーは、作成した計算指標または共有された計算指標に対してのみ、タグ付け、共有、削除、名前変更、承認、未承認の操作を行うことができます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL セグメントの作成] | ユーザーが [セグメントを作成できるようにします](/help/components/segments/seg-overview.md)。 ユーザーは、作成したセグメントまたは共有されたセグメントにのみ、タグ付け、共有、削除、名前変更、承認または承認解除を行うことができます。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL Labs のアクセス] | ユーザーがCustomer Journey Analyticsの「[Labs](/help/labs/labs.md)」タブにアクセスできるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 注釈の作成] | ユーザーが [注釈](/help/components/annotations/overview.md)を作成できるようにします。 ユーザーは、自分が作成した注釈またはユーザーと共有している注釈のみタグ、共有、削除および名前変更できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL オーディエンスの表示] | ユーザーが [&#x200B; オーディエンス &#x200B;](/help/components/audiences/audiences-overview.md) を表示できるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL オーディエンスの作成] | ユーザーが [オーディエンス](/help/components/audiences/audiences-overview.md)を作成できるようにします。 Adobe Experience Platform では [セグメントの管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home) が必要です。 |
| [!UICONTROL レポートツール] | [!UICONTROL データストーリーテリング] | ユーザーがワークスペースプロジェクトに基づいてスライドプレゼンテーションを [生成できるようにします。](/help/analysis-workspace/curate-share/generate-slides.md)<p>データストーリーテリングはリリースの限定テスト段階にあり、環境ではまだ利用できない可能性があります。 機能が一般公開されたら、このメモは削除されます。Customer Journey Analytics リリースプロセスについて詳しくは、[Customer Journey Analytics 機能リリース](/help/release-notes/releases.md)を参照してください。</p> |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL 監査ログへのアクセス] | [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) と監査ログ UI に対して権限チェックを実施します。 |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL &#x200B; 任意のユーザーとプロジェクトリンクを共有 &#x200B;] | ユーザーが誰とでもプロジェクトを [共有できるようにします。](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL レポートツール] | [!UICONTROL 予測] | ユーザーがAnalysis Workspaceの [&#x200B; 予測機能 &#x200B;](../analysis-workspace/c-forecast/forecasting.md) アクセスできるようにする |
| [!UICONTROL &#x200B; レポートツール &#x200B;] | [!UICONTROL AI アシスタント: 製品ナレッジ] | ユーザーが [AI アシスタント](../ai-assistant.md) にアクセスして製品ナレッジを確認できるようにします。 |
| [!UICONTROL レポートツール] | [!UICONTROL インテリジェントキャプション] | ユーザーが [インテリジェントキャプション](/help/analysis-workspace/visualizations/intelligent-captions.md)にアクセスできるようにします。 |
| [!UICONTROL データ表示ツール] | [!UICONTROL フルテーブル書き出し] | ユーザーがテーブル全体を クラウド に [エクスポートできるようにします](/help/analysis-workspace/export/export-cloud.md)。 |
| [!UICONTROL データ表示ツール] | [!UICONTROL CJA BI 拡張] | ユーザーが [BI 拡張機能 &#x200B;](../data-views/bi-extension.md) を使用できるようにする |

{style="table-layout:auto"}

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションがどのようにデータビューに結び付いているかについて詳しくは、[プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md)を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは [データビュー](/help/data-views/data-views.md) で変更できるため、Customer Journey Analytics変更される可能性があります。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

製品プロファイル管理アクセス権を、会社が勤務するサードパーティのチームリードに付与できます。 この管理者は、会社のチームのユーザーをこの製品プロファイルに追加できます。 この製品プロファイル管理者は、特定のデータビューへのアクセス権を付与し、サードパーティ内の他のユーザーをこの製品プロファイルに追加できます。 製品プロファイル管理者は、サードパーティチームの要件に合わせてデータ表示を変更できます。

### 行レベルのアクセス制御

1 日のデータへのアクセスをユーザーに許可したい。 アクセスを特定の行に制限する方法を次に示します。

1. 特定のデータ表示の [!UICONTROL 設定] のセグメント作成、 [!UICONTROL 日] は、データ アクセスを許可する日付と等しくなります。 詳しくは [作成 データ表示](/help/data-views/create-dataview.md#settings-filters) を参照してください。
1. データビューを保存します。これにより、基になる接続のデータセットのデータ部分にセグメントが適用されます。 セグメント定義に適合しない行はデータビューから自動的に除外され、このデータビューを使用する際にAnalysis Workspaceで使用できなくなります。
1. Admin Consoleで新しい [&#x200B; 製品プロファイル &#x200B;](#product-profile-admin-role) を作成し、製品プロファイルにユーザーを追加して、この特定のデータビューのみを製品プロファイルに含めます。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。 管理者は、データビューで [&#x200B; 含める/除外する機能 &#x200B;](/help/data-views/component-settings/include-exclude-values.md) または [&#x200B; 値のバケット化 &#x200B;](../data-views/component-settings/value-bucketing.md) コンポーネント設定を使用して、データビューから特定のディメンション値を除外または集計できます。

例えば、データセットの個々の患者データを含むコンポーネントから、データビューで *高血圧* と呼ばれる指標を作成します。 値のバケット化を使用して、バケット化された値へのアクセスのみを提供し、データのユーザーが個々の患者データを表示しないようにします。
