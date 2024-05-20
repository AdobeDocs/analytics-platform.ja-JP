---
description: Customer Journey Analyticsドキュメントを確認する方法
title: Adobe Customer Journey Analyticsの AI アシスタント
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: true
hidefromtoc: true
source-git-commit: 9659ebfc267be769c7a87c01b129245c97b82a95
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---


# Adobe Customer Journey Analyticsの AI アシスタント

>[!NOTE]
>
>Customer Journey Analytics用 AI アシスタントは現在ベータ版です。 機能とそのドキュメントは変更される場合があります。

AI アシスタントは、Adobe Customer Journey Analyticsの概念や用語を移動して理解するための UI 機能です。 Customer Journey Analyticsの AI アシスタントは、Adobe Experience Leagueのドキュメントでトレーニングを受けます。 質問すると、AI アシスタントは迅速な学習を可能にする便利な回答で応答します。

初心者ユーザーであれば、AI アシスタントを使用してCustomer Journey Analyticsのコンセプトを学習し、なじみのない製品や機能に自分をオンボーディングできます。 経験豊富なユーザーは、AI アシスタントを使用して、より高度なユースケースやヒントやテクニックを提示できます。

概念に関する質問の例を次に示します。

* バッチ取得とストリーミング取得の違いは何ですか。
* Customer Journey Analyticsの用途を教えてください。
* データビューを設定するにはどうすればよいですか？

ドキュメント取得モデルは、Customer Journey Analyticsに基づいてトレーニングされます。 Adobe TargetやAdobe Creative Cloudスイートなど、他のAdobe製品に関する質問など、Customer Journey Analytics範囲外の質問には回答できません。

Customer Journey Analytics用 AI アシスタントは、すべての製品層で使用できます。

>[!IMPORTANT]
>
>現時点では、Customer Journey Analytics用 AI アシスタントは組織内のデータオブジェクトに関する使用状況の質問には回答しません。

## 機能へのアクセス

この最初のリリースでは、AI アシスタント機能へのアクセスは、次のパラメータによって制御されます。

* **ソリューションへのアクセス**:AI アシスタントはCustomer Journey Analyticsでは使用できますが、Adobe Analyticsでは使用できません。 また、Adobe Experience Platform、Adobe Journey Optimizer、Adobe Real-Time CDPやその他のExperience Platformアプリでも使用できます。

* **契約によるアクセス**:AI アシスタントを使用できない場合は、組織の管理者またはAdobeアカウント担当者にお問い合わせください。 AI アシスタントを組織で使用する前に、会社は GenAI 関連の特定の法的条項に同意する必要があります。

* **権限**：です [!UICONTROL Adobe Admin Console] [!UICONTROL レポートツール] 「AI Assistant ドキュメント」権限により、このツールへのアクセスが決まります。 この権限は、5 月中旬にレポートツール セクションに追加される予定です。 必ずを作成してください。 [製品プロファイル](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html) この権限が付与されたAdmin Consoleで、このプロファイルにユーザーを手動で追加します。

## Customer Journey AnalyticsUI で AI アシスタントにアクセスする

1. AI アシスタントを起動するには、Customer Journey AnalyticsUI の任意のページの上部ヘッダーから「AI アシスタント」アイコンを選択します。

   ![AI アシスタント アイコン](assets/ai-asst1.png)

   AI アシスタントを初めて使用する際には、アシスタントの使用条件に関する免責事項が表示されます。

1. 表示されたボックスで、AI アシスタントの特定の自然言語の質問をします。

   ![質問ボックス](assets/ai-asst2.png)

1. （オプション）ソースを表示するには、 **[!UICONTROL ソースを表示]**、および回答に情報を提供したドキュメントソースが表示されます。

1. （任意）回答の有用性について、サムズアップまたはサムズダウンの投票を提供することもできます。
