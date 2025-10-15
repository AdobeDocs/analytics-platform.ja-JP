---
title: 移行ガイド
description: Customer Journey AnalyticsからCustomer Journey Analytics B2B editionに移行する方法を説明します
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 3c13ae26a9ef48454467fc21b8faaa9e078c7f9f
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# 移行ガイド

このガイドでは、Customer Journey AnalyticsからCustomer Journey AnalyticsのB2B editionに移行する方法について説明します。

この記事では、ある程度までCustomer Journey Analyticsを使用していることを前提としています。

* データをCustomer Journey Analyticsに取り込む [&#x200B; 接続 &#x200B;](/help/connections/overview.md) があります。
* これらの接続のデータを使用する [&#x200B; データビュー &#x200B;](/help/data-views/data-views.md) があります。
* これらのデータビューを活用したレポートとビジュアライゼーションを持つ [&#x200B; プロジェクト &#x200B;](/help/analysis-workspace/home.md) があります。

Customer Journey Analyticsを使用したことがない場合は、[B2B edition クイックスタートガイド &#x200B;](cja-b2b-quick-start-guide.md) を参照してください。

Adobe Analytics ユーザーでCustomer Journey Analytics B2B editionの使用を計画している場合は、まず [Adobe AnalyticsからCustomer Journey Analyticsへのアップグレード &#x200B;](cja-upgrade/cja-upgrade-recommendations.md) ドキュメントを参照してください。


## 既存の実装

Customer Journey Analytics B2B editionのライセンスを取得してプロビジョニングすると、Customer Journey Analyticsの既存の実装はまったく変わりません。

既存の接続はすべて [&#x200B; ユーザーベースの接続 &#x200B;](cja-b2b-concepts-features.md#connections-and-identifiers) と見なされ、更新なしで引き続き機能します。 データビュー、ワークスペースプロジェクト、セグメント、スケジュールされた書き出し、アラートなど、これらのユーザーベースの接続からのデータに依存するすべてのものは、最初に計画され、意図されたとおりに引き続き機能します。

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

1. [&#x200B; 新しいアカウントベースの接続を作成 &#x200B;](/help/connections/create-connection.md#account-based-connection)。 含めるオプションコンテナを選択し、[&#x200B; データセットを追加 &#x200B;](/help/connections/create-connection.md#add-datasets)、[&#x200B; 各データセットの設定 &#x200B;](/help/connections/create-connection.md#dataset-settings) を定義します。 可能な限り、ルックアップレコードデータセットに [&#x200B; コンテナで一致 &#x200B;](cja-b2b-concepts-features.md#match-by-container) を使用します。

1. 新しい接続に基づいて [&#x200B; データビューを作成 &#x200B;](/help/data-views/create-dataview.md) します。

   * すべての関連するフィールドを、取り込んだデータから指標またはディメンションとして必ず追加してください。
   * 必要に応じて、コンポーネントの設定（永続性、アトリビューションなど）を適用します。
   * 必要に応じて、派生フィールドを追加します。

1. [&#x200B; ワークスペースプロジェクトを作成 &#x200B;](/help/analysis-workspace/build-workspace-project/create-projects.md) し、B2B データに関するレポートを作成してインサイトを得ます。 [&#x200B; コンテナ &#x200B;](cja-b2b-concepts-features.md#containers) などの特定の B2B 機能を使用して、深いインサイトを得ます。

   複数の [&#x200B; パネル &#x200B;](/help/analysis-workspace/c-panels/panels.md) を使用して、B2B （ユーザーベース）と B2B （アカウントベース）のレポートとインサイトを 1 つのワークスペースプロジェクトに組み合わせることができます。
