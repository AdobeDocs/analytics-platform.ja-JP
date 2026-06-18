---
title: 移行ガイド
description: Customer Journey AnalyticsからCustomer Journey Analytics B2B editionへの移行方法について説明します
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
autotag-review: '2026-05-19T08:06:36.475Z'
TQID: 'https://experienceleague.adobe.com/vkf6272OwRu9B4ZgpiXKhc4J3WAqUAm8r-3iQLUgOKg'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7id: d3f42e9e-bb51-4077-a732-358b801d8b29
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: d76b9e53-27fb-4597-933f-419cc0dd46dbid: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: c0173fff-a288-46f9-94aa-2b9ca0aa9ac1id: bfef374d-acfd-4c57-bf74-a2b36053c545id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 9c87ce4fb30c7d1d66ce88174443369ef44a7377
workflow-type: tm+mt
source-wordcount: 623
ht-degree: 3%

---

# 移行ガイド

このガイドでは、Customer Journey AnalyticsからCustomer Journey AnalyticsのB2B editionへの移行方法について説明します。

この記事では、Customer Journey Analyticsをある程度すでに使用していることを前提としています。

* Customer Journey Analyticsにデータを取り込む[connections](/help/connections/overview.md)があります。
* これらの接続のデータを使用する[ データビュー](/help/data-views/data-views.md)があります。
* これらのデータビューを活用したレポートとビジュアライゼーションを含む[ プロジェクト ](/help/analysis-workspace/home.md)があります。

以前にCustomer Journey Analyticsを使用したことがない場合は、[B2B edition クイックスタートガイド ](cja-b2b-quick-start-guide.md)を参照してください。

Adobe Analytics ユーザーで、Customer Journey Analytics B2B editionを使用する予定がある場合は、まずAdobe AnalyticsからCustomer Journey Analyticsへの[ アップグレードに関するドキュメント ](cja-upgrade/cja-upgrade-recommendations.md)を参照してください。


## 既存の実装

Customer Journey Analytics B2B editionのライセンスとプロビジョニングを取得しても、Customer Journey Analyticsの既存の実装は変更されません。

既存のすべての接続は[人ベースの接続](cja-b2b-concepts-features.md#connections-and-identifiers)と見なされ、更新なしで引き続き機能します。 データビュー、ワークスペースプロジェクト、セグメント、スケジュールされた書き出し、アラートなど、これらの個人ベースの接続からのデータに依存するあらゆるものが、当初の計画どおりに機能し続けます。

>[!IMPORTANT]
>
>既存の個人ベースの接続をアカウントベースの接続に変更することはできません。 B2B editionの機能を利用するには、新しいアカウントベースの接続が必要です。
>


## B2B機能の導入

既存の実装にB2B機能を導入するには、次の手順に従う必要があります。

1. B2B データをモデル化する： [Adobe Experience Data Model （XDM） ](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=ja)を使用して、B2B データを標準化し、B2B データのスキーマを定義できます。<br/> スキーマは、Real-time CDP B2B edition](https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/schemas/b2b)で提供されている[標準クラスに基づいて作成するか、独自のカスタムクラスとスキーマを使用できます。 [ ユースケース ](/help/use-cases/b2b/b2b-edition/use-cases-overview.md)記事では、Real-time CDP B2B edition クラスとスキーマを使用していますが、標準クラスとスキーマを使用するには、Real-time CDP B2B edition ライセンスは必要ありません。 <br/>Customer Journey Analytics B2B editionは、少なくともアカウントベースの時系列イベントデータを想定しており、追加のプロファイルまたはルックアップレコードデータのメリットを享受できます。 アカウントデータ、購買グループデータ、商談データ、マーケティングリストメンバーデータなど、さまざまなデータソースを選択できます。

   * プライマリアカウント識別子（アカウント ID）として使用する識別子を定義します。 多くの場合、既存のCRMまたはその他のツール（例：Demandbase）を使用すると、その識別子を判断できます。
   * 使用する予定のその他のB2B データの追加IDを特定します。グローバルアカウント識別子、商談識別子、購買グループ識別子、人物識別子です。

1. B2B データの準備。 あらゆる時系列イベントデータと関連するレコードデータをまたいで、アカウント IDを追加し、収集していることを確認します。 同様に、時系列イベントデータとルックアップレコードに、関連イベントの他の識別子が含まれていることを確認します。 例：別のセールスステージへの移行を示すイベントには、商談識別子を付ける必要があります。 このIDは商談検索データの一部である必要があります。

1. [新しいアカウントベースの接続を作成](/help/connections/create-connection.md#account-based-connection)。 含めるオプションのコンテナを選択し、[ データセット ](/help/connections/create-connection.md#add-datasets)を追加して、各データセット ](/help/connections/create-connection.md#dataset-settings)の[設定を定義します。 可能な限り、ルックアップレコードデータセットに[ コンテナによる一致](cja-b2b-concepts-features.md#match-by-container)を使用します。

1. [新しい接続に基づいてデータビュー](/help/data-views/create-dataview.md)を作成します。

   * 取り込んだデータから、関連するあらゆるフィールドを指標またはディメンションとして追加する必要があります。
   * 必要に応じて、コンポーネントの設定（永続性やアトリビューションなど）を適用します。
   * 必要に応じて、派生フィールドを追加します。

1. [ ワークスペースプロジェクト ](/help/analysis-workspace/build-workspace-project/create-projects.md)を作成して、B2B データに関するレポートを作成し、インサイトを得ます。 [ コンテナ ](cja-b2b-concepts-features.md#containers)などの特定のB2B機能を使用して、詳細なインサイトを得ます。

   1つのワークスペースプロジェクトで複数の[ パネル ](/help/analysis-workspace/c-panels/panels.md)を使用することで、B2B （個人ベース）およびB2B （アカウントベース）のレポートとインサイトを組み合わせることができます。
