---
title: Customer Journey Analytics のアクセス制御
description: Customer Journey Analytics でアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
TQID: https://experienceleague.adobe.com/-Zv1B2pvTFAAgwV1uAV6ik65jtKVRBsF-2rc0tCHuUs
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
subfeature_v2:
  - id: a4cd176f-aea0-45b8-80e6-7f1b931e5847
  - id: a67cb189-a535-41f6-afa2-448f39c4759f
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
  - id: bfa38d8a-4e93-4fd8-8cd8-e72c589e3af8
  - id: c38ed341-fab2-46df-9d72-88d8166edebb
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d13dba12-733d-4914-8d92-d643658bbe5d
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e0cfe18a-f68c-495b-bafc-f6bcc0392d6c
  - id: e1471301-a189-438e-8d48-264a8db508a6
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e8abc408-b05c-427f-9e37-f8b033a6b3c3
  - id: f24857a4-4b64-4b25-b237-d43026362144
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b23e006f-0a29-4f1d-8fd0-77aa56f3d12b
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 1661
ht-degree: 95%

---

# アクセス制御

Customer Journey Analytics は、製品管理者の役割、製品プロファイル管理者の役割、ユーザーレベルのアクセスという 3 つのアクセスレベルまたは 3 つの役割によって管理されます。 このトピックでは、これらの役割について詳しく説明します。

さらに、この記事では、Workspace のキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## 役割ベースのアクセス制御

次の役割ベースのアクセス制御レベルが使用可能です。

### 製品管理者の役割

