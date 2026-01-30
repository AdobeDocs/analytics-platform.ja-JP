---
title: リクエストのステッチ
description: ステッチのリクエスト方法
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 7%

---

# リクエストのステッチ


>[!IMPORTANT]
>
>Adobeを使用したリクエストのステッチは不要になり、この方法は非推奨（廃止予定）になりました。 [&#x200B; 接続 UI でステッチを有効にします &#x200B;](use-stitching-ui.md)。
>



組織がすべての [&#x200B; 前提条件 &#x200B;](overview.md#prerequisites) を満たし、一般的な [&#x200B; 制限 &#x200B;](overview.md#limitations) およびステッチ方法固有の（[&#x200B; フィールドベース &#x200B;](fbs.md#limitations) および [&#x200B; グラフベース &#x200B;](gbs.md#limitations)）の制限を理解したら、次の手順に従ってCustomer Journey Analyticsでステッチをリクエストし使用を開始できます。

## オプションを選択

使用できるCustomer Journey Analytics パッケージによって、ステッチ方法、初期バックフィル期間のオプション、ルックバックウィンドウ、再生頻度、ステッチで許可されるデータセットの最大数が決まります。 詳しくは、[Customer Journey Analyticsの製品説明 &#x200B;](https://helpx.adobe.com/jp/legal/product-descriptions/customer-journey-analytics.html) を参照してください。 サポートを依頼する前に、利用可能なオプションを決定してください。

| | Customer Journey Analytics<br/> 選択 | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| 使用可能なステッチ方法 | フィールドベースのステッチ | フィールドベースのステッチ <br/> グラフベースのステッチ | フィールドベースのステッチ <br> グラフベースのステッチ</li> |
| 1 回限りのステッチバックフィル期間 | 13 か月 | 13 か月 | 25 か月 |
| ルックバックウィンドウと再生頻度 | 1 日、毎日 <br/> 最大 7 日、毎週 | 1 日、毎日 <br/> 最大 14 日、毎週 | 1 日、毎日 <br/> 最大 30 日、毎週 |
| ステッチできるデータセットの最大数 | 5 | 15 | 50 |

## サポートをリクエスト

1. 次の情報をアドビカスタマーサポートに連絡してください。

   - ステッチを有効にするリクエスト。
   - キーを変更するデータセットのデータセット ID。
   - 目的のデータセットの永続 ID の列名（ID パスと名前空間） （すべての行に表示される識別子）。
   - データセットが `identityMap` をサポートしている場合：
      - フィールドベースのステッチの場合は、永続 ID と人物 ID の両方の名前空間を指定します。
      - グラフベースのステッチの場合は、永続 ID の名前空間と、ID グラフのクエリに使用する ID 名前空間を指定します。
   - データセットが `identityMap` をサポートしていない場合：
      - フィールドベースのステッチの場合、目的のデータセットのユーザー ID の列名（ユーザー識別子。接続のコンテキストでデータセット間のリンクとしても機能します）。
      - グラフベースのステッチの場合、ID グラフのクエリに使用する ID 名前空間。
   - ルックバックウィンドウと再生頻度の環境設定。 [options](#options) については、Customer Journey Analytics パッケージを参照してください。
   - サンドボックス名


2. Adobe カスタマーサポートはAdobe エンジニアリングと連携し、お客様のリクエストを受け取ったらステッチを有効にします。 有効にすると、ステッチされた ID 列を含んだ再入力されたデータセットがAdobe Experience Platformに表示されます。 Adobe カスタマーサポートは、新しいデータセットの ID を提供できます。
3. 最初にオンにした際、Adobeはステッチデータのバックフィルを行います。 [option](#options) については、Customer Journey Analytics パッケージを参照してください。

4. クロスチャネル分析でステッチされたデータセットを使用する場合は、ステッチされたデータセットをCustomer Journey Analyticsの [connection](../connections/overview.md) に追加する必要があります。 次に、クロスチャネル分析に必要な他のデータセットを追加し、各データセットに対して正しいユーザー ID を選択します。

5. 接続に基づいて、[データ表示を作成](/help/data-views/create-dataview.md)します。

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

データビューを設定したら、チャネルとデバイスをまたいでCustomer Journey Analytics レポート分析を実行できます。
