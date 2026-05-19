---
title: レポートの結合
description: ステッチをリクエストする方法を説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
autotag-review: '2026-05-19T09:25:02.883Z'
TQID: 'https://experienceleague.adobe.com/0A4WNJ6TQDD3QrbupAK7R2sT25Nc-ovCnLFWjIyk0tU'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: faea9abd-7024-4c5e-a5b4-87919e09b24b
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: a05097c6a462301be1f1e45e0c1aa3cfa0676ff6
workflow-type: tm+mt
source-wordcount: 422
ht-degree: 27%

---

# リクエストのステッチ


>[!IMPORTANT]
>
>Adobeを介したリクエストのステッチは不要になり、このメソッドは非推奨になりました。 [接続UI](use-stitching-ui.md)でステッチを有効にします。
>

## サポートを依頼

1. 次の情報をアドビカスタマーサポートに連絡してください。

   - ステッチを有効にするためのリクエスト。
   - 再入力するデータセットのデータセット ID。
   - 目的のデータセット（すべての行に表示される識別子）の永続的IDの列名（ID パスと名前空間）。
   - データセットが`identityMap`をサポートしている場合：
      - フィールドベースの合成の場合は、永続IDと個人IDの両方の名前空間を指定します。
      - グラフベースの合成の場合は、永続的IDの名前空間と、ID グラフのクエリに使用するID名前空間を指定します。
   - データセットが`identityMap`をサポートしていない場合：
      - フィールドベースのステッチの場合、目的のデータセットのユーザーIDの列名（接続のコンテキストでデータセット間のリンクとしても機能するユーザー識別子）。
      - グラフベースのステッチの場合、ID グラフのクエリに使用するID名前空間。
   - ルックバックウィンドウと再生頻度の設定。 利用可能な[options](#options)については、Customer Journey Analytics パッケージを参照してください。
   - サンドボックス名


2. Adobe カスタマーサポートは、Adobe エンジニアリングと連携して、リクエストを受け取った際にステッチを有効にします。 有効にすると、ステッチ ID列を含む再入力されたデータセットがAdobe Experience Platformに表示されます。 Adobe カスタマーサポートは、新しいデータセットのIDを提供できます。
3. 最初にオンにすると、Adobeは合成データのバックフィルを提供します。 利用可能な[option](#options)については、Customer Journey Analytics パッケージを参照してください。

4. クロスチャネル分析でステッチされたデータセットを使用する場合は、ステッチされたデータセットをCustomer Journey Analyticsの[接続](../connections/overview.md)に追加する必要があります。 続いて、クロスチャネル分析に必要なその他のデータセットを追加し、各データセットに正しい人物IDを選択します。

5. 接続に基づいて、[データ表示を作成](/help/data-views/create-dataview.md)します。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

データビューを設定したら、チャネルやデバイスをまたいでCustomer Journey Analytics レポート分析を実行できます。

## 制限事項

- ソースイベントデータセットスキーマに加えた変更を、ステッチされた新しいデータセットスキーマにも適用します。

- ソースデータセットを削除すると、ステッチされたデータセットは処理を停止し、システムによって削除されます。

- データ使用状況ラベルは、ステッチされたデータセットスキーマに自動的には反映されません。 ソースデータセットスキーマにデータ使用状況ラベルが適用されている場合は、ステッチされたデータセットスキーマにこれらのデータ使用状況ラベルを手動で適用する必要があります。 詳しくは、[Experience Platform でのデータ使用状況ラベルの管理](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/overview)を参照してください。