製品管理者の役割が割り当てられたユーザーには、Customer Journey Analytics 内のほとんどのタスクを実行するために必要な権限がデフォルトで付与されます。 ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. [Admin Console](https://adminconsole.adobe.com/enterprise/) に移動します。

1. [!UICONTROL **Customer Journey Analytics**]／[!UICONTROL **管理者**]&#x200B;タブ／[!UICONTROL **管理者を追加**]&#x200B;を選択します。

   追加したユーザーには、[製品管理者のデフォルトの権限](#product-admin-default-permissions)が付与されます。 また、必要に応じて、これらのユーザーに[追加の権限](#product-admin-additional-permissions)を付与することもできます。

#### 製品管理者のデフォルトの権限

製品管理者には、Customer Journey Analytics 内のほとんどのタスクを実行する権限があります。

製品管理者には、次のタスクを実行するために必要な権限がデフォルトで付与されます。

* 他のユーザーが作成したプロジェクト、セグメント、計算指標、オーディエンス、注釈、セグメントの更新と削除を行う
* Workspace プロジェクトをすべてのユーザーと共有する
* [レポートアクティビティマネージャー](/help/reporting-activity-manager/reporting-activity-overview.md)でレポートアクティビティを管理する
* Analysis Workspace から[完全なテーブルを書き出す](/help/analysis-workspace/export/export-cloud.md)

#### 製品管理者の追加の権限

[Admin Console](https://adminconsole.adobe.com/enterprise/) の **Customer Journey Analytics 製品プロファイル**&#x200B;に製品管理者として追加されることに加えて、Customer Journey Analytics 内で次のタスクを完了するには追加の権限が必要です。

* [データビュー](/help/data-views/data-views.md)を作成、更新、削除する。
* [接続](/help/connections/overview.md)を作成、更新、削除する

  このタスクを実行するには、ユーザーは次の権限を付与する **Experience Platform 製品プロファイル**&#x200B;に属している必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL サンドボックス] | [!UICONTROL 少なくとも 1 つ] | 接続に関連するサンドボックスへのアクセス。 |
  | [!UICONTROL データモデリング] | [!UICONTROL スキーマの表示] | スキーマおよび関連リソースへの読み取り専用アクセス |
  | [!UICONTROL データモデリング] | [!UICONTROL スキーマの管理] | 各スキーマと関連リソースへの読み取り、作成、編集および削除アクセス |
  | [!UICONTROL データ管理] | [!UICONTROL データセットの表示] | データセットおよびスキーマへの読み取り専用アクセス |
  | [!UICONTROL ID 管理] | [!UICONTROL ID 名前空間の表示] | ID 名前空間への読み取り専用アクセス |

  Experience Platform の権限について詳しくは、[製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。


* Journey OptimizerがJourney Optimizer Connections が存在するCustomer Journey Analyticsと統合されている場合は、接続にアクセスするためのジャーニー権限も追加する必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーイベント、データソース、アクションの表示] | ジャーニーイベント、ジャーニーカスタムアクション、ジャーニーデータソースへの読み取り専用アクセス。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーイベント、データソース、アクションの管理] | イベント、ソース、アクションの読み取り、作成、編集、削除。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーの表示] | ジャーニーへの読み取り専用アクセス。 |
  | [!UICONTROL ジャーニー] | [!UICONTROL ジャーニーの管理] | ジャーニーの読み取り、作成、編集、削除。 |

* [宛先](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/export-datasets)へのデータセットの書き出し

  このタスクを実行するには、ユーザーは次の権限を付与する **Experience Platform 製品プロファイル**&#x200B;に属している必要があります。

  | カテゴリ | 権限 | 説明 |
  |---|---|---|
  | [!UICONTROL 宛先] | [!UICONTROL 宛先の管理] | 宛先接続と宛先アカウントの読み取り、作成および削除へのアクセス。 |
  | [!UICONTROL 宛先] | [!UICONTROL 宛先のアクティブ化] | ユーザーが既存の宛先に対してセグメントをアクティブ化できるようにします。 アクティブ化ワークフローのマッピングステップを有効にします。 また、この権限の場合は、データを宛先に対してアクティブ化するユーザーに宛先の表示権限も付与する必要があります。 |

  Experience Platform の権限について詳しくは、[製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

* [BI 拡張機能](../data-views/bi-extension.md)の使用

  ユーザーが BI 拡張機能を使用する場合、製品管理者は以下を行う必要があります。

   * ユーザーの Experience Platform 権限に、「クエリを管理」オプションと「クエリサービス統合を管理」オプションを含むクエリサービスリソースを持つ役割が含まれていることを確認する必要があります。 Experience Platform の権限について詳しくは、[製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

     | カテゴリ | 権限 | 説明 |
     |---|---|---|
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリの管理] | Platform データの構造化 SQL クエリの読み取り、作成、編集、および削除へのアクセス。 |
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリサービス統合の管理] | クエリサービスアクセスの有効期限が切れていない資格情報を作成、更新、削除するためのアクセス。 |

   * ユーザーに次の適切な Customer Journey Analytics 権限を付与する必要があります。
      * 関連するデータビューにアクセスする権限。 [!UICONTROL ユーザーレベルアクセス]の[データビュー](#user-level-access)を参照してください。
      * Customer Journey Analytics BI 拡張機能にアクセスする権限。 [ユーザーレベルアクセス](#user-level-access)の[!UICONTROL データビューツール]を参照してください。

### 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。 製品管理者は、製品プロファイルを作成し、1 つ以上の製品プロファイルを管理する製品プロファイル管理者を割り当てることができます。 製品プロファイル管理者は、次の操作を実行できます。

* 割り当てられた製品プロファイルを管理する。 ユーザーまたはユーザーグループの追加や削除、製品プロファイルの権限の変更など。

* Customer Journey Analytics で、割り当てられた製品プロファイルの一部であるデータビューを編集する。 製品プロファイル管理者は、新しいデータビューを作成できません。

### ユーザーレベルのアクセス

次の表に、関連するユーザーに対して設定できる様々な Customer Journey Analytics 機能の主なアクセス権限の概要を示します。 製品プロファイルを通じて、様々なレベルのユーザーアクセスを管理できます。 製品プロファイルは、多数の権限を組み合わせ、個々のユーザーやユーザーグループに割り当てることができます。

「**[!UICONTROL 権限]**」タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。

![Admin Console 権限](assets/permissions.png)

| カテゴリ | 権限 | 説明 |
| --- | --- | ---|
| [!UICONTROL データビュー] | *データビュー名* | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。 この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL ガイド付き分析へのアクセス] | ユーザーは[ガイド付き分析](/help/guided-analysis/overview.md)にアクセスできます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 計算指標の作成] | ユーザーは[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を作成できます。 ユーザーは、作成した計算指標または共有された計算指標のみにタグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL セグメントの作成] | ユーザーは[セグメント](/help/components/segments/seg-overview.md)を作成できます。 ユーザーは、作成したセグメントまたは共有されたセグメントのみにタグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL Labs のアクセス] | ユーザーは Customer Journey Analytics の「[ラボ](/help/labs/labs.md)」タブにアクセスできます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 注釈の作成] | ユーザーは[注釈](/help/components/annotations/overview.md)を作成できます。 ユーザーは、作成した注釈または共有されている注釈に対してのみ、タグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL オーディエンスビュー] | ユーザーは[オーディエンス](/help/components/audiences/audiences-overview.md)を表示できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL オーディエンスの作成] | ユーザーは[オーディエンス](/help/components/audiences/audiences-overview.md)を作成できます。 Adobe Experience Platformで[&#x200B; セグメントの管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home)が必要です。 |
| [!UICONTROL レポートツール] | [!UICONTROL データストーリーテリング] | ユーザーは [Workspace プロジェクトに基づいてスライドプレゼンテーションを生成](/help/analysis-workspace/curate-share/generate-slides.md)できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 監査ログへのアクセス] | [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) と今後の監査ログ UI に対する権限チェックを実施します。 |
| [!UICONTROL レポートツール] | [!UICONTROL 任意のユーザーとプロジェクトリンクを共有] | ユーザーは[任意のユーザーとプロジェクトを共有](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/curate-share/share-projects)できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 予測] | ユーザーは Analysis Workspace の[予測](../analysis-workspace/c-forecast/forecasting.md)機能にアクセスできます |
| [!UICONTROL レポートツール] | [!UICONTROL AI アシスタント：製品知識] | ユーザーは [AI アシスタント](../ai-assistant.md)にアクセスして、製品知識を得ることができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL Data Insights Agent] | AIを活用したデータインサイト用の[Data Insights Agent](../data-analysis-ai.md)にアクセスできます。 |
| [!UICONTROL レポートツール] | [!UICONTROL インテリジェントキャプション] | ユーザーは[インテリジェントキャプション](/help/analysis-workspace/visualizations/intelligent-captions.md)にアクセスできます |
| [!UICONTROL レポートツール] | [!UICONTROL MCP アクセス &#x200B;] | [Customer Journey Analytics MCP サーバー](https://developer.adobe.com/analytics-mcp/docs/cja/)へのアクセスを許可します。 |
| [!UICONTROL データビューツール] | [!UICONTROL 完全なテーブルの書き出し] | ユーザーは[完全なテーブルをクラウドに書き出す](/help/analysis-workspace/export/export-cloud.md)ことができます。 |
| [!UICONTROL データビューツール] | [!UICONTROL CJA BI 拡張機能] | ユーザーは [BI 拡張機能](../data-views/bi-extension.md)を使用できます。 |

{style="table-layout:auto"}

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。 特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。 Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションがどのようにデータビューに結び付いているかについて詳しくは、[プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md)を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。 指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、Customer Journey Analytics で変更される可能性があります。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

会社が提携しているサードパーティのチームリーダーに、製品プロファイル管理アクセス権を付与できます。 この管理者は、会社のチームのユーザーをこの製品プロファイルに追加できます。 この製品プロファイル管理者は、特定のデータビューへのアクセス権を付与し、サードパーティ内の他のユーザーをこの製品プロファイルに追加できます。 製品プロファイル管理者は、サードパーティチームの要件に合わせてデータビューを変更できます。

### 行レベルのアクセス制御

ユーザーに 1 日に限りデータへのアクセス権を付与するとします。 アクセスを特定の行に制限する方法を次に示します。

1. 特定のデータビューの[!UICONTROL 設定]でセグメントを作成します。ここで、[!UICONTROL 日]はデータアクセス権を付与する日付となります。 詳しくは、[データビューの作成](/help/data-views/create-dataview.md#settings-filters)を参照してください。
1. データビューを保存します。これにより、基になる接続のデータセットのデータ部分にセグメントが適用されます。 セグメント定義に適合しない行はデータビューから自動的に除外され、このデータビューを使用する際に Analysis Workspace で使用できなくなります。
1. Admin Console で新しい[製品プロファイル](#product-profile-admin-role)を作成し、製品プロファイルにユーザーを追加して、この特定のデータビューのみを製品プロファイルに含めます。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。 管理者は、データビューの[含める／除外機能](/help/data-views/component-settings/include-exclude-values.md)または[値のバケット化](../data-views/component-settings/value-bucketing.md)コンポーネント設定を使用して、データビューから特定のディメンション値を除外または集計できます。

例えば、データセットの個々の患者データを含むコンポーネントから、データビューで「*高血圧*」と呼ばれる指標を作成します。 値のバケット化を使用すると、バケット化された値へのアクセス権のみが付与されるので、そのデータのユーザーには個々の患者のデータは表示されません。
