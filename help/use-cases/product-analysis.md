---
title: Customer Journey Analyticsの製品分析
description: Customer Journey Analytics内で製品分析を効果的に実行するために使用できる機能について説明します。
source-git-commit: aa7b73db10e81a96f532eedf09091109209124c0
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 1%

---

# Customer Journey Analyticsの製品分析

製品分析は、ジャーニーのすべての段階で、ユーザーが製品とどのようにやり取りするかを理解するプロセスです。 データを分析して、ユーザーの行動、製品のパフォーマンス、成長の機会に関するインサイトを明らかにする必要があります。 効果的な製品分析は、チームが十分な情報に基づいた意思決定を行い、ユーザーエクスペリエンスを向上させ、エンゲージメントを促進し、ビジネス目標を達成するのに役立ちます。

Customer Journey Analyticsは、次の機能を備えた製品エクスペリエンスを分析および最適化するツールをチームに提供します。

* **製品データの大規模な管理**：ビジネスニーズに合わせて製品データを簡単に取り込み、変換および管理し、信頼性の高いインサイトを確保します。
* **獲得とアクティベーションの測定**：新規ユーザーが製品をどのように発見し、最初の価値創出イベントにどのように関与するかを追跡します。
* **エンゲージメントと採用の測定**：ユーザーが製品ファネルを通じてどのように進歩するかを理解し、摩擦ポイントを特定し、主要機能の採用を追跡します。
* **リテンションとチャーンの測定**：時間の経過に伴うユーザーリテンションを分析し、チャーンの指標を特定して、ドロップオフを減らし、ロイヤルティを高める戦略を開発します。
* **アクション製品インサイト**：データ駆動型のインサイトを実用的な戦略に変えて、ユーザーエクスペリエンスを向上させ、持続可能な製品の成長を促進します。
* **組織とインサイトを共有**：チーム間で主な結果を伝えて取り組みを一致させ、コラボレーションを促進し、全員が共有された製品とビジネスの目標に向かって取り組んでいることを確認します。

これらの機能を活用することで、Customer Journey Analyticsは製品の可能性を最大限に引き出し、ユーザーの成功とビジネスの成功を促進するためのシームレスでデータ駆動型のアプローチを作成できます。

## 製品データの大規模な管理

正確な製品データは、効果的な製品分析の基礎です。 データ取り込みは、製品データのインストルメントと収集のプロセスを指しますが、データ管理では、分析要件を確実に満たすように、このデータを変換して維持する必要があります。

Adobe Experience PlatformとCustomer Journey Analyticsの次の機能を使用すると、商品データを大規模に取り込み、管理できます。

