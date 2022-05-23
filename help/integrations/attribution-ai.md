---
description: AEPAttribution AIを CJA で Workspace と統合する方法を説明します。
title: Attribution AIと CJA の統合
role: Admin
solution: Customer Journey Analytics
exl-id: 5ab563b9-d4f6-4210-8789-e16e5c93d968
source-git-commit: acfa4086c525ed78b52e430c110ec1daca9d20a5
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 4%

---

# Attribution AIと CJA の統合

>[!NOTE]
>
>この機能は 2022 年 5 月 25 日にリリースされます。

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en)は、Adobe Experience Platformインテリジェントサービスの一部で、指定した結果に対する顧客とのやり取りの影響と増分的な影響を計算する、マルチチャネルのアルゴリズムアトリビューションサービスです。 マーケターは、Attribution AIジャーニーの各段階における個々の顧客インタラクションの影響を把握することで、マーケティング費用と広告費用を測定し、最適化できます。

Attribution AIは、次の 2 つのカテゴリのスコアをサポートします。アルゴリズムとルールベースの両方を使用できます。 アルゴリズムスコアには、増分スコアと影響スコアが含まれます。

* **影響スコア** マーケティングチャネル間でコンバージョンクレジットの 100%を配分します。
* **増分スコア** まず、マーケティングを行わなくても達成できたコンバージョンベースラインを考慮します。 このベースラインは、既存のブランド認知度、忠誠度、口コミによるパターンや季節性などの AI による観測に依存します。 残りのクレジットはマーケティングチャネルに分割されます。

ルールベーススコアには、以下が含まれます [!UICONTROL ファーストタッチ], [!UICONTROL ラストタッチ], [!UICONTROL 線形], [!UICONTROL U 字形]、および [!UICONTROL タイムディケイ]. Attribution AIは、次の 3 つのExperience Platformスキーマをサポートします。エクスペリエンスイベント、Adobe Analytics、および消費者エクスペリエンスイベント。

Attribution AIはCustomer Journey Analytics(CJA) と統合され、Attribution AIに対してモデルが実行され、CJA がこれらのモデルの出力をデータセットとして読み込むので、他の CJA データセットと統合できます。 Attribution AIが有効なデータセットは、CJA のデータビューとレポートで利用できます。

## ワークフロー

一部の手順は、CJA での出力を操作する前に、Adobe Experience Platformで実行されます。 出力は、適用されたデータモデルを持つAttribution AIセットで構成されます。

### 手順 1:Attribution AIインスタンスの作成

Experience Platformで、Attribution AIを選択してマッピングし、イベントを定義し、データをトレーニングすることで、データインスタンスを作成します（説明を参照） [ここ](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### 手順 2:Attribution AIセットへの CJA 接続の設定

CJA で、次の操作を実行できます。 [1 つ以上の接続を作成](/help/connections/create-connection.md) を、Attribution AI用に実装されたExperience Platformセットに追加しました。 これらのデータセットは、次に示すように、「Attribution AIスコア」プレフィックスで表示されます。

![AAI スコア](assets/aai-scores.png)

### 手順 3:これらの接続に基づくデータビューの作成

CJA では、 [1 つ以上のデータビューを作成する](/help/data-views/create-dataview.md) Attribution AIXDM フィールドを含む （ここにスクリーンショットを表示すると便利です）。

### 手順 4:CJA Workspace での AAI データのレポート

CJA Workspace プロジェクトでは、「AAI 注文」などの指標や、「AAI キャンペーン名」や「AAI マーケティングチャネル」などのディメンションを取り込むことができます。

![AAI ディメンション](assets/aai-dims.png)

AAI データを含む Workspace プロジェクトが表示され、影響スコアと増分スコアを含む注文が示されます。 任意のディメンションにドリルダウンして、次の方法でアトリビューションを理解します。キャンペーン、製品グループ、ユーザーセグメント、地域など。

![AAI プロジェクト](assets/aai-project.png)

![AAI プロジェクト](assets/aai-project2.png)

チャネルのインタラクションを理解して、他のチャネルと最も効果的に使用できるチャネルを確認します。

![マーケティングチャネルの重複](assets/mc-overlap.png)

次の表に、タッチポイントの設計と最適化に役立つ、コンバージョン（重複排除）への上位のパスを示します。

![上位チャネル](assets/top-channels.png)

ここでは、タッチポイントがミックスに含まれる場合のコンバージョンへのリードタイムを確認します。 リードタイムの最適化に役立ちます。

![リードタイム](assets/lead-time.png)

## 新しい CJA 指標

| 指標 | 説明 |
| --- | --- |
| [!UICONTROL 獲得率] | 各チャネルについて、タッチしたコンバージョンパスのうち、チャネルがスターターの割合です。 |
| [!UICONTROL プレーヤー率] | 各チャネルについて、タッチしたコンバージョンパスの中で、チャネルのプレーヤーである割合。 |
| [!UICONTROL クローザー率] | 各チャネルについて、タッチしたコンバージョンパスの中で、チャネルのクローザー率が表されます。 |
| [!UICONTROL AAI 平均発注日数] | 各チャネルについて、注文からの平均日数。 |
| [!UICONTROL AAI 平均販売プロセスの合計日数] | 各チャネルについて、タッチしたコンバージョンパスの平均合計日数。 |
| [!UICONTROL 平均タッチで注文を回避] | 各チャネルでの平均タッチ数は、順序から遠くなります。 |

## Attribution AIとAttribution IQの違い

したがって、Attribution AIデータを使用するタイミングと [Attribution IQ](/help/analysis-workspace/attribution/overview.md)、ネイティブの CJA 機能？ 次の表に、機能の違いを示します。

| 機能 | アトリビューション AI | Attribution IQ |
| --- | --- | --- |
| 分数の属性を含む | ○ | × |
| ユーザーがモデルを調整できるようにします | ○ | ○ |
| チャネルをまたいで属性を設定します ( 注意：AAI は、CJA と同じステッチ済みデータを使用しません )。 | ○ | ○ |
| 増分スコアと影響スコアが含まれます | ○ | × |
| ML モデリングを実行 | ○ | ○ |
| 予測を使用した ML モデリングの実行 | ○ | × |

{style=&quot;table-layout:auto&quot;}
