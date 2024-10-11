---
title: Target レポート
description: Adobe TargetとCustomer Journey Analyticsの統合
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
source-git-commit: 979564d0249abadd454ce43aba9aeae2c78a44f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 41%

---

# Target レポート

Customer Journey Analyticsの Target レポートを使用すると、Adobe Target アクティビティをCustomer Journey Analyticsで直接測定およびレポートできます。 この機能は、Analytics for Target （A4T）を介してAdobe Analytics（AA）で実行される機能と同等ですが、Adobe Experience Platform（AEP）への接続も備えています。

Target 分類ルックアップデータセット（デフォルトではExperience PlatformCustomer Journey Analyticsで使用できます）を Target Connection に追加することで、Target レポートツール、Target オーダーアトリビューション、その他の機能を適切に利用できるようになります。 Customer Journey Analyticsデータビュー内で行われた軽微な準備と調整のみで、これらのアクティビティは、Target データを CJA に直接送信したいユーザーが直ちに利用できるようになります。

## プライマリの利点

* マーケターは、Customer Journey Analytics の成功指標を Target アクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要がありません。
* マーケターは、実験パネルなどの Customer Journey Analytics 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、Adobe Journey Optimizer と Target に単一のレポートソースを使用できます。どちらのパーソナライゼーション製品も Customer Journey Analytics に接続して、web パーソナライズ機能の全体像を把握できます。

## メモと考慮事項

ターゲット分類イベントデータセットが CJA 接続に追加されたら、これらのコンポーネントがディメンションとして追加された後、CJA データビュー内で次のような小規模な調整がいくつか行われます。

* 永続性を Target での追跡方法と同様に設定します（適切な設定を確認するには、Target のコンサルタントまたは顧客にお問い合わせください）。

* 永続性をすべて設定します。これにより、複数の Target アクティビティを同時に追跡し、今後または以前のアクティビティで上書きしないようにすることができます。

## 詳細情報

詳しくは、Target ドキュメントの [Adobe Customer Journey Analytics での Target レポート](https://experienceleague.adobe.com/ja/docs/target/using/integrate/cja/target-reporting-in-cja)を参照してください。

アナリストが様々なユーザーエクスペリエンス、マーケティングまたはメッセージングのバリエーションを比較して、特定の結果を導くの最適なのはどれかを判断する方法について詳しくは、[実験パネル](../analysis-workspace/c-panels/experimentation.md)を参照してください。A/B 実験の上昇率と信頼性は、Target や Journey Optimizer などのアドビのソリューション、BYO（bring-your-own）データなど、オンラインまたはオフラインのあらゆる実験プラットフォームで評価できます。
