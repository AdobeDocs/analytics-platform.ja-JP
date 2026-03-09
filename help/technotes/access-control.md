---
title: Customer Journey Analytics のアクセス制御
description: Customer Journey Analytics でアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '1554'
ht-degree: 96%

---

# アクセス制御

Customer Journey Analytics は、製品管理者の役割、製品プロファイル管理者の役割、ユーザーレベルのアクセスという 3 つのアクセスレベルまたは 3 つの役割によって管理されます。このトピックでは、これらの役割について詳しく説明します。

さらに、この記事では、Workspace のキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## 役割ベースのアクセス制御

次の役割ベースのアクセス制御レベルが使用可能です。

### 製品管理者の役割

製品管理者の役割が割り当てられたユーザーには、Customer Journey Analytics 内のほとんどのタスクを実行するために必要な権限がデフォルトで付与されます。ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. [Admin Console](https://adminconsole.adobe.com/enterprise/) に移動します。

1. [!UICONTROL **Customer Journey Analytics**]／[!UICONTROL **管理者**]&#x200B;タブ／[!UICONTROL **管理者を追加**]&#x200B;を選択します。

   追加したユーザーには、[製品管理者のデフォルトの権限](#product-admin-default-permissions)が付与されます。また、必要に応じて、これらのユーザーに[追加の権限](#product-admin-additional-permissions)を付与することもできます。

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
  | [!UICONTROL 宛先] | [!UICONTROL 宛先のアクティブ化] | ユーザーが既存の宛先に対してセグメントをアクティブ化できるようにします。アクティブ化ワークフローのマッピングステップを有効にします。また、この権限の場合は、データを宛先に対してアクティブ化するユーザーに宛先の表示権限も付与する必要があります。 |

  Experience Platform の権限について詳しくは、[製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

* [BI 拡張機能](../data-views/bi-extension.md)の使用

  ユーザーが BI 拡張機能を使用する場合、製品管理者は以下を行う必要があります。

   * ユーザーの Experience Platform 権限に、「クエリを管理」オプションと「クエリサービス統合を管理」オプションを含むクエリサービスリソースを持つ役割が含まれていることを確認する必要があります。Experience Platform の権限について詳しくは、[製品プロファイルの権限の管理](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/ui/permissions)を参照してください。

     | カテゴリ | 権限 | 説明 |
     |---|---|---|
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリの管理] | Platform データの構造化 SQL クエリの読み取り、作成、編集、および削除へのアクセス。 |
     | [!UICONTROL クエリサービス] | [!UICONTROL クエリサービス統合の管理] | クエリサービスアクセスの有効期限が切れていない資格情報を作成、更新、削除するためのアクセス。 |

   * ユーザーに次の適切な Customer Journey Analytics 権限を付与する必要があります。
      * 関連するデータビューにアクセスする権限。[!UICONTROL ユーザーレベルアクセス]の[データビュー](#user-level-access)を参照してください。
      * Customer Journey Analytics BI 拡張機能にアクセスする権限。[ユーザーレベルアクセス](#user-level-access)の[!UICONTROL データビューツール]を参照してください。

### 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。製品管理者は、製品プロファイルを作成し、1 つ以上の製品プロファイルを管理する製品プロファイル管理者を割り当てることができます。 製品プロファイル管理者は、次の操作を実行できます。

* 割り当てられた製品プロファイルを管理する。 ユーザーまたはユーザーグループの追加や削除、製品プロファイルの権限の変更など。

* Customer Journey Analytics で、割り当てられた製品プロファイルの一部であるデータビューを編集する。製品プロファイル管理者は、新しいデータビューを作成できません。

### ユーザーレベルのアクセス

次の表に、関連するユーザーに対して設定できる様々な Customer Journey Analytics 機能の主なアクセス権限の概要を示します。製品プロファイルを通じて、様々なレベルのユーザーアクセスを管理できます。製品プロファイルは、多数の権限を組み合わせ、個々のユーザーやユーザーグループに割り当てることができます。

「**[!UICONTROL 権限]**」タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。

![Admin Console 権限](assets/permissions.png)

| カテゴリ | 権限 | 説明 |
| --- | --- | ---|
| [!UICONTROL データビュー] | *データビュー名* | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL ガイド付き分析へのアクセス] | ユーザーは[ガイド付き分析](/help/guided-analysis/overview.md)にアクセスできます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 計算指標の作成] | ユーザーは[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を作成できます。ユーザーは、作成した計算指標または共有された計算指標にのみ、タグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL セグメントの作成] | ユーザーは[セグメント](/help/components/segments/seg-overview.md)を作成できます。ユーザーは、作成したセグメントまたは共有されたセグメントにのみ、タグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL Labs のアクセス] | ユーザーは Customer Journey Analytics の「[ラボ](/help/labs/labs.md)」タブにアクセスできます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 注釈の作成] | ユーザーは[注釈](/help/components/annotations/overview.md)を作成できます。ユーザーは、作成した注釈または共有されている注釈に対してのみ、タグ付け、共有、削除、名前変更を行うことができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL オーディエンスビュー] | ユーザーは[オーディエンス](/help/components/audiences/audiences-overview.md)を表示できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL オーディエンスの作成] | ユーザーが [&#x200B; オーディエンス &#x200B;](/help/components/audiences/audiences-overview.md) を作成できるようにする Adobe Experience Platformに [&#x200B; セグメントの管理 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/access-control/home) が必要です。 |
| [!UICONTROL レポートツール] | [!UICONTROL データストーリーテリング] | ユーザーは [Workspace プロジェクトに基づいてスライドプレゼンテーションを生成](/help/analysis-workspace/curate-share/generate-slides.md)できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 監査ログへのアクセス] | [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) と今後の監査ログ UI に対する権限チェックを実施します。 |
| [!UICONTROL レポートツール] | [!UICONTROL 任意のユーザーとプロジェクトリンクを共有] | ユーザーは[任意のユーザーとプロジェクトを共有](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/curate-share/share-projects)できます。 |
| [!UICONTROL レポートツール] | [!UICONTROL 予測] | ユーザーは Analysis Workspace の[予測](../analysis-workspace/c-forecast/forecasting.md)機能にアクセスできます |
| [!UICONTROL レポートツール] | [!UICONTROL AI アシスタント：製品知識] | ユーザーは [AI アシスタント](../ai-assistant.md)にアクセスして、製品知識を得ることができます。 |
| [!UICONTROL レポートツール] | [!UICONTROL Data Insights Agent] | ユーザーが [Data Insights Agent](../data-analysis-ai.md) にアクセスして、AI によるデータインサイトを得られるようにします。 |
| [!UICONTROL レポートツール] | [!UICONTROL インテリジェントキャプション] | ユーザーは[インテリジェントキャプション](/help/analysis-workspace/visualizations/intelligent-captions.md)にアクセスできます |
| [!UICONTROL データビューツール] | [!UICONTROL 完全なテーブルの書き出し] | ユーザーは[完全なテーブルをクラウドに書き出す](/help/analysis-workspace/export/export-cloud.md)ことができます。 |
| [!UICONTROL データビューツール] | [!UICONTROL CJA BI 拡張機能] | ユーザーは [BI 拡張機能](../data-views/bi-extension.md)を使用できます。 |

