---
title: アルゴリズムアトリビューション
description: アルゴリズムアトリビューションモデルの詳細。
feature: Attribution
exl-id: ce174253-4864-4fb0-8a96-a134a9fc9fba
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 84%

---

# アルゴリズムアトリビューション

>[!NOTE]
>
>Customer Journey Analytics 内の Analysis Workspace に関するドキュメントを表示しています。この機能セットは、[従来の Adobe Analytics の Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=ja) とは少し異なります。[詳細情報...](/help/getting-started/cja-aa.md)

以下に、アルゴリズムアトリビューションの概要ビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/36205/?quality=12)

Analysis Workspace のアルゴリズム[アトリビューションモデル](models.md)は、統計的な手法を使用して、レポートまたはフリーフォームテーブルのディメンション項目にクレジットを割り当てるという点で、他のモデルとは異なります。Analysis Workspaceの他のすべてのアトリビューションモデルと同様に、任意のディメンションや指標で使用でき、無制限のフィルターや分類をサポートし、コンバージョンの 100%をテーブル内のディメンション（「分数」アトリビューションとも呼ばれます）に分配します。

アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。ハルサニ配当は、結果への貢献度が等しくないゲーム内のプレーヤー間でクレジットを分配するためのシャープレイ値ソリューション（ノーベル賞受賞者のエコノミスト、ロイドシャープレイにちなんで名付けられました）の一般化です。

高いレベルでは、各タッチポイントのコンバージョンクレジットのアトリビューション計算では、ルックバックウィンドウ内の各マーケティングタッチポイントを、剰余を均等に配分する必要のあるプレーヤーの連合とみなします。各連合の余剰分配は、各サブ連合（または以前に参加したディメンション項目）によって以前に再帰的に作成された余剰に従って決定されます。詳しくは、John Harsanyi と Lloyd Shapley の元の論文を参照してください。

* Shapley, Lloyd S. (1953).n 人用ゲームの値&#x200B;*Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963).n 人用協力ゲームのシンプル版安価モデル。*International Economic Review 4(2)*, 194-220.

>[!IMPORTANT]
>
>アルゴリズムアトリビューションの結果は、特定のルックバックウィンドウ内に複数のタッチポイントが存在する場合のみ、他のモデルと異なります。単一のタッチポイントを持つコンバージョンは、アトリビューションモデルに関係なく、100%のクレジットを受け取ります。
