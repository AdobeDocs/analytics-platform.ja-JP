---
description: Customer Journey Analyticsドキュメントを確認する方法
title: Adobe Customer Journey Analytics 向けの AI アシスタント
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
source-git-commit: 20b578a6269aeaf54f6296b1f4337937887ecf05
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 2%

---


# Adobe Customer Journey Analytics 向けの AI アシスタント

AI アシスタントは、実務担当者が迅速にタスクを実行できる会話経験です。 タスクが、概念の理解、問題のトラブルシューティング、情報の検索のいずれを目的としているか。 また、AI アシスタントを使用すると、エキスパートでないユーザーでも専門的なタスクを実行でき、作業の全体的な品質を向上させることができます。

Customer Journey Analyticsの AI アシスタントは、Adobe Experience Leagueのドキュメントでトレーニングを受けます。 質問すると、AI アシスタントは迅速な学習を可能にする便利な回答で応答します。

初心者ユーザーであれば、AI アシスタントを使用してCustomer Journey Analyticsのコンセプトを学習し、なじみのない製品や機能に自分をオンボーディングできます。 経験豊富なユーザーは、AI アシスタントを使用して、より高度なユースケースやヒントやテクニックを提示できます。

概念に関する質問の例を次に示します。

* バッチ取得とストリーミング取得の違いは何ですか。
* Customer Journey Analyticsの用途を教えてください。
* データビューを設定するにはどうすればよいですか？

Adobe TargetやAdobe Creative Cloudスイートなど、他のAdobe製品に関する質問など、Customer Journey Analytics範囲外の質問には回答できません。

Customer Journey Analytics用 AI アシスタントは、すべての製品層で使用できます。

## 製品に関する知識 {#knowledge}

Customer Journey Analyticsに基づいて商品ナレッジ取得モデルをトレーニングする。 データ分析などのその他の機能は、後で展開されます。

| 製品に関する知識 | 例 |
| --- | --- |
| 先を見越した学習 | <ul><li>Adobe AnalyticsとCustomer Journey Analyticsの違いは何ですか？</li><li>計算指標の作成方法</li></ul> |
| 検出を開く | <ul><li>Workspace プロジェクトを書き出すにはどうすればよいですか？</li><li>重複するWorkspace コンポーネントを見つけるにはどうすればよいですか？</li></ul> |
| トラブルシューティング | <ul><li>データが CJA に取り込まれるまでにどのくらい時間がかかりますか？</li><li>Customer Journey Analytics接続に含めることができる派生フィールドはいくつですか？</li></ul> |

## 機能へのアクセス

次のパラメータは、AI アシスタント機能へのアクセスを制御します。

* **ソリューションアクセス**:AI Assistant はCustomer Journey Analyticsでは使用できますが、Adobe Analyticsでは使用できません。 また、Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDPやその他のExperience Platformアプリでも使用できます。

* **契約によるアクセス**:AI アシスタントを使用できない場合は、組織の管理者またはAdobeアカウント担当者にお問い合わせください。 組織が AI アシスタントを使用する前に、GenAI 関連の特定の法的条項に同意する必要があります。

* **権限**:[!UICONTROL Adobe Admin Console] では、[!UICONTROL  レポートツール ]**[!UICONTROL AI アシスタント：製品ナレッジ]** 権限によってこのツールへのアクセスが決まります。 [ 製品プロファイル管理者 ](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html) は、[!UICONTROL Admin Consoleの次の手順に従う必要があり ] す。
   1. **[!UICONTROL Admin Console]** / **[!UICONTROL 製品およびサービス]** / **[!UICONTROL 製品]** / **[!UICONTROL Customer Journey Analyticsプロファイル]** に移動します
   1. [!UICONTROL AI アシスタント：製品ナレッジ ] へのアクセスを提供する製品プロファイルのタイトルを選択します。
   1. 特定の製品プロファイルで、「**[!UICONTROL 権限]**」を選択します。
   1. ![ 編集 ](/help/assets/icons/Edit.svg) を選択して **[!UICONTROL レポートツール]** を編集します。
   1. ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して **AI Assistant: Product Knowledge** を **[!UICONTROL 含まれる権限項目]** に追加します。

      ![ 権限を追加 ](assets/ai-assistant-permissions.png).

   1. 「**[!UICONTROL 保存]**」を選択して、権限を保存します。

詳しくは、[ アクセス制御 ](/help/technotes/access-control.md#access-control) を参照してください。

## Customer Journey AnalyticsUI で AI アシスタントにアクセスする

1. AI アシスタントを起動するには、Customer Journey AnalyticsUI の任意のページの上部ヘッダーから「AI アシスタント」アイコンを選択します。

   ![AI アシスタント アイコン ](assets/ai-asst1.png)

   AI アシスタントを初めて使用する際には、アシスタントの使用条件に関する免責事項が表示されます。

1. 表示されたボックスで、AI アシスタントの特定の自然言語の質問をします。

   ![ 質問ボックス ](assets/ai-asst2.png)

1. （任意）ソースを表示するには、「**[!UICONTROL ソースを表示]**」をクリックします。回答に情報を提供したドキュメントソース（1 つまたは複数）が表示されます。

1. （任意）回答の有用性について、サムズアップまたはサムズダウンの投票を提供することもできます。

1. （任意）不適切なコンテンツや有害なコンテンツに対して回答にフラグを付けることができます。