* Adobe Experience Platform
   * [ データセット&#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)
   * [ データ準備&#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/data-prep/home)
   * [ データDistiller&#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
   * [接続&#x200B;](/help/connections/overview.md)
   * [ 派生フィールド ](/help/data-views/data-views.md) を含む [ データビュー&#x200B;](/help/data-views/derived-fields/derived-fields.md)
   * [セグメント&#x200B;](/help/components/filters/filters-overview.md)
   * [計算指標](/help/components/calc-metrics/calc-metr-overview.md)
   * [ガイド付き分析&#x200B;：タイムライン&#x200B;](/help/guided-analysis/types/timeline.md)

## 獲得とアクティブ化を測定

製品の成長は、新規ユーザーを引き付け、コンバージョンパスを明らかにし、ジャーニーの過程での摩擦を排除する、実用的なファネルの上位インサイトに左右されます。

* 獲得では、製品を使用する新規ユーザーを、その到着方法や最も効果が高い取り組みや効果が低い取り組みを含めて追跡します。
* アクティベーションは、特定の目標に従って定義された、最初の価値イベントに関与する新しいユーザーを監視します。

Customer Journey Analyticsの次の機能を使用すると、獲得とアクティベーションの両方を効果的に測定できます。

* [ガイド付き分析&#x200B;: アクティブな成長](/help/guided-analysis/types/active-growth.md)
* [ガイド付き分析：純成長率](/help/guided-analysis/types/net-growth.md)
* [ガイド付き分析：トレンド](/help/guided-analysis//types/trends.md)
* [属性パネル&#x200B;](/help/analysis-workspace/c-panels/attribution.md)
* マーケティングチャネルディメンションを含む [ フリーフォームテーブル ](/help/analysis-workspace/c-panels/freeform-panel.md) （[ 派生フィールドを使用して作成 ](/help/data-views/derived-fields/derived-fields.md)）

## エンゲージメントと採用の測定

新しいユーザーを獲得することで、製品ファネルの上部が拡張されます。 エンゲージメントは、これらのユーザーをファネルの先まで導き、成功への障害を取り除くことに焦点を当てています。 彼らの成功は、ビジネスの成功を直接推進します。

Customer Journey Analyticsの次の機能を使用して、製品のエンゲージメントと採用を追跡できます。

* [ガイド付き分析：エンゲージメント](/help/guided-analysis/types/engagement.md)
* [ガイド付き分析：トレンド](/help/guided-analysis/types/trends.md)
* [ガイド付き分析：頻度](/help/guided-analysis/types/frequency.md)
* [ガイド付き分析：ファネル](/help/guided-analysis/types/funnel.md)
* [ガイド付き分析：コンバージョンのトレンド](/help/guided-analysis/types/conversion-trends.md)
* [ガイド付き分析：リリースの影響](/help/guided-analysis/types/release-impact.md)
* [ガイド付き分析：初回使用時の影響&#x200B;](/help/guided-analysis/types/first-use-impact.md)
* [ガイド付き分析：タイムライン](/help/guided-analysis/types/timeline.md)
* [フリーフォームテーブル&#x200B;](/help/analysis-workspace/c-panels/freeform-panel.md)
* [フロー](/help/analysis-workspace/visualizations/c-flow/flow.md)

## リテンションとチャーンの測定

リテンションは、最初の獲得とアクティベーションの後に、製品に引き続きエンゲージするユーザーの数を測定します。 高性能な製品は、継続的な使用に最も強く関連する機能とのインタラクションを最大化することで、安定した忠実なユーザーベースを維持します。 保持ユーザーは時間の経過と共に製品に戻ってやり取りしますが、チャーンされたユーザーは戻りません。 製品チームは、リテンションを追跡して、継続的なエンゲージメントを促進する機能を特定し、チャーンしたユーザーをリテンションされたユーザー行動にシフトする設計介入を追跡します。

Customer Journey Analyticsの次の機能は、リテンションとチャーンを効果的に追跡するのに役立ちます。

* [ ガイド付き分析：リテンション ](/help/guided-analysis/types/retention.md)&#x200B;
* [ガイド付き分析：能動的な成長](/help/guided-analysis/types/active-growth.md)
* [ガイド付き分析：純成長率](/help/guided-analysis/types/net-growth.md)
* [コホートテーブル&#x200B;](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## 実用的な製品インサイト

インサイトは、行動を促す場合にのみ価値を提供します。 分析結果を、ユーザーエクスペリエンスを向上させ、製品の長期的な成長をサポートするアクションに変換します。

Experience Cloud内の次の機能を使用すると、インサイトに基づいて効果的に行動できます。

* [ オーディエンスを作成して公開 ](/help/components/audiences/publish.md)&#x200B;Customer Journey Analyticsからアクティブ化
* Experience Cloud製品を通じてオーディエンスをアクティブ化：
   * AJOおよびAdobe Targetで [ 実験を実行 ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) し、[ 実験パネルを使用してCustomer Journey Analyticsのバリエーションの影響を測定 ](/help/analysis-workspace/c-panels/experimentation.md)
   * AJOのユーザーに [ アプリ内エンゲージメントの配信 ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/channels/in-app/get-started-in-app) を提供する
* Adobe Real-time CDP を使用した、外部宛先への [ オーディエンスのアクティブ化 ](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/activate/activation-overview)&#x200B;

## 組織にインサイトを共有&#x200B;

チーム間で主な結果を伝え、取り組みを一致させ、コラボレーションを促進し、全員が共有された製品とビジネスの目標に向かって確実に取り組めるようにします。

Customer Journey Analyticsの次の機能を使用すると、インサイトを効果的に共有できます。

* 特定のビジネス上の質問に合わせたガイド付き分析ビューを [ 共有 ](/help/analysis-workspace/curate-share/share-projects.md) し、消費者が次の質問をセルフサービスで提供できるようにします
* ガイド付き分析、パネル、ビジュアライゼーションを、[Analysis Workspaceの包括的なダッシュボードに組み合わせ ](/help/analysis-workspace/home.md) す。
* エグゼクティブや外出先で使用する他の消費者向けに、主要な製品インサイトを備えた [ モバイルスコアカード ](/help/mobile-app/home.md) を作成します
