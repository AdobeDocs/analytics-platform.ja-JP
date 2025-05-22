---
title: 移行ガイド
description: Customer Journey AnalyticsからCustomer Journey Analytics B2B editionに移行する方法を説明します
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
hide: true
hidefromtoc: true
source-git-commit: c0446bd85b65109fd3311d54e33f9fb33af28f88
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# 移行ガイド

{{draft-b2b}}

このガイドでは、Customer Journey AnalyticsからCustomer Journey AnalyticsのB2B editionに移行する方法について説明します。

この記事では、ある程度までCustomer Journey Analyticsを使用していることを前提としています。

* データをCustomer Journey Analyticsに取り込む [ 接続 ](/help/connections/overview.md) があります。
* これらの接続のデータを使用する [ データビュー ](/help/data-views/data-views.md) があります。
* これらのデータビューを活用したレポートとビジュアライゼーションを使用した [ プロジェクト ](/help/analysis-workspace/home.md) があります。

Customer Journey Analyticsを使用したことがない場合は、[B2B edition クイックスタートガイド ](cja-b2b-quick-start-guide.md) を参照してください。


## 既存の実装

Customer Journey Analytics B2B editionのライセンスを取得してプロビジョニングすると、Customer Journey Analyticsの既存の実装はまったく変わりません。

既存の接続はすべて [ ユーザーベースの接続 ](cja-b2b-concepts-features.md#connections-and-identifiers) と見なされ、更新なしで引き続き機能します。 データビュー、ワークスペースプロジェクト、セグメント、スケジュールされた書き出し、アラートなど、これらのユーザーベースの接続からのデータに依存するすべてのものは、最初に計画され、意図されたとおりに引き続き機能します。

>[!IMPORTANT]
>
>既存のユーザーベースの接続をアカウントベースの接続に変更することはできません。 B2B editionの機能を利用するには、新しいアカウントベースの接続が必要です。
>


## B2B 機能の実装

既存の実装に B2B 機能を実装するには、次の手順に従う必要があります。

1. B2B データをモデル化します。 Customer Journey Analytics B2B editionでは、少なくともアカウントベースの時系列イベントデータを想定し、追加のプロファイルまたはルックアップレコードデータのメリットがあります。 例えば、アカウントデータ、購入グループデータ、商談データ、マーケティングリストメンバーデータなどのデータです。

   * プライマリアカウント識別子として使用する識別子（アカウント ID）を定義します。 多くの場合、既存の CRM やその他のツール（例：Demandbase）を使用すると、その識別子を判断できます。
   * 使用を予定しているその他の B2B データに対して、追加の識別子（グローバルアカウント ID、オポチュニティ ID、購入グループ ID、人物識別子）を識別します。

1. B2B データを準備します。 すべての時系列イベントデータと関連するレコードデータにわたって、アカウント識別子を確実に追加および収集します。 同様に、時系列のイベントデータとルックアップレコードには、関連するイベントの他の識別子が含まれていることを確認します。 例：別の販売ステージへの移行を知らせるイベントには、オポチュニティ ID を含める必要があります。 この識別子は、商談ルックアップデータの一部である必要があります。

1. [ 新しいアカウントベースの接続を作成 ](/help/connections/create-connection.md#account-based-connection)。 含めるオプションコンテナを選択し、[ データセットを追加 ](/help/connections/create-connection.md#add-datasets)、[ 各データセットの設定 ](/help/connections/create-connection.md#dataset-settings) を定義します。 可能な限り、ルックアップレコードデータセットに [ コンテナで一致 ](cja-b2b-concepts-features.md#match-by-container) を使用します。

1. 新しい接続に基づいて ](/help/data-views/create-dataview.md) データビューを作成 [ します。

   * すべての関連するフィールドを、取り込んだデータから指標またはディメンションとして必ず追加してください。
   * 必要に応じて、コンポーネントの設定（永続性、アトリビューションなど）を適用します。
   * 必要に応じて、派生フィールドを追加します。

1. [ ワークスペースプロジェクトを作成 ](/help/analysis-workspace/build-workspace-project/create-projects.md) し、B2B データに関するレポートを作成してインサイトを得ます。 [ コンテナ ](cja-b2b-concepts-features.md#containers) などの特定の B2B 機能を使用して、深いインサイトを得ます。

   複数の [ パネル ](/help/analysis-workspace/c-panels/panels.md) を使用して、B2B （ユーザーベース）と B2B （アカウントベース）のレポートとインサイトを 1 つのワークスペースプロジェクトに組み合わせることができます。
