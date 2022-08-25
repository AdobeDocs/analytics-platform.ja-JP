---
title: CJA アクセス制御
description: CJA でアクセス制御を実装する方法について説明します。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: ccb13b9632433f2fcc9c765e9527f157dad632d4
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 17%

---

# CJA アクセス制御

Customer Journey Analytics(CJA) は、3 つのアクセスレベルまたは 3 つの役割で管理されます。製品管理者の役割、製品プロファイル管理者の役割、ユーザーレベルのアクセス。 このトピックでは、これらの役割について詳しく説明します。

## 製品管理者の役割

製品管理者には、CJA 内で必要なタスクを完了する権限があります。 製品管理者として、 **Customer Journey Analytics製品プロファイル** 内 [Admin Console](https://adminconsole.adobe.com/enterprise/) under [!UICONTROL Customer Journey Analytics] > [!UICONTROL 管理者] タブ/ [!UICONTROL 管理者を追加]. 製品管理者には、次の権限が付与されます。

* 接続またはデータ表示の作成／更新／削除を行う
* 他のユーザーが作成したプロジェクト、フィルター、計算指標、オーディエンス、注釈、フィルターの更新/削除
* Workspace プロジェクトをすべてのユーザーと共有する

Customer Journey Analyticsのみで製品管理者になることは、 [接続](/help/connections/overview.md). Experience Platform データセットへの接続を作成するには、Experience Platform 権限も必要です。特に、**Experience Platform 製品プロファイル**&#x200B;の一部であり、次の権限が与えられていることが必要です。

* データモデリング：ビュースキーマ、スキーマの管理
* データ管理：ビューデータセット，データセットの管理
* データ取り込み：ソースの管理
* ID 名前空間の表示

Experience Platform の権限について詳しくは、[Adobe Experience Platform のアクセス制御](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=ja)を参照してください。

## 製品プロファイル管理者の役割

製品プロファイルは、一連の権限です。 製品プロファイル管理者が実行できる操作

* 新しいユーザーの追加など、個々の製品プロファイルを作成および管理します。

* CJA で、管理する製品プロファイルの一部であるデータビューを編集します。 新しいデータビューを作成することはできません。

## ユーザーレベルのアクセス

Customer Journey Analytics内のユーザーは、データビューや接続を作成、編集、表示することはできません。 ユーザーは、指標内で特別な権限を持つフィルター、プロジェクト、オーディエンスおよび計算Admin Consoleを作成できます。

## Workspace プロジェクトのキュレーション

別のレベルのアクセス制御は、Workspace レポートレベルで使用できます。 特定のユーザーの特定のコンポーネントへのアクセスを制限できます。 Workspace プロジェクトレベルでのコンポーネント（ディメンション、指標、セグメント、日付範囲）の制限方法、キュレーションとデータビューとの関連付け方法について詳しくは、 [プロジェクトのキュレーション](/help/analysis-workspace/curate-share/curate.md).

## 個々の指標またはディメンションへのアクセス権を付与する

従来の Adobe Analytics の場合とは異なり、Customer Journey Analytics 内の個々の指標やディメンションに権限を付与または拒否することはできません。指標およびディメンションは、 [データビュー](/help/data-views/data-views.md) したがって、CJA では変更される可能性があります。 これらを変更すると、レポートも遡って変更されます。

## ユースケース

実際のシナリオでアクセス制御をどのように使用できるかを説明する使用例を以下にいくつか示します。

### サードパーティアクセス

貴社が連携するサードパーティには、製品プロファイル管理者にできるチームリードがいます。 その後、この管理者は自分のチームのユーザーをこの製品プロファイルに追加できます。 この管理者は、特定のデータビューへのアクセス権を付与し、この製品プロファイルに他のユーザーを追加できます。 また、チームのニーズに合わせて制御できるデータビューを変更することもできます。

### 行レベルのアクセス制御

ユーザーに 1 日のデータへのアクセス権を付与したいとします。 アクセスを特定の行に制限する方法を次に示します。

1. CJA でフィルターを作成します。ここで、 **[!UICONTROL 日]** は、データアクセスを希望する日付と等しくなります。
1. In [!UICONTROL データビュー] > [!UICONTROL 設定]をクリックし、そのフィルターをデータビューに追加します。
1. データビューを保存し、フィルターをデータセットに自動適用します。 フィルター定義に適合しない行は、編集後のデータビューから自動的に除外されるようになりました。
1. Admin Consoleで新しい製品プロファイルを作成し、ユーザーを追加して、このデータビューへのアクセスを制限します。

### 値レベルのアクセス制御

データビューへのアクセス権を持つユーザーは、管理者がこのデータビューに含めた指標およびディメンションのみを操作できます。 管理者は、 [含める/除外機能](/help/data-views/component-settings/include-exclude-values.md) を使用して、例えば、特定のディメンション値をデータビューから除外します。

医療関連の例を次に示します。例えば、このデータを含むデータセットから、データビューで「高血圧」と呼ばれる指標を作成したとします。 指標であるという事実はこの指標の総値を見ることができますがその指標に該当する個々の患者は見ることができません

## CJA 権限

この **[!UICONTROL 権限]** タブは、 [Admin Console](https://adminconsole.adobe.com/enterprise/). 特定の製品プロファイルにユーザーを追加できます。 次に、特定のデータビューに権限を割り当て、製品プロファイルのユーザーが持つ権限を指定します。 CJA 固有の権限を次に示します。

![admin console 権限](assets/permissions.png)

| 権限 | 定義 |
| --- | --- |
| **[!UICONTROL データビュー]** | 切り替えた場合 **[!UICONTROL 自動インクルード]** から **[!UICONTROL オン]**&#x200B;の場合、この製品プロファイルの一部であるユーザーは、新しく作成された既存のすべてのデータビューを表示できます。 この設定が **[!UICONTROL オフ]**&#x200B;を使用すると、ユーザーがアクセスできる特定のデータビューを選択できます。 |
| **[!UICONTROL レポートツール]**: |  |
| **[!UICONTROL 監査ログへのアクセス]** | 現在、 [監査ログ](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) は、API 経由でのみ使用できます。 この権限は、開発中の将来の UI に対するものです。 |
| **[!UICONTROL レポート使用状況の管理]** | ユーザーは、会社で実行されているレポートを表示および削除できます。 （レポートの使用機能はまだリリースされていません）。 |
| **[!UICONTROL レポート使用状況のビュー]** | ユーザーは同時レポートリクエストをすべて表示できます。 （レポートの使用機能はまだリリースされていません）。 |
| **[!UICONTROL 計算指標の作成]** | ユーザーが [計算指標](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL フィルターの作成]** | ユーザーが [フィルター](/help/components/filters/filters-overview.md). |
| **[!UICONTROL ラボのアクセス]** | ユーザーが [ラボ](/help/labs/labs.md) 」タブを使用します。 |
| **[!UICONTROL 注釈の作成]** | ユーザーが [注釈](/help/components/annotations/overview.md). |
| **[!UICONTROL オーディエンスの作成]** | ユーザーが [audiences](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL オーディエンス表示]** | ユーザーが [audiences](/help/components/audiences/audiences-overview.md). |