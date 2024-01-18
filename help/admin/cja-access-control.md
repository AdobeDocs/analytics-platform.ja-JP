---
title: Customer Journey Analytics のアクセス制御
description: アクセス制御を実装する方法について説明します。Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 24d8d03867cf9619bbee1dd647b2a2a57a36492b
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 63%

---

# Customer Journey Analytics のアクセス制御

Customer Journey Analyticsは、3 つのアクセスレベルまたは 3 つのロール（製品管理者ロール、製品プロファイル管理者ロール、ユーザーレベルアクセス）で管理されます。 このトピックでは、これらの役割について詳しく説明します。

さらに、Workspace のキュレーションや行レベル、値レベルのアクセス制御など、アクセス制限についてのより詳細な方法についても説明します。

## 製品管理者の役割

製品管理者の役割を割り当てられたユーザーには、デフォルトで、Customer Journey Analytics内でほとんどのタスクを実行するために必要な権限が付与されます。 ただし、一部のタスクには追加の権限が必要です。

ユーザーを製品管理者として追加するには：

1. 次に移動： [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. 選択 [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理者**] タブ/ [!UICONTROL **管理者を追加**].

   追加したユーザーには、 [製品管理者のデフォルトの権限](#product-admin-default-permissions). また、付与することもできます [追加の権限](#product-admin-additional-permissions) 必要に応じて。

### 製品管理者のデフォルトの権限

製品管理者には、タスク内のほとんどのタスクを完了する権限があります。Customer Journey Analytics

製品管理者には、デフォルトで次のタスクを実行するために必要な権限が付与されます。

* データビューの作成、更新、削除
* 他のユーザーが作成したプロジェクト、フィルター、計算指標、オーディエンス、注釈、フィルターの更新と削除
* Workspace プロジェクトをすべてのユーザーと共有する
* でのレポートアクティビティの管理 [レポートアクティビティマネージャー](/help/reporting-activity-manager/reporting-activity-overview.md)

### 製品管理者の追加の権限

製品管理者として追加されたことに加えて、 **Customer Journey Analytics製品プロファイル** （内） [Admin Console](https://adminconsole.adobe.com/enterprise/)の場合、Customer Journey Analytics内で次のタスクを完了するには、追加の権限が必要です。

* データの作成、更新、削除 [接続](/help/connections/overview.md)

  このタスクを実行するには、ユーザーが **Experience Platform製品プロファイル** には次の権限があります。
   * データモデリング：ビュースキーマ、スキーマの管理
   * データ管理：ビューデータセット，データセットの管理
   * データ取り込み：ソースの管理
   * ID 名前空間の表示

     Experience Platform の権限について詳しくは、[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)を参照してください。

* AEP の宛先からデータセットを書き出す

  このタスクを実行するには、次のExperience Platform権限も必要です。
   * 宛先の管理
   * 宛先のアクティブ化

     宛先の権限について詳しくは、「Experience Platformの宛先」を参照してください。 [宛先の概要](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=ja).

## 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。製品プロファイル管理者が実行できる操作

* 新しいユーザーの追加や、ユーザーグループとそれらに関連する製品プロファイルの管理など、単体製品のプロファイルを作成および管理します。

* Customer Journey Analyticsで、管理する製品プロファイルの一部であるデータビューを編集します。 新しいデータビューを作成することはできません。

## ユーザーレベルのアクセス

ユーザーは、Customer Journey Analytics では、データビューや接続を作成、編集または表示できません。ユーザーは、Admin Console で特別な権限を持つフィルター、プロジェクト、オーディエンスおよび計算指標を作成できます。

## Workspace プロジェクトのキュレーション

Workspace レポートレベルでは、別のレベルのアクセス制御を使用できます。特定のユーザーに対して、特定のコンポーネントへのアクセスを制限できます。Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、フィルター、日付範囲）の制限方法、キュレーションとデータビューとの関連付け方法について詳しくは、 [プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md).

## 個々の指標またはディメンションへのアクセス権を付与する

Customer Journey Analytics では、従来の Adobe Analytics の場合とは異なり、個々の指標やディメンションに権限を付与または拒否することはできません。指標およびディメンションは、 [データビュー](/help/data-views/data-views.md) こうして、Customer Journey Analyticsが変わる。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明するユースケースを次に示します。

### サードパーティアクセス

会社が連携するサードパーティには、製品プロファイル管理者になれるチームリードがいます。この管理者は、この製品プロファイルで自分のチームにユーザーを追加できます。この管理者は、特定のデータビューへのアクセス権を付与し、この製品プロファイルに他のユーザーを追加できます。また、チームのニーズに合わせて制御可能なデータビューを変更することもできます。

### 行レベルのアクセス制御

例えば、ユーザーに 1 日に限りデータへのアクセス権を付与するとします。アクセスを特定の行に制限する方法を次に示します。

1. 次の場所にフィルターをCustomer Journey Analytics **[!UICONTROL 日]** は、データアクセスを希望する日付と等しくなります。
1. [!UICONTROL データビュー]／[!UICONTROL 設定]をクリックし、そのフィルターをデータビューに追加します。
1. データビューを保存し、フィルターをデータセットに自動適用します。フィルター定義に適合しない行は、編集されたデータビューから自動的に除外されるようになります。
1. Admin Console で新しい製品プロファイルを作成し、ユーザーを追加して、このデータビューへのアクセスを制限します。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。管理者は、データビューで[機能の包含／除外](/help/data-views/component-settings/include-exclude-values.md)を使用して、例えば、特定のディメンション値をデータビューから除外します。

医療関連の例を次に示します。例えば、このデータを含むデータセットから、データビューで「高血圧」と呼ばれる指標を作成したとします。指標であるということは、この指標の総値を確認できますが、その指標に該当する個々の患者は確認できません。

## Customer Journey AnalyticsのAdmin Console権限

「**[!UICONTROL 権限]**」タブは、[Admin Console](https://adminconsole.adobe.com/enterprise/) の各製品プロファイルの一部です。特定の製品プロファイルにユーザーを追加できます。次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。次に、Customer Journey Analytics固有の権限を示します。

![Admin Console 権限](assets/permissions.png)

| 権限 | 定義 |
| --- | --- |
| **[!UICONTROL データビュー]** | **[!UICONTROL 自動インクルード]**&#x200B;を&#x200B;**[!UICONTROL オン]**&#x200B;に切り替えた場合、この製品プロファイルの一部であるユーザーは、既存のすべてのデータビューおよび新しく作成されたデータビューを表示できます。この設定が&#x200B;**[!UICONTROL オフ]**&#x200B;の場合、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| **[!UICONTROL レポートツール]**： |   |
| **[!UICONTROL 監査ログへのアクセス]** | この権限は、[API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) と今後の監査ログ UI に対する権限チェックを実施します。 |
| **[!UICONTROL レポート使用状況の管理]** | ユーザーは、会社で実行されているレポートを表示および削除できます |
| **[!UICONTROL レポート使用状況のビュー]** | ユーザーは同時レポートリクエストをすべて表示できます。 |
| [!UICONTROL **フルテーブルエクスポート**] | ユーザーに許可 [完全なテーブルをクラウドにエクスポート](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL 計算指標の作成]** | ユーザーは[計算指標](/help/components/calc-metrics/calc-metr-overview.md)を作成できます。 |
| **[!UICONTROL フィルターの作成]** | ユーザーは[フィルター](/help/components/filters/filters-overview.md)を作成できます。 |
| **[!UICONTROL Labs のアクセス]** | ユーザーが [Labs](/help/labs/labs.md) 」タブをCustomer Journey Analyticsに追加します。 |
| **[!UICONTROL 注釈の作成]** | ユーザーは[注釈](/help/components/annotations/overview.md)を作成できます。 |
| **[!UICONTROL オーディエンスの作成]** | ユーザーは[オーディエンス](/help/components/audiences/audiences-overview.md)を作成できます。 |
| **[!UICONTROL オーディエンスの表示]** | ユーザーは[オーディエンス](/help/components/audiences/audiences-overview.md)を表示できます。 |

{style="table-layout:auto"}
