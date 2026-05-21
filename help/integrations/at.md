---
title: ターゲットレポート
description: Adobe TargetとCustomer Journey Analyticsの統合
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
TQID: https://experienceleague.adobe.com/7Q8q-e58PrmANht9DpOXuNFImYC48ELhrXPRhBG6gYQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 410
ht-degree: 44%

---

# ターゲットレポート

Customer Journey AnalyticsのTarget Reportingを使用すると、Adobe Target アクティビティをCustomer Journey Analyticsで直接測定およびレポートできます。 この機能は、Analytics for Target （A4T）を介してAdobe Analytics（AA）で実行されるものと同等ですが、Adobe Experience Platform（AEP）との接続性があります。

Target Classification ルックアップデータセット（Experience Platformでデフォルトで使用可能）をCustomer Journey Analytics Connectionに追加することで、ユーザーはTarget レポートツール、Target注文アトリビューションなどの機能を適切に利用できるようになりました。 Customer Journey Analytics データビュー内で行われたマイナーな準備と調整により、Target データをCJAに直接送信したいユーザーは、これらのアクティビティをすぐに利用できます。

## プライマリの利点

* マーケターは、Customer Journey Analytics の成功指標を Target アクティビティレポートにいつでも動的に適用できます。 アクティビティを実行する前にすべての項目を指定する必要がありません。
* マーケターは、実験パネルなどの Customer Journey Analytics 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、Adobe Journey Optimizer と Target に単一のレポートソースを使用できます。 どちらのパーソナライゼーション製品も Customer Journey Analytics に接続して、web パーソナライゼーションの全体像を把握できます。

## メモと考慮事項

Target アクティビティでは、[Customer Journey Analyticsをレポートソースとして使用する必要があります](https://experienceleague.adobe.com/ja/docs/target/using/integrate/cja/target-reporting-in-cja)。

ターゲット分類イベントデータセットが接続に追加されると、これらのコンポーネントがディメンションとして追加されると、データビュー内で次のような調整が行われます。

* 永続性をTargetでのトラッキング方法と類似するように設定します（適切な設定を確認するには、Target コンサルタントまたはお客様に確認してください）。

* 永続性をALLに設定すると、複数のTarget アクティビティを同時に追跡し、今後または以前のアクティビティで上書きしないようにできます。

## 詳細情報

詳しくは、Target ドキュメントの [Adobe Customer Journey Analytics での Target レポート](https://experienceleague.adobe.com/ja/docs/target/using/integrate/cja/target-reporting-in-cja)を参照してください。

アナリストが様々なユーザーエクスペリエンス、マーケティングまたはメッセージングのバリエーションを比較して、特定の結果を導くの最適なのはどれかを判断する方法について詳しくは、[実験パネル](../analysis-workspace/c-panels/experimentation.md)を参照してください。 A/B 実験の上昇率と信頼性は、Target や Journey Optimizer などのアドビのソリューション、BYO（bring-your-own）データなど、オンラインまたはオフラインのあらゆる実験プラットフォームで評価できます。
