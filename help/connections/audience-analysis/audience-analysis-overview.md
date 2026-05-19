---
title: Audience Analysis Overview
description: Customer Journey AnalyticsでRTCDPのオーディエンスを分析する方法について説明します。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 1e962f52-6b56-4671-afea-d58dae67e8a8
autotag-review: '2026-05-19T10:43:44.564Z'
TQID: 'https://experienceleague.adobe.com/Glq5cGUw910uanF1Blgj5E-Fzo1Ycn26VzZvNRwxpLE'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 752
ht-degree: 3%

---

# Audience Analysis overview

>[!NOTE]
>
>オーディエンス分析とオーディエンス公開の違いを理解する：
>
>* **オーディエンス分析**: Experience Platform プロファイル データセットからCustomer Journey Analytics接続にオーディエンスメンバーシップ データを取り込むことができます。
>* **オーディエンスの公開**:Customer Journey Analyticsで発見したオーディエンスを作成し、Adobe Experience Platformに公開して、顧客のターゲティングとパーソナライズを行うことができます。 オーディエンスの公開について詳しくは、[&#x200B; オーディエンスの公開の概要](/help/components/audiences/audiences-overview.md)を参照してください。

Audience Analysisを使用すると、Experience Platform プロファイルデータセットからCustomer Journey Analytics接続にオーディエンスメンバーシップデータを取り込むことができます。 オーディエンスは、Analysis Workspaceで使用する新しいディメンションとして利用できるようになります。

次の図と関連する表は、Customer Journey Analyticsのaudience analysis設定によって、Experience PlatformのオーディエンスデータがAnalysis Workspaceでどのように利用できるようになるのかを示す概要を示しています。

![&#x200B; オーディエンス分析の概要](assets/audience-analysis-overview.png)

| 数値 | 機能 | 関数 |
|---------|----------|---------|
| 1 | オーディエンス分析設定 | Customer Journey Analyticsの設定インターフェイスは、オーディエンス分析の設定に使用されます。 |
| 2 | サンドボックス | 接続に追加するプロファイルデータセットを含める必要があります。 |
| 3 | Profile データセット | Experience Platformのオーディエンスデータを含める必要があります。 このプロファイルデータセットは、選択した接続に追加されます。 |
| 4 | 結合ポリシー | 分析するExperience Platform オーディエンスに関連付けられている結合ポリシー。 |
| 5 | プロファイルデータ | 選択した結合ポリシーに関連付けられているプロファイルデータ。 このデータは、Experience Platformのデータセットで利用できます。 |
| 6 | 新しい参照データセット | 作成される新しいオーディエンスディメンションのわかりやすい名前を提供します。 <p>ルックアップデータセットが自動的に作成され、選択したプロファイルデータセットとともに接続に追加されます。</p> |
| 7 | 接続 | 選択したプロファイルデータセットを追加する接続。 |
| 8 | 新しいオーディエンスディメンション | 選択したプロファイルデータセットに含まれ、Analysis Workspaceでレポートに使用できるExperience Platform オーディエンスを表す新しいオーディエンスディメンション <!--and metrics?-->。 これらのディメンションは自動的に作成されます。 |
| 9 | データビュー | 選択したデータビューが、接続に関連付けられています。 Analysis Workspace内のExperience Platform オーディエンスデータを分析する際に使用するデータビューです。 これらのデータビューは、レポート用にExperience Platformオーディエンスデータで自動的に設定されます。 |

## オーディエンス分析の設定

オーディエンス分析を設定する際に、分析するExperience Platform オーディエンスに関連付けられているサンドボックスと結合ポリシーを選択します。 Customer Journey Analyticsは新しいルックアップデータセットを作成し、選択した接続にルックアップデータセットとプロファイルデータセットを自動的に追加します。

>[!IMPORTANT]
>
>オーディエンスデータは毎晩再処理および生成され、前日（「昨日」）のみ分析できる正確なオーディエンスデータになります。
>
>オーディエンスは、audience analysis設定を作成した翌日にCustomer Journey Analytics データビューで使用できます。

詳しくは、[&#x200B; オーディエンス分析の設定](/help/connections/audience-analysis/audience-analysis-configure.md)を参照してください。

## オーディエンス分析の設定の管理

オーディエンス分析設定は、作成後に管理できます。 設定を表示、編集、削除できます。

既存のオーディエンス分析設定の管理について詳しくは、[&#x200B; オーディエンス分析設定の管理](/help/connections/audience-analysis/audience-analysis-manage.md)を参照してください。

## Adobe Customer Journey Analyticsでのオーディエンスデータの分析

Adobe Customer Journey Analyticsで利用可能なオーディエンスデータを活用すれば、さまざまなチャネルをまたいでオーディエンスがどのように行動しているのかを、実践的なインサイトを得ることができます。

例えば、同じメールプロモーションに含まれた個々の顧客の行動を追跡できます。 Customer Journey Analyticsで利用可能なオーディエンスを使用すると、各オーディエンスメンバーに関する次の種類の情報を確認できます。

* 電子メールからサイトへのクリックスルー率が高く、最終的に購入につながった

* オーディエンス：最終的に店舗で購入した

詳しくは、[Customer Journey AnalyticsでのExperience Platform オーディエンスの分析](/help/connections/audience-analysis/analyze-audiences.md)を参照してください。

## オーディエンス分析の役割と権限の要件

オーディエンス分析には、次のCustomer Journey Analyticsの役割とExperience Platformの権限が必要です。

| 機能 | Customer Journey Analyticsの役割または権限の要件 | Experience Platformの権限の要件 |
|---------|----------|----------|
| [&#x200B; オーディエンス分析設定の作成](/help/connections/audience-analysis/audience-analysis-configure.md) | システム管理者 | <ul><li>データセット：読み取り権限</li><li>スキーマ：読み取り、書き込み</li><li>ID名前空間：読み取り</li></ul> |
| [&#x200B; データビューでオーディエンス分析ディメンションを表示](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | データビューが割り当てられている製品プロファイルの製品プロファイル管理者 <p>詳しくは、[&#x200B; アクセス制御](/help/technotes/access-control.md)を参照してください。</p> | 該当なし |
| Analysis Workspaceでのオーディエンス分析ディメンションの使用 | オーディエンス分析ディメンションが追加されたデータビューへのアクセス | 該当なし |

## オーディエンス分析のユースケース

Audience Analysisが提供する値を強調表示するユースケースの例については、[Audience Analysis ユースケース &#x200B;](/help/connections/audience-analysis/audience-analysis-use-cases.md)を参照してください。

## オーディエンス分析の限界

オーディエンス分析[&#128279;](/help/connections/audience-analysis/audience-analysis-configure.md)を設定する場合は、次の制限を考慮してください。

* 1つのサンドボックスで最大100個のオーディエンス分析設定をサポートできます。

* 1つの接続は、1つのオーディエンス分析設定にのみ関連付けることができます。
