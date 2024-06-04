---
description: Customer Journey Analyticsドキュメントを確認する方法
title: Adobe Customer Journey Analyticsの AI アシスタント
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: fb9b0d2c8d2333aba83598ab1e1aea2370636002
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 0%

---


# Adobe Customer Journey Analyticsの AI アシスタント

>[!NOTE]
>
>Customer Journey Analytics用 AI アシスタントは現在ベータ版です。 機能とそのドキュメントは変更される場合があります。

AI アシスタントは、概念の理解、問題のトラブルシューティング、情報の検索など、実務担当者が迅速にタスクを実行できる対話型エクスペリエンスです。 また、エキスパートでないユーザーでも専門的なタスクを実行できるため、全体的な作業の質が向上します。

Customer Journey Analyticsの AI アシスタントは、Adobe Experience Leagueのドキュメントでトレーニングを受けます。 質問すると、AI アシスタントは迅速な学習を可能にする便利な回答で応答します。

初心者ユーザーであれば、AI アシスタントを使用してCustomer Journey Analyticsのコンセプトを学習し、なじみのない製品や機能に自分をオンボーディングできます。 経験豊富なユーザーは、AI アシスタントを使用して、より高度なユースケースやヒントやテクニックを提示できます。

概念に関する質問の例を次に示します。

* バッチ取得とストリーミング取得の違いは何ですか。
* Customer Journey Analyticsの用途を教えてください。
* データビューを設定するにはどうすればよいですか？

Adobe TargetやAdobe Creative Cloudスイートなど、他のAdobe製品に関する質問など、Customer Journey Analytics範囲外の質問には回答できません。

Customer Journey Analytics用 AI アシスタントは、すべての製品層で使用できます。

## 製品に関する知識 {#knowledge}

Customer Journey Analyticsに基づいて商品ナレッジ取得モデルをトレーニングする。 データ分析などのその他の機能は、後日展開される予定です。

| 製品に関する知識 | 例 |
| --- | --- |
| 先を見越した学習 | <ul><li>Adobe AnalyticsとCustomer Journey Analyticsの違いは何ですか？</li><li>計算指標の作成方法</li></ul> |
| 検出を開く | <ul><li>ワークスペースプロジェクトを書き出すにはどうすればよいですか？</li><li>重複する Workspace コンポーネントを見つけるにはどうすればよいですか？</li></ul> |
| トラブルシューティング | <ul><li>データが CJA に取り込まれるまでにどのくらい時間がかかりますか？</li><li>Customer Journey Analytics接続に含めることができる派生フィールドはいくつですか？</li></ul> |

## 機能へのアクセス

この最初のリリースでは、AI アシスタント機能へのアクセスは、次のパラメータによって制御されます。

* **ソリューションへのアクセス**:AI アシスタントはCustomer Journey Analyticsでは使用できますが、Adobe Analyticsでは使用できません。 また、Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDPやその他のExperience Platformアプリでも使用できます。

* **契約によるアクセス**:AI アシスタントを使用できない場合は、組織の管理者またはAdobeアカウント担当者にお問い合わせください。 AI アシスタントを組織で使用する前に、会社は GenAI 関連の特定の法的条項に同意する必要があります。

* **権限**：の [!UICONTROL Adobe Admin Console], [!UICONTROL レポートツール] 「AI アシスタント：製品ナレッジ」権限により、このツールへのアクセスが決定します。
A [製品プロファイル管理者](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html) は、Admin Consoleで次の手順に従う必要があります。
   1. に移動します。 [!UICONTROL Admin Console] > [!UICONTROL 製品とサービス] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL 製品プロファイル] > [!UICONTROL 権限] > [!UICONTROL レポートツールを編集].
   1. 「AI アシスタント：製品に関する知識」を追加します。

## Customer Journey AnalyticsUI で AI アシスタントにアクセスする

1. AI アシスタントを起動するには、Customer Journey AnalyticsUI の任意のページの上部ヘッダーから「AI アシスタント」アイコンを選択します。

   ![AI アシスタント アイコン](assets/ai-asst1.png)

   AI アシスタントを初めて使用する際には、アシスタントの使用条件に関する免責事項が表示されます。

1. 表示されたボックスで、AI アシスタントの特定の自然言語の質問をします。

   ![質問ボックス](assets/ai-asst2.png)

1. （オプション）ソースを表示するには、 **[!UICONTROL ソースを表示]**、および回答に情報を提供したドキュメントソース（1 つまたは複数）が表示されます。

1. （任意）回答の有用性について、サムズアップまたはサムズダウンの投票を提供することもできます。
