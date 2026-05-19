---
title: Adobe Customer Journey Analyticsの製品分析
description: Customer Journey Analyticsで効果的に商品分析を行うために使用できる機能について説明します。
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
TQID: https://experienceleague.adobe.com/24OrFfxJY7XuqMYoTrmijM5xRfsdGhfA-aKe5tY-7xw
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bfa38d8a-4e93-4fd8-8cd8-e72c589e3af8
  - id: bfef374d-acfd-4c57-bf74-a2b36053c545
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: f3ca85c1-72de-4df2-97ed-05753cd77c47
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 14557a59902110b1768d61e621adfb3f76ee9930
workflow-type: tm+mt
source-wordcount: 894
ht-degree: 5%

---

# Adobe Customer Journey Analyticsの製品分析

製品分析とは、利用者がジャーニーの各段階で製品とどのように関わっているかを把握するプロセスです。 データを分析して、利用者の行動、製品のパフォーマンス、成長の機会に関するインサイトを明らかにすることが含まれます。 効果的な製品分析は、ユーザーエクスペリエンスの向上、エンゲージメントの促進、ビジネス目標の達成のために、十分な情報にもとづいた意思決定をおこなうのに役立ちます。

Customer Journey Analyticsなら、プロダクトエクスペリエンスを分析、最適化し、次のことを実現できます。

* **製品データの大規模な管理**：製品データを容易に取り込み、変換、管理し、ビジネスニーズに対応して、信頼できるインサイトを確保します。
* **獲得とアクティベーションの測定**：新規ユーザーが製品をどのように発見し、最初の価値創出イベントにエンゲージしたかを追跡します。
* **エンゲージメントとアダプションの測定**：利用者が製品funnelをどのように利用しているのかを把握し、利用者がつまずきやすいポイントを特定し、主要機能の導入を追跡します。
* **リテンションと解約の測定**：ユーザーのリテンション率を長期的に分析し、解約の指標を特定し、脱落を減らし、ロイヤルティを高めるための戦略を策定します。
* **アクション製品のインサイト**: データ主導のインサイトを実用的な戦略に変換し、ユーザーエクスペリエンスを向上させ、持続可能な製品の成長を促進します。
* **組織とインサイトを共有する**：チーム間で重要な発見を伝え、取り組みを調整し、コラボレーションを促進し、全員が共有された製品およびビジネス目標に向かって取り組んでいることを確認します。

Customer Journey Analyticsでは、これらの機能を活用することで、製品の可能性を最大限に引き出し、ユーザーとビジネスの成功を促進するシームレスなデータドリブン型のアプローチを実現します。

## 製品データの大規模な管理

正確な商品データは、効果的な製品分析の基盤です。 データ収集とは、製品データを計測して収集するプロセスのことです。一方、データ管理では、このデータを変換および保守し、分析要件を満たしていることを確認します。

Adobe Experience PlatformおよびCustomer Journey Analyticsには、次のような機能があります。

