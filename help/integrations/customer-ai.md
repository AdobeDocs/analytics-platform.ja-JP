---
description: AEP Customer AI と CJA の Workspace の統合方法を説明します。
title: 顧客 AI と CJA の統合
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 9%

---


# 顧客 AI と CJA の統合

>[!NOTE]
>
>このページは作成中です。

[顧客 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en)は、Adobe Experience Platform Intelligent Services の一部として、マーケターに対して、個々のレベルで顧客予測を生成する力を提供します。

顧客 AI は、影響力のある要因の助けを借りて、顧客が何をする可能性があるかとその理由を知ることができます。さらに、マーケターは、顧客 AI の予測と洞察を活用して、最も適切なオファーとメッセージを提供することで、顧客のエクスペリエンスをパーソナライズできます。

顧客 AI は、次のデータセットの 1 つを分析して、傾向スコアの変化やコンバージョン傾向スコアを予測します。

* Analytics ソースコネクタを使用したAdobe Analyticsデータ
* Adobe Audience Managerソースコネクタを使用したAudience Managerデータ
* エクスペリエンスイベント (EE) データセット
* 消費者エクスペリエンスイベント (CEE) データセット

顧客 AI はCustomer Journey Analytics(CJA) と統合され、顧客 AI が有効なデータセットを CJA のデータビューおよびレポートで利用できる範囲です。

## ワークフロー

一部の手順は、CJA での出力を操作する前に、Adobe Experience Platformで実行されます。

### 手順 1:顧客 AI スコアのダウンロード

顧客 AI スコアのダウンロードは、説明に従って、Experience PlatformAPI 呼び出しの組み合わせを通じておこなわれます [ここ](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### 手順 2:顧客 AI の入力と出力の定義

このプロセスについては、 [顧客 AI での入力と出力](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) ドキュメント。

### 手順 3:顧客 AI インスタンスの設定

データを準備し、すべての資格情報とスキーマを設定したら、次の手順に従って開始します。 [顧客 AI インスタンスの設定](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) ガイド。

### 手順 4:顧客 AI データセットへの CJA 接続の設定

CJA で、次の操作を実行できます。 [1 つ以上の接続を作成](/help/connections/create-connection.md) を、顧客 AI に実装されたExperience Platformデータセットに追加しました。 これらのデータセットは、次に示すように、「顧客 AI スコア」プレフィックスで表示されます。

![CAI スコア](assets/cai-scores.png)

「アカウントをアップグレードする可能性」などの各予測は、1 つのデータセットと同じです。

次に、CJA が既存または新しいデータセットの一部として取り込む XDM スキーマの例を示します。

![CAI スキーマ](assets/cai-schema.png)

( この例はプロファイルデータセットです。同じスキーマオブジェクトのセットは、CJA が取得するエクスペリエンスイベントデータセットの一部になります。 エクスペリエンスイベントデータセットには、スコアの日付としてタイムスタンプが含まれます )。 このモデルでスコアリングされたすべての顧客には、スコア、scoreDate などが割り当てられます。 と関連付けられています。

### 手順 5:これらの接続に基づくデータビューの作成

CJA では、確立した接続の一部として取り込まれたディメンションを使用して、データビューの作成に進むことができます。