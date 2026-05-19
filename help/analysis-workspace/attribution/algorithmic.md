---
title: アルゴリズムアトリビューション
description: アルゴリズムアトリビューションモデルの詳細を理解します。
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 42%

---

# アルゴリズムアトリビューション

Analysis Workspace のアルゴリズム[アトリビューションモデル](models.md)は、統計的な手法を使用して、レポートまたはフリーフォームテーブルのディメンション項目にクレジットを割り当てるという点で、他のモデルとは異なります。 Analysis Workspaceの他のすべてのアトリビューションモデルと同様に、アルゴリズムによるアトリビューションは、あらゆるディメンションや指標で利用できます。 アルゴリズムアトリビューションでは、無制限のセグメンテーションと分類がサポートされ、コンバージョンの100%がテーブル内の1つ以上のディメンション（「分数」アトリビューションとも呼ばれます）に分布されます。

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

アトリビューションに使用されるアルゴリズムは、協同ゲーム理論のハルサニ配当に基づきます。 Harsanyiの配当金は、結果に不平等な貢献を持つゲームのプレイヤー間で信用を分配するためのShapleyの価値ソリューションの一般化（Lloyd Shapley、ノーベル賞経済学者にちなんで名付けられた）です。

各タッチポイントに対するコンバージョンクレジットのアトリビューション計算では、ルックバックウィンドウ内の各マーケティングタッチポイントをプレイヤーの連合と見なします。 その連立候補には、利益が公平に分配されなければならない。 各連合の黒字配分は、各連合が以前に再帰的に作成した黒字から決定されます。

詳しくは、John HarsanyiとLloyd Shapleyのオリジナルの論文を参照してください。

* シェイプリー、ロイド S。 (1953). n 人用ゲームの値 *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi、ジョン C。 (1963). n 人用協力ゲームのシンプル版安価モデル。 *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>アルゴリズムアトリビューションの結果は、特定のルックバックウィンドウ内に複数のタッチポイントが存在する場合のみ、他のモデルと異なります。 単一のタッチポイントを持つコンバージョンは、アトリビューションモデルに関係なく、100%のクレジットを受け取ります。
