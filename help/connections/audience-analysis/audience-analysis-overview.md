---
title: オーディエンス分析の概要
description: Customer Journey AnalyticsのRTCDPからオーディエンスを分析する方法について説明します。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: f23775342a29d758b478206a77386e18a58312a6
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 4%

---

# オーディエンス分析の概要

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md and this article: /help/analysis-workspace/templates/use-templates.md-->

>[!NOTE]
>
>オーディエンス分析とオーディエンス公開の違いを理解する：
>
>* **オーディエンス分析**:Experience Platform プロファイルデータセットからCustomer Journey Analytics接続にオーディエンスメンバーシップデータを取り込むことができます。
>* **オーディエンスの公開**:Customer Journey Analyticsで検出されたオーディエンスを作成してAdobe Experience Platformに公開し、顧客のターゲティングやパーソナライゼーションに使用できます。 オーディエンスの公開について詳しくは、[&#x200B; オーディエンスの公開の概要 &#x200B;](/help/components/audiences/audiences-overview.md) を参照してください。

Audience analysis では、オーディエンスメンバーシップデータをExperience Platform プロファイルデータセットからCustomer Journey Analytics接続に取り込むことができます。 オーディエンスは、Analysis Workspaceで使用する新しいディメンションとして使用できるようになります。

次の図と関連する表は、Analysis Workspaceの Audience Analysis 設定により、Customer Journey AnalyticsでExperience Platformのオーディエンスデータが使用できるようにする仕組みを簡単に示しています。

![&#x200B; オーディエンス分析の概要 &#x200B;](assets/audience-analysis-overview.png)

| 数値 | 機能 | 関数 |
|---------|----------|---------|
| 1 | オーディエンス分析設定 | オーディエンス分析の設定に使用する、Customer Journey Analyticsの設定インターフェイス。 |
| 2 | サンドボックス | 接続に追加するプロファイルデータセットが含まれている必要があります。 |
| 3 | Profile データセット | 分析するExperience Platform オーディエンスデータを含める必要があります。 このプロファイルデータセットは、選択した接続に追加されます。 |
| 4 | 結合ポリシー | 分析するExperience Platform オーディエンスに関連付けられた結合ポリシー。 |
| 5 | プロファイルデータ | 選択した結合ポリシーに関連付けられたプロファイルデータ。 このデータは、Experience Platform データセット内で使用できます。 |
| 6 | 新しいルックアップデータセット | 作成された新しいオーディエンスディメンションにわかりやすい名前を指定します。 ルックアップデータセットが自動的に作成され、選択したプロファイルデータセットと共に接続に追加されます。 |
| 7 | 接続 | 選択したプロファイルデータセットを追加する接続。 |
| 8 | 新しいオーディエンスディメンション | 選択したプロファイルデータセットに含まれるExperience Platform オーディエンスを表し <!--and metrics?-->Analysis Workspaceでレポートに使用できる新しいオーディエンスディメンション。 これらのディメンションは自動的に作成されます。 |
| 9 | データビュー | 接続に関連付けられた、選択したデータビュー。 これらは、Analysis Workspace内でExperience Platform オーディエンスデータを分析する際に使用するデータビューです。 これらのデータビューは、レポート用にExperience Platform オーディエンスデータで自動的に設定されます。 |
| 10 | Analysis Workspace | 取り込まれたCustomer Journey Analytics オーディエンスを含んだレポートを作成するExperience Platform内の領域。 |

## オーディエンス分析の設定

オーディエンス分析を設定する場合は、分析するExperience Platform オーディエンスに関連付けられたサンドボックスと結合ポリシーを選択します。 Customer Journey Analyticsは、新しいルックアップデータセットを作成してから、ルックアップデータセットとプロファイルデータセットを選択した接続に自動的に追加します。

詳しくは、[&#x200B; オーディエンス分析の設定 &#x200B;](/help/connections/audience-analysis/audience-analysis-configure.md) を参照してください。

## オーディエンス分析設定の管理

オーディエンス分析設定の作成後に、それらを管理できます。 設定の表示、編集、削除を行うことができます。

既存のオーディエンス分析設定の管理について詳しくは、[&#x200B; オーディエンス分析設定の管理 &#x200B;](/help/connections/audience-analysis/audience-analysis-manage.md) を参照してください。

## Customer Journey Analyticsでのオーディエンスデータの分析

Customer Journey Analyticsで利用可能なオーディエンスデータを使用すると、様々なチャネルでのオーディエンスメンバーの行動に関する実用的なインサイトを得ることができます。

例えば、同じメールプロモーションに含まれた個々の顧客の行動を追跡できます。 Customer Journey Analyticsで利用できるオーディエンスを使用すると、各オーディエンスメンバーに関して次の種類の情報を確認できます。

* 最終的に購入につながったメールからサイトへのクリックスルー

* 最終的に店舗で購入したオーディエンスメンバー

詳しくは、[Customer Journey AnalyticsでのExperience Platform オーディエンスの分析 &#x200B;](/help/connections/audience-analysis/analyze-audiences.md) を参照してください。

## オーディエンス分析の役割と権限の要件

オーディエンス分析には、次のCustomer Journey Analyticsの役割とExperience Platformの権限が必要です。

| 機能 | Customer Journey Analyticsの役割または権限の要件 | Experience Platformの権限要件 |
|---------|----------|----------|
| [&#x200B; オーディエンス分析設定の作成 &#x200B;](/help/connections/audience-analysis/audience-analysis-configure.md) | システム管理者 | <ul><li>データセット：読み取り権限</li><li>スキーマ：読み取り、書き込み</li><li>および ID 名前空間：読み取り</li></ul> |
| [&#x200B; データビューでのオーディエンス分析ディメンションの表示 &#x200B;](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | データビューが割り当てられた製品プロファイルの製品プロファイル管理者 <p>詳しくは、[&#x200B; アクセス制御 &#x200B;](/help/technotes/access-control.md) を参照してください。</p> | 該当なし |
| Analysis Workspaceでのオーディエンス分析ディメンションの使用 | オーディエンス分析ディメンションが追加されたデータビューにアクセスします | 該当なし |










