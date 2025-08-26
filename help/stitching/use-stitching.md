---
title: ステッチの使用
description: ステッチの使用方法
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 1ee282d0bf91c1a2f27073d0755cf404148d4d5b
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 9%

---

# ステッチの使用

組織がすべての [ 前提条件 ](overview.md#prerequisites) を満たし、一般的な [ 制限 ](overview.md#limitations) およびステッチ方法固有の（[ フィールドベース ](fbs.md#limitations) および [ グラフベース ](gbs.md#limitations)）の制限を理解したら、次の手順に従ってCustomer Journey Analyticsでのステッチの使用を開始できます。

## オプションを選択

使用できるCustomer Journey Analytics パッケージによって、ステッチ方法、初期バックフィル期間のオプション、ルックバックウィンドウ、再生頻度、ステッチで許可されるデータセットの最大数が決まります。 詳しくは、[Customer Journey Analyticsの製品説明 ](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html) を参照してください。 サポートを依頼する前に、利用可能なオプションを決定してください。

| | Customer Journey Analytics<br/> 選択 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 使用可能なステッチ方法 | <li>フィールドベースのステッチ</li> | <li>フィールドベースのステッチ</li><li>グラフベースのステッチ</li> | <li>フィールドベースのステッチ</li><li>グラフベースのステッチ</li> |
| 1 回限りのステッチバックフィル期間 | 13 か月 | 13 か月 | 25 か月 |
| ルックバックウィンドウと再生頻度 | <li>1 日、毎日</li><li>最大 7 日間、毎週</li> | <li>1 日、毎日</li><li>最大 14 日間、毎週</li> | <li>1 日、毎日</li><li>最大 30 日間、毎週</li> |
| ステッチできるデータセットの最大数 | 5 | 15 | 50 |

## サポートをリクエスト

1. 次の情報をアドビカスタマーサポートに連絡してください。

   - ステッチを有効にするリクエスト。
   - キーを変更するデータセットのデータセット ID。
   - 目的のデータセットの永続 ID の列名（ID パスと名前空間） （すべての行に表示される識別子）。
   - データセットが `identityMap` をサポートしている場合：
      - フィールドベースのステッチの場合は、永続 ID と一時 ID の両方の名前空間を指定します。
      - グラフベースのステッチの場合は、永続 ID の名前空間と、ID グラフのクエリに使用する ID 名前空間を指定します。
   - データセットが `identityMap` をサポートしていない場合：
      - フィールドベースのステッチの場合、目的のデータセットの一時的な ID の列名（ユーザー識別子。接続のコンテキストでデータセット間のリンクとしても機能します）。
      - グラフベースのステッチの場合、ID グラフのクエリに使用する ID 名前空間。
   - ルックバックウィンドウと再生頻度の環境設定。 [options](#options) については、Customer Journey Analytics パッケージを参照してください。
   - サンドボックス名


2. Adobe カスタマーサポートはAdobe エンジニアリングと連携し、お客様のリクエストを受け取ったらステッチを有効にします。 有効にすると、新しいステッチ ID 列を含んだ新しいキー再設定済みデータセットがAdobe Experience Platformに表示されます。 Adobe カスタマーサポートは、新しいデータセットの ID を提供できます。

3. 最初にオンにした際、Adobeはステッチデータのバックフィルを行います。 [option](#options) については、Customer Journey Analytics パッケージを参照してください。

4. クロスチャネル分析で新しいステッチされたデータセットを使用する場合は、新しいステッチされたデータセットをCustomer Journey Analyticsの [connection](../connections/overview.md) に追加する必要があります。 次に、クロスチャネル分析に必要な他のデータセットを追加し、各データセットに対して正しいユーザー ID を選択します。

5. 接続に基づいて、[データ表示を作成](/help/data-views/create-dataview.md)します。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

データビューを設定したら、チャネルとデバイスをまたいでCustomer Journey Analytics レポート分析を実行できます。

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->
