---
title: リクエストのステッチ
description: ステッチのリクエスト方法を説明します。
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 26%

---

# リクエストのステッチ


>[!IMPORTANT]
>
>Adobeを使用したリクエストのステッチは不要になり、この方法は非推奨（廃止予定）になりました。 [ 接続 UI でステッチを有効にします ](use-stitching-ui.md)。
>

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

## 制限事項

- ソースイベントデータセットスキーマに加えた変更を、ステッチされた新しいデータセットスキーマにも適用します。

- ソースデータセットを削除すると、ステッチされたデータセットは処理を停止し、システムによって削除されます。

- データ使用状況ラベルは、ステッチされたデータセットスキーマに自動的には反映されません。ソースデータセットスキーマにデータ使用状況ラベルが適用されている場合は、ステッチされたデータセットスキーマにこれらのデータ使用状況ラベルを手動で適用する必要があります。詳しくは、[Experience Platform でのデータ使用状況ラベルの管理](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/overview)を参照してください。
