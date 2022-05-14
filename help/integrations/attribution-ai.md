---
description: AEPAttribution AIを CJA で Workspace と統合する方法を説明します。
title: Attribution AIと CJA の統合
role: Admin
solution: Customer Journey Analytics
source-git-commit: e75836841cdaf8acd2408723111f13048d31505d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 11%

---

# Attribution AIと CJA の統合

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)は、Adobe Experience Platformインテリジェントサービスの一部で、指定した結果に対する顧客とのやり取りの影響と増分的な影響を計算する、マルチチャネルのアルゴリズムアトリビューションサービスです。 マーケターは、Attribution AIジャーニーの各段階における個々の顧客インタラクションの影響を把握することで、マーケティング費用と広告費用を測定し、最適化できます。

Attribution AIは、次の 2 つのカテゴリのスコアをサポートします。アルゴリズムとルールベースの両方を使用できます。 アルゴリズムスコアには、増分スコアと影響スコアが含まれます。ルールベーススコアには、ファーストタッチ、ラストタッチ、リニア、U 字形、タイムディケイが含まれます。

Attribution AIはCustomer Journey Analytics(CJA) と統合され、Attribution AIに対してモデルが実行され、CJA がこれらのモデルの出力をデータセットとして読み込むので、他の CJA データセットと統合できます。 Attribution AIが有効なデータセットは、CJA のデータビューとレポートで利用できます。

Attribution AIは、次の 3 つのExperience Platformスキーマをサポートします。エクスペリエンスイベント、Adobe Analytics、および消費者エクスペリエンスイベント。

## ワークフロー

一部の手順は、CJA での出力を操作する前に、Adobe Experience Platformで実行されます。

### Attribution AIスコアのダウンロード

1. Experience Platformで、説明に従ってAttribution AIスコアをダウンロードします。 [ここ](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).
1. Experience Platformで、Attribution AIを選択してマッピングし、イベントを定義し、データをトレーニングすることで、データインスタンスを作成します（説明を参照） [ここ](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).
1. CJA では、

## Attribution AIとAttribution IQの違い

したがって、Attribution AIデータを使用するタイミングと [Attribution IQ](/help/analysis-workspace/attribution/overview.md)、ネイティブの CJA 機能？ 次の表に、機能の違いを示します。

| 機能 | アトリビューション AI | Attribution IQ |
| --- | --- | --- |
| 分数の属性を含む | ○ | × |
| ユーザーがモデルを調整できるようにします | × | ○ |
| チャネルをまたいで属性を設定します ( 注意：AAI は、CJA と同じステッチ済みデータを使用しません )。 | ○ | ○ |
| 増分スコアと影響スコアが含まれます | ○ | × |
| ML モデリングを実行 | ○ | ○ |
| 予測を使用した ML モデリングの実行 | ○ | × |

{style=&quot;table-layout:auto&quot;}