{style="table-layout:auto"}

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションがどのようにデータビューに結び付いているかについて詳しくは、[プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md)を参照してください。

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。指標とディメンションは[データビュー](/help/data-views/data-views.md)で変更できるので、Customer Journey Analytics で変更される可能性があります。これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

会社が提携しているサードパーティのチームリーダーに、製品プロファイル管理アクセス権を付与できます。この管理者は、会社のチームのユーザーをこの製品プロファイルに追加できます。この製品プロファイル管理者は、特定のデータビューへのアクセス権を付与し、サードパーティ内の他のユーザーをこの製品プロファイルに追加できます。製品プロファイル管理者は、サードパーティチームの要件に合わせてデータビューを変更できます。

### 行レベルのアクセス制御

ユーザーに 1 日に限りデータへのアクセス権を付与するとします。アクセスを特定の行に制限する方法を次に示します。

1. 特定のデータビューの[!UICONTROL 設定]でセグメントを作成します。ここで、[!UICONTROL 日]はデータアクセス権を付与する日付となります。詳しくは、[データビューの作成](/help/data-views/create-dataview.md#settings-filters)を参照してください。
1. データビューを保存します。これにより、基になる接続のデータセットのデータ部分にセグメントが適用されます。セグメント定義に適合しない行はデータビューから自動的に除外され、このデータビューを使用する際に Analysis Workspace で使用できなくなります。
1. Admin Console で新しい[製品プロファイル](#product-profile-admin-role)を作成し、製品プロファイルにユーザーを追加して、この特定のデータビューのみを製品プロファイルに含めます。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。管理者は、データビューの[含める／除外機能](/help/data-views/component-settings/include-exclude-values.md)または[値のバケット化](../data-views/component-settings/value-bucketing.md)コンポーネント設定を使用して、データビューから特定のディメンション値を除外または集計できます。

例えば、データセットの個々の患者データを含むコンポーネントから、データビューで「*高血圧*」と呼ばれる指標を作成します。値のバケット化を使用すると、バケット化された値へのアクセス権のみが付与されるので、そのデータのユーザーには個々の患者のデータは表示されません。
