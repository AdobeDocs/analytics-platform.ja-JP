---
description: Adobe Experience Platform Customer AI データと Workspace の統合の仕組みをCustomer Journey Analyticsで確認します。
title: 顧客 AI データとCustomer Journey Analyticsの統合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Platform Integration
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 49%

---

# 顧客 AI データとAdobe Customer Journey Analyticsの統合

{{release-limited-testing}}

マーケターは、Adobe Experience Platform インテリジェントサービスの一部である[顧客 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=ja) を使用して、顧客予測を個人レベルで生成することができます。

顧客 AI は、影響力のある要因の助けを借りて、顧客が何をする可能性があるかとその理由を知ることができます。さらに、マーケターは、顧客 AI の予測と洞察を活用して、最も適切なオファーとメッセージを提供することで、顧客のエクスペリエンスをパーソナライズできます。

顧客 AI は、傾向スコアリングに個々の行動データとプロファイルデータに依存します。顧客 AI には、Adobe Analytics、Adobe Audience Manager、消費者エクスペリエンスイベントデータ、エクスペリエンスイベントデータなど、複数のデータソースを柔軟に取り込むことができます。Experience Platform ソースコネクタを使用して Adobe Audience Manager と Adobe Analytics のデータを取り込むと、モデルは自動的に標準のイベントタイプを選択し、モデルのトレーニングとスコアリングを実施します。標準のイベントタイプを使用せずに独自のエクスペリエンスイベントデータセットを取り込む場合、モデルで使用するには、関連するフィールドをカスタムイベントまたはプロファイル属性としてマッピングする必要があります。これは、Experience Platformの顧客 AI の設定手順でおこなえます。

顧客 AI は、顧客 AI 対応のデータセットをCustomer Journey Analyticsのデータビューおよびレポートで利用できる範囲で、Customer Journey Analyticsと統合できます。 次のことができます。

* **ユーザーのセグメントの傾向スコアを経時的に追跡する**。
   * 使用例：特定のセグメントにおける顧客のコンバージョンの可能性を把握します。
   * 例：ホテルチェーンのマーケターは、ホテルのコンサート会場でホテルの顧客がショーチケットを購入する可能性を理解したいと考えています。
* **傾向スコアに関連付けられている成功イベントまたは属性を分析する**.
   * 使用例：傾向スコアに関連付けられた属性や成功イベントについて理解します。
   * 例：ホテルチェーンのマーケターは、ホテルのコンサート会場でのショーチケットの購入が傾向スコアとどのように関連付けられているかを理解したいと考えています。
* **異なるスコアリング実行での顧客傾向のエントリフローに従う**。
   * 使用例：最初に傾向が低いユーザーで、長期にわたって傾向が高いユーザーになったユーザーを把握します。
   * 例：ホテルチェーンのマーケターは、ショーチケットを購入する傾向が低い顧客として最初にどのホテル顧客が特定されたかを把握したいと考えていますが、時間が経つと、ショーチケットを購入する傾向が高い顧客になりました。
* **傾向の分布を確認する**。
   * 使用例：傾向スコアの分布を理解し、セグメントの定義でより正確にします。
   * 例：ある小売業者は、1 つの製品で 50 ドルの特定のプロモーションを実行したいと考えています。 この業者は、予算などの理由から、非常に限定的なプロモーションのみの実施を希望することがあります。データを分析し、顧客の上位 80%以上をターゲットにすることにします。
* **特定のコホートがアクションを実行する傾向を経時的に確認する**。
   * 使用例：特定のコホートを経時的に追跡します。
   * 例：ホテルチェーンのマーケターは、時間の経過と共に、ブロンズ層と銀層、または銀層と金層を比較して追跡したいと考えています。 訪問者は、時間の経過と共にホテルを予約する各コホートの傾向を確認できます。

実際に顧客 AI データをCustomer Journey Analyticsと統合するには、次の手順に従います。

>[!NOTE]
>
>手順の一部は、Customer Journey Analyticsの出力を操作する前に、Adobe Experience Platformで実行されます。


## 手順 1：顧客 AI インスタンスを設定する

データを準備し、すべての資格情報とスキーマを設定したら、Adobe Experience Platform ガイドの[顧客インスタンスの設定](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=ja)の手順に従って開始します。

## 手順 2:顧客 AI データセットへのCustomer Journey Analytics接続の設定

Customer Journey Analyticsで、 [1 つ以上の接続を作成](/help/connections/create-connection.md) を、顧客 AI に実装されたExperience Platformデータセットに追加しました。 「アカウントをアップグレードする可能性」などの予測はそれぞれ、1 つのデータセットと同じです。これらのデータセットには、「Customer AI Scores in EE Format - name_of_application」というプレフィックスが付きます。

>[!IMPORTANT]
>
>切り替えをオンにして手順 1 の設定時にCustomer Journey Analyticsのスコアを有効にすると、各顧客 AI インスタンスには 2 つの出力データセットがあります。 1 つの出力データセットが Profile XDM 形式、もう 1 つが Experience Event XDM 形式で表示されます。

![CAI スコア](assets/cai-scores.png)

![接続を作成](assets/create-conn.png)

次に、Customer Journey Analyticsが既存または新しいデータセットの一部として取り込む XDM スキーマの例を示します。

![CAI スキーマ](assets/cai-schema.png)

( この例はプロファイルデータセットです。同じスキーマオブジェクトのセットは、Customer Journey Analyticsが取得するエクスペリエンスイベントデータセットの一部です。 エクスペリエンスイベントデータセットには、スコアの日付としてタイムスタンプが含まれます。）このモデルでスコアリングされたすべての顧客には、スコア、scoreDate などが関連付けられています。

## 手順 3：これらの接続に基づいたデータビューを作成する

Customer Journey Analyticsで、 [データビューを作成](/help/data-views/create-dataview.md) を設定します。

![データビューの作成](assets/create-dataview.png)

## 手順 4：Workspace での CAI スコアのレポート

Customer Journey Analyticsワークスペースで、新しいプロジェクトを作成し、ビジュアライゼーションを取り込みます。

### 傾向スコアのトレンド

CAI データを含む Workspace プロジェクトの例を次に示します。CAI データは、経時的なユーザーのセグメントの傾向スコアのトレンドを、積み重ね棒グラフで表示します。

![スコアバケット](assets/workspace-scores.png)

### 理由コードを含むテーブル

次の表に、セグメントの傾向が高いまたは低い理由コードを示します。

![理由コード](assets/reason-codes.png)

### 顧客の傾向の入口フロー

次のフロー図は、様々なスコアリング実行における顧客の傾向の入口フローを示しています。

![入口フロー](assets/flow.png)

### 傾向スコアの分布

この棒グラフは、傾向スコアの分布を示します。

![配布](assets/distribution.png)

### 傾向の重複

次のベン図は、様々なスコアリングの実行で傾向が重なっていることを示しています。

![傾向の重複](assets/venn.png)