* Adobe Experience Platform
   * [データセット&#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)
   * [データ準備&#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)
   * [Data &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [つながり&#x200B;](/help/connections/overview.md)
   * [&#x200B; データビュー](/help/data-views/data-views.md) （[派生フィールド&#x200B;](/help/data-views/derived-fields/derived-fields.md)を含む）
   * [セグメント&#x200B;](/help/components/segments/seg-overview.md)
   * [計算指標](/help/components/calc-metrics/calc-metr-overview.md)
   * [ガイド付き分析&#x200B;：タイムライン&#x200B;](/help/guided-analysis/types/timeline.md)

## 獲得とアクティベーションを測定

商品の成長は、新規顧客を惹きつけ、コンバージョンへの道筋を明らかにし、カスタマージャーニーにおけるつまずきを排除するための、実用的なfunnel上部のインサイトの獲得にかかっています。

* 顧客獲得は、製品にアクセスした新規ユーザーを追跡し、その増加方法や、効果が最も高い取り組み、低い取り組みを追跡します。
* アクティベーションでは、具体的な目標に従って定義された、最初の価値イベントに関与した新しいユーザーを監視します。

![アクティブな増加率](/help/guided-analysis/assets/active.png)

Customer Journey Analyticsでは、次の機能を利用して、獲得とアクティベーションの両方を効果的に測定できます。

* [ガイド付き分析&#x200B;：アクティブな成長](/help/guided-analysis/types/active-growth.md)
* [ガイド付き分析：純成長](/help/guided-analysis/types/net-growth.md)
* [ガイド付き分析：トレンド](/help/guided-analysis//types/trends.md)
* [アトリビューションパネル&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* マーケティングチャネルディメンションを含む[&#x200B; フリーフォームテーブル &#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md) （[派生フィールド &#x200B;](/help/data-views/derived-fields/derived-fields.md)を使用して作成）

## エンゲージメントと導入を測定

新規ユーザーの獲得は、商品のトップを拡大しますfunnel. エンゲージメントでは、そうした利用者をfunnelのさらに下に誘導し、成功への障害を取り除くことに焦点を当てます。 その成功は、ビジネスの成功を直接促進します。

![&#x200B; エンゲージメント分析](/help/guided-analysis/assets/feature-matrix.png)

Customer Journey Analyticsの次の機能は、製品のエンゲージメントと採用率を追跡するのに役立ちます。

* [ガイド付き分析：エンゲージメント](/help/guided-analysis/types/engagement.md)
* [ガイド付き分析：トレンド](/help/guided-analysis/types/trends.md)
* [ガイド付き分析：頻度](/help/guided-analysis/types/frequency.md)
* [ガイド付き分析：Funnel](/help/guided-analysis/types/funnel.md)
* [ガイド付き分析：コンバージョンのトレンド](/help/guided-analysis/types/conversion-trends.md)
* [ガイド付き分析：リリースの影響](/help/guided-analysis/types/release-impact.md)
* [ガイド付き分析：初回使用の影響&#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [ガイド付き分析：タイムライン](/help/guided-analysis/types/timeline.md)
* [フリーフォームテーブル&#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md)
* [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md)

## 顧客維持と顧客離れを測定

顧客維持率とは、最初の獲得とアクティベーションの後、製品とエンゲージメントし続けるユーザー数を表します。 パフォーマンスの高い製品は、継続的な使用に最も強く相関する機能とのインタラクションを最大化することで、安定したロイヤルティの高い顧客基盤を維持します。 維持しているユーザーは製品に何度も戻って操作しますが、解約したユーザーは返品しません。 製品チームは、リテンションを追跡し、継続的なエンゲージメントを促進する機能を特定し、離反したユーザーをリテンションされたユーザー行動に移行させる介入を設計します。

![&#x200B; リテンション分析](/help/guided-analysis/assets/retention.png)

Customer Journey Analyticsの次の機能は、リテンションと解約を効果的に追跡するのに役立ちます。

* [&#x200B; ガイド付き分析：保持](/help/guided-analysis/types/retention.md)&#x200B;
* [ガイド付き分析：アクティブな成長](/help/guided-analysis/types/active-growth.md)
* [ガイド付き分析：純成長](/help/guided-analysis/types/net-growth.md)
* [コホートテーブル&#x200B;](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## 実用的な製品インサイト

インサイトが価値を提供するのは、それが行動を促す場合に限られます。 分析の結果を、ユーザーエクスペリエンスを向上し、長期的な製品成長をサポートするアクションに変換します。

Adobe CX Enterpriseでは、次の機能を利用して、インサイトを効果的に活用できます。

* Customer Journey Analyticsからアクティブ化する[&#x200B; オーディエンスを作成して公開](/help/components/audiences/publish.md)&#x200B;
* CX Enterprise製品を通じてオーディエンスをアクティベーション：
   * [AJOとAdobe Targetで実験](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment)を実行し、[実験パネル &#x200B;](/help/analysis-workspace/c-panels/experimentation.md)を使用してCustomer Journey Analyticsのバリエーションの影響を測定します
   * [AJOのユーザーにアプリ内エンゲージメントを配信](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/in-app/get-started-in-app)
* Adobe Real-time CDPで[&#x200B; オーディエンスを外部宛先にアクティベート &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/activation-overview)&#x200B;

## 組織全体でインサイトを共有&#x200B;

チーム全体で重要な知見を共有し、取り組みを調整して、コラボレーションを促進し、全員が共有された製品およびビジネス目標に向かって作業できるようにします。

![Workspaceのガイド付き分析](assets/guided-analysis-workspace.png)

Adobe Customer Journey Analyticsでは、次の機能を利用して、インサイトを効果的に共有できます。

* [Share](/help/analysis-workspace/curate-share/share-projects.md)は、特定のビジネス上の質問に合わせたガイド付き分析ビューを提供し、消費者が次の質問をセルフサービスで行えるようにします
* ガイド付き分析、パネル、ビジュアライゼーションを[Analysis Workspace](/help/analysis-workspace/home.md)の包括的なダッシュボードに組み合わせる
* [&#x200B; モバイルスコアカード &#x200B;](/help/mobile-app/home.md)を、経営陣やその他の外出先の消費者向けに主要な製品インサイトとともに作成します
