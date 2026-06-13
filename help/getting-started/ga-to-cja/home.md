---
title: Google Analytics 4からCustomer Journey Analyticsへの移行
description: Google Analytics 4に精通しているアナリスト向けに、Customer Journey Analyticsでレポートを取得するための主要な概念について説明します。
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: 3d7c8b91-f2a4-4e6b-9c1d-5f8e3a720469
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 046df00868ca4a5b3bab3eb36cca7d91b141333a
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 3%

---


# Google Analytics 4からCustomer Journey Analyticsへの移行

このガイドでは、Google Analytics 4について詳しいアナリストが、Adobe Customer Journey Analyticsで同等の概念とレポートを学ぶのに役立ちます。 レポートではなく技術的な実装を担当する場合は、Web SDKの設定とデータ取り込みに関するガイダンスについては、[&#x200B; サードパーティ分析ソリューションからCustomer Journey Analyticsへのアップグレード &#x200B;](../cja-upgrade/cja-upgrade-third-party-solution.md)を参照してください。 既存のGoogle Analytics データをAdobe Experience Platformに移行する必要がある場合は、[Google Analyticsからのデータの移行](/help/use-cases/third-party/ga/overview.md)を参照してください。

## GA4とCustomer Journey Analyticsの主な違い

Adobe GA4とAdobe Customer Journey Analyticsは、同様の基本理念を持っています。あらゆる顧客とのやり取りはイベントであり、分析はブランクキャンバスツールで実行されます。ドラッグ&amp;ドロップ操作でディメンションと指標を設定し、カスタムビューを構築できます。 GA4 Exploreをご存知の方なら、Analysis Workspaceはすぐに認知可能になります。

最も大きな違いは、Customer Journey AnalyticsがGA4にとどまらない点です。

* **クロスチャネルデータ**: Customer Journey Analyticsは、web分析をオフラインのデータソース（コールセンターのレコード、CRM アクティビティ、ロイヤルティプログラム、メールエンゲージメントなど）と同じ分析で組み合わせることができます。 GA4は、SDKを通じて収集したデジタルインタラクションに限定されます。
* **レポート時処理**: Customer Journey Analyticsは、アトリビューションモデル、セッション定義、セグメントルールなどのロジックを、収集時ではなくクエリ時に適用します。 セッション定義やアトリビューションモデルに加えられた変更は、再処理することなく、すべての履歴データに過去にさかのぼって適用されます。
* **柔軟なセッション定義**: セッションタイムアウト時間、セッション開始イベント、セッション終了イベントはすべて、Customer Journey Analyticsのデータビューごとに設定可能です。 GA4のセッションタイムアウトは調整可能（デフォルトでは30分、最大7時間55分）ですが、プロパティ全体に適用され、セッション開始とセッション終了の動作が修正されます。
* **IDの合成**: Customer Journey Analyticsのステッチング機能を使用すると、クロスデバイスおよびクロスチャネルのインタラクションを同じ人物にリンクできるため、GA4のブレンド ID モデルよりも正確な人物数を生成できます。

## アカウントとデータ構造

GA4とCustomer Journey Analyticsでは、プラットフォームレベルでデータの整理が異なります。

| GA4 | Customer Journey Analytics |
|---|---|
| Google アカウント | Adobe IMS組織 |
| プロパティ | 接続+ データビュー |
| データストリーム | Platformの[!UICONTROL &#x200B; イベントデータセット &#x200B;] |
| データフィルター | データビューコンポーネントフィルター |
| サブプロパティ | フィルターを適用した個別のデータビュー |
| ロールアッププロパティ | 複数のデータセットを組み合わせた接続 |

最も重要な構造的な違いは、GA4 プロパティがデータ配線とレポートの両方を単一のオブジェクトとして処理することです。 Customer Journey Analyticsでは、これらのコンセプトを2つのレイヤーに分けています。

* **connection**&#x200B;は、1つ以上のAdobe Experience Platform データセットをCustomer Journey Analyticsにリンクします。 このステップでは、レポート用に最適化されたフォーマットでCustomer Journey Analyticsにデータを取り込みます。
* **データビュー**&#x200B;は、接続の上に構築され、レポートに使用できるディメンション、指標、設定を定義します。 これはレポート設定レイヤーです。

Customer Journey Analyticsでデータを分析する前に、両方が必要です。 Customer Journey Analyticsにはレポートスイートがありません。

## Analysis Workspace入門

GA4のExploreとAnalysis Workspaceは、どちらもブランクキャンバスのドラッグ&amp;ドロップ操作の分析ツールです。 インタラクションモデルは同じですが、用語が少し異なります。

| GA4の詳細 | Analysis Workspace |
|---|---|
| 探索キャンバス | パネル |
| グラフまたはビジュアライゼーションタイプ | ビジュアライゼーション |
| ディメンション | ディメンション |
| 指標 | 指標 |
| セグメントまたはフィルター | セグメント |
| イベント数 | [!UICONTROL イベント] |
| ユーザー | [!UICONTROL 人物] |
| Sessions | [!UICONTROL セッション] |

>[!TIP]
>
>GA4のセグメントコンテナには、ユーザー、セッション、イベントという名前が付けられています。 Customer Journey Analyticsでは、同等のコンテナは&#x200B;**[!UICONTROL Person]**、**[!UICONTROL Session]**、**[!UICONTROL Event]**&#x200B;です。 スコーピングロジックは同じです。

>[!MORELIKETHIS]
>
>* [Google Analyticsからのデータの移行](/help/use-cases/third-party/ga/overview.md)
