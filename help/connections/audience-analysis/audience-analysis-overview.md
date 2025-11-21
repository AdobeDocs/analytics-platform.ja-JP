---
title: オーディエンス分析の概要
description: Customer Journey AnalyticsのRTCDPからオーディエンスを分析する方法について説明します。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 4%

---

# オーディエンス分析の概要

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md -->

>[!NOTE]
>
>オーディエンス分析は、オーディエンスの公開とは異なります。オーディエンスの公開では、Customer Journey Analyticsで検出されたオーディエンスを作成してAdobe Experience Platformに公開し、顧客のターゲティングやパーソナライゼーションに使用できます。 オーディエンスの公開について詳しくは、[&#x200B; オーディエンスの公開の概要 &#x200B;](/help/components/audiences/audiences-overview.md) を参照してください。

Audience analysis では、オーディエンスメンバーシップデータをExperience Platform プロファイルデータセットからCustomer Journey Analytics接続に取り込むことができます。 オーディエンスは、Analysis Workspaceで使用する新しいディメンションとして使用できるようになります。

次の図と関連する表は、Experience Platformの Audience Analysis 設定により、Analysis WorkspaceでCustomer Journey Analyticsのオーディエンスデータがどのように提供されるかを簡単に示したものです。

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

## Customer Journey Analyticsでのオーディエンスデータの分析

Customer Journey Analyticsで利用可能なオーディエンスデータを使用すると、様々なチャネルでのオーディエンスメンバーの行動に関する実用的なインサイトを得ることができます。

例えば、同じメールプロモーションに含まれた個々の顧客の行動を追跡できます。 Customer Journey Analyticsで利用できるオーディエンスを使用すると、各オーディエンスメンバーに関して次の種類の情報を確認できます。

* 最終的に購入につながったメールからサイトへのクリックスルー

* 最終的に店舗で購入したオーディエンスメンバー

詳しくは、[Customer Journey AnalyticsでのExperience Platform オーディエンスの分析 &#x200B;](/help/connections/audience-analysis/analyze-audiences.md) を参照してください。










