---
description: AEP Customer AI と CJA の Workspace の統合方法を説明します。
title: 顧客 AI と CJA の統合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 5d22437ec6514196146283af311b6661c1f2e45b
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 9%

---

# 顧客 AI と CJA の統合

>[!NOTE]
>
>この機能は 2022 年 5 月 25 日にリリースされます。

[顧客 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)は、Adobe Experience Platform Intelligent Services の一部として、マーケターに対して、個々のレベルで顧客予測を生成する力を提供します。

顧客 AI は、影響力のある要因の助けを借りて、顧客が何をする可能性があるかとその理由を知ることができます。さらに、マーケターは、顧客 AI の予測と洞察を活用して、最も適切なオファーとメッセージを提供することで、顧客のエクスペリエンスをパーソナライズできます。

顧客 AI は、次の 1 つ以上のデータセットを分析して、傾向スコアの変化やコンバージョン傾向スコアを予測します。

* Analytics ソースコネクタを使用したAdobe Analyticsデータ
* Adobe Audience Managerソースコネクタを使用したAudience Managerデータ
* エクスペリエンスイベント (EE) データセット
* 消費者エクスペリエンスイベント (CEE) データセット

顧客 AI はCustomer Journey Analytics(CJA) と統合され、顧客 AI が有効なデータセットを CJA のデータビューおよびレポートで利用できる範囲です。

## ワークフロー

一部の手順は、CJA での出力を操作する前に、Adobe Experience Platformで実行されます。

### 手順 1:顧客 AI インスタンスの設定

データを準備し、すべての資格情報とスキーマを設定したら、次の手順に従って開始します。 [顧客 AI インスタンスの設定](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) ガイド。

### 手順 2:顧客 AI データセットへの CJA 接続の設定

CJA で、次の操作を実行できます。 [1 つ以上の接続を作成](/help/connections/create-connection.md) を、顧客 AI に実装されたExperience Platformデータセットに追加しました。 これらのデータセットは、次に示すように、「顧客 AI スコア」プレフィックスで表示されます。

![CAI スコア](assets/cai-scores.png)

「アカウントをアップグレードする可能性」などの各予測は、1 つのデータセットと同じです。

次に、CJA が既存または新しいデータセットの一部として取り込む XDM スキーマの例を示します。

![CAI スキーマ](assets/cai-schema.png)

( この例はプロファイルデータセットです。同じスキーマオブジェクトのセットは、CJA が取得するエクスペリエンスイベントデータセットの一部になります。 エクスペリエンスイベントデータセットには、スコアの日付としてタイムスタンプが含まれます )。 このモデルでスコアリングされたすべての顧客には、スコア、scoreDate などが割り当てられます。 と関連付けられています。

### 手順 3:これらの接続に基づくデータビューの作成

CJA で、次に進むことができます。 [データビューを作成](/help/data-views/create-dataview.md) を設定します。

### 手順 4:Workspace での CAI スコアのレポート

次に、積み重ね棒グラフでスコア日を表示する CAI データを含む Workspace プロジェクトの例を示します。

![スコアバケット](assets/workspace-scores.png)

