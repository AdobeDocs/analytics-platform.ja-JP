---
description: Adobe Experience Platform 顧客 AI データが Customer Journey Analytics の Workspace とどのように統合されるのかを説明します。
title: 顧客 AI データの統合
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
feature: Experience Platform Integration
source-git-commit: c26829d7a53e9ba8d5faf731a8a1dca2e741bf21
workflow-type: ht
source-wordcount: '959'
ht-degree: 100%

---

# 顧客 AI データの統合

{{release-limited-testing}}

マーケターは、Adobe Experience Platform インテリジェントサービスの一部である[顧客 AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=ja) を使用して、顧客予測を個人レベルで生成することができます。

顧客 AI は、影響力のある要因の助けを借りて、顧客が何をする可能性があるかとその理由を知ることができます。さらに、マーケターは、顧客 AI の予測と洞察を活用して、最も適切なオファーとメッセージを提供することで、顧客のエクスペリエンスをパーソナライズできます。

顧客 AI は、傾向スコアリングに個々の行動データとプロファイルデータに依存します。顧客 AI には、Adobe Analytics、Adobe Audience Manager、消費者エクスペリエンスイベントデータ、エクスペリエンスイベントデータなど、複数のデータソースを柔軟に取り込むことができます。Experience Platform ソースコネクタを使用して Adobe Audience Manager と Adobe Analytics のデータを取り込むと、モデルは自動的に標準のイベントタイプを選択し、モデルのトレーニングとスコアリングを実施します。標準のイベントタイプを使用せずに独自のエクスペリエンスイベントデータセットを取り込む場合、モデルで使用するには、関連するフィールドをカスタムイベントまたはプロファイル属性としてマッピングする必要があります。これは、Experience Platform の顧客 AI の設定手順で行えます。

顧客 AI は、顧客 AI 対応データセットを Customer Journey Analytics のデータビューおよびレポートで利用できる範囲で、Customer Journey Analytics と統合できます。次のことができます。

* **ユーザーのセグメントの傾向スコアを経時的に追跡する**。
   * ユースーケース：特定のセグメントの顧客がコンバージョンする可能性を把握します。
   * 例：ホテルのコンサート会場で宿泊客がショーチケットを購入する可能性をホテルチェーンのマーケターが把握したい場合。
* **傾向スコアに関連付けられている成功イベントまたは属性を分析する**。
   * ユースーケース：傾向スコアに関連付けられている属性や成功イベントを把握します。
   * 例：ホテルのコンサート会場でのショーチケットの購入が傾向スコアにどのように関連付けられているかをホテルチェーンのマーケターが把握したい場合。
* **異なるスコアリング実行での顧客傾向のエントリフローに従う**。
   * ユースーケース：最初は傾向の低いユーザーだったのが、時間の経過と共に傾向の高いユーザーになった顧客を把握します。
   * 例：最初はショーチケットを購入する傾向が低い顧客として特定されたが、時間が経つにつれて、ショーチケットを購入する傾向が高い顧客になった宿泊客をホテルチェーンのマーケターが把握したい場合。
* **傾向の分布を確認する**。
   * ユースーケース：傾向スコアの分布を把握して、より正確にセグメントを定義します。
   * 例：小売業者がある製品に対して 50 ドル割引のプロモーションを実施したい場合。この業者は、予算などの理由から、限定的なプロモーションのみの実施を希望しています。データを分析し、顧客の上位 80％以上のみをターゲットにすることを決定します。
* **特定のコホートのアクションを遂行する傾向を経時的に確認する**。
   * ユースーケース：特定のコホートを経時的に追跡します。
   * 例：ブロンズ層とシルバー層の対比またはシルバー層とゴールド層の対比をホテルチェーンのマーケターが経時的に追跡したい場合。各コホートのホテル予約の傾向を経時的に確認できます。

実際に顧客 AI データを Customer Journey Analytics と統合するには、次の手順に従います。

>[!NOTE]
>
>この手順の一部は、Customer Journey Analytics の出力を処理する前に、Adobe Experience Platform で実行されます。


## 手順 1：顧客 AI インスタンスを設定する

データを準備し、すべての資格情報とスキーマを設定したら、Adobe Experience Platform ガイドの[顧客インスタンスの設定](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=ja)の手順に従って開始します。

## 手順 2：顧客 AI データセットへの Customer Journey Analytics 接続を設定する

Customer Journey Analytics で、顧客 AI 用に計測された Experience Platform データセットに、[1 つ以上の接続を作成](/help/connections/create-connection.md)できるようになりました。「アカウントをアップグレードする可能性」などの予測はそれぞれ、1 つのデータセットと同じです。これらのデータセットには、「Customer AI Scores in EE Format - name_of_application」というプレフィックスが付きます。

>[!IMPORTANT]
>
>手順 1 での設定時に Customer Journey Analytics のスコアを有効にする切替スイッチをオンにしている場合、各顧客 AI インスタンスには 2 つの出力データセットがあります。1 つの出力データセットが Profile XDM 形式、もう 1 つが Experience Event XDM 形式で表示されます。

![CAI スコア](assets/cai-scores.png)

![接続を作成](assets/create-conn.png)

Customer Journey Analytics が既存または新規データセットの一部として取り込む XDM スキーマの例を以下に示します。

![CAI スキーマ](assets/cai-schema.png)

（この例はプロファイルデータセットです。同じスキーマオブジェクトセットは、Customer Journey Analytics が取得するエクスペリエンスイベントデータセットの一部になります。エクスペリエンスイベントデータセットには、スコアの日付としてタイムスタンプが含まれます。）このモデルでスコアリングされたすべての顧客には、スコア、scoreDate などが関連付けられています。

## 手順 3：これらの接続に基づいたデータビューを作成する

Customer Journey Analytics で、確立した接続の一部として得られたディメンション（スコア、スコアの日付、確率など）や指標を使用して、[データビューの作成](/help/data-views/create-dataview.md)に進むことができます。

![データビューウィンドウの作成](assets/create-dataview.png)

## 手順 4：Workspace での CAI スコアのレポート

Customer Journey Analytics Workspace で新しいプロジェクトを作成し、ビジュアライゼーションを取り込みます。

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
