---
title: データビューの作成
description: Customer Jeurney Analytics(CJA)でプラットフォームデータセットに対するデータビューを作成する方法について説明します。
translation-type: tm+mt
source-git-commit: c85b5d2e702a38aa6569da893a25bacd39604f8a

---


# データビューの作成

データ表示は、データの「フィルター」表示であるという意味で、Analyticsの仮想レポートスイートに似ています。 同じ接続に対して異なるデータビューを作成し、訪問のタイムアウトや属性などを異なる設定で指定できます。 1つのデータセットに対して複数のデータビューを作成できます。 例えば、すべてのディメンションが「ラストタッチ」に設定された1つのデータビューと、すべてのディメンションが「ファーストタッチ」に設定された別のデータビュー（同じデータセットに基づく）を同時に作成できます。

Customer Jeurney AnalyticsのWorkspaceプロジェクトは、データビューに基づいています。

ビデオの [概要について](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html) 、ここをクリックしてください。

## 前提条件

データビューを作成する前に、Adobe Experience Platformデータセ [ットへの1つ以上の接続を設定する必要があります](/help/connections/create-connection.md)。

## 設定する

1. Customer Jeurney Analyticsで、タブに移動し **[!UICONTROL Data Views]** ます。

1. をクリック **[!UICONTROL Add]** して、データビューを追加し、その設定を行います。

   | セッション設定 | 定義 |
   |---|---|
   | 接続 | このフィールドは、データビューを、プラットフォームデータセットを含む、以前に確立した接続にリンクします。 |
   | 名前 | データビューに名前を付けることは必須です。 |
   | 説明 | 詳細な説明は必須ではありませんが、お勧めします。 |
   | タグの追加 | タグを使用すると、データビューをカテゴリに整理できます。 |
   | タイムゾーン | データ表示のタイムゾーンを選択します。 |
   | セッションタイムアウト | 「セッション」の定義を選択します。 セッションタイムアウトの設定は、新しいセッションが自動的に開始されるまでに実訪問者が持つ無操作状態の時間を定義します。 デフォルトは30分です。 例えば、セッションのタイムアウトを45分に設定した場合、収集されたヒットの各シーケンスに対して、45分間の無操作状態が続くたびに新しいセッショングループが作成されます。 <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | イベントを使用して新しいセッションを開始 | セッションがタイムアウトしたかどうかに関係なく、イベントが発生すると、新しいセッションが開始されます。 新しく作成されたセッションには、そのセッションを開始したイベントが含まれます。 また、複数のイベントを使用してセッションを開始し、データ内でこれらのイベントの1つが観察された場合に新しいセッションが発生するようにすることもできます。 この設定は、ディメンションに対する訪問回数、セッション（以前の訪問）セグメントコンテナ、訪問の有効期限ロジックに影響します。 |
   | フィルターを追加 | 「フィルター」は、Customer Jeurney Analyticsの「セグメント」を指します。 データをフィルターする場合は、左側のナビゲーションバーから該当するフィルターをここにドラッグします。 フィルターを選択しない場合、データビューにはすべてのデータが表示されます。 |

1. クリック **[!UICONTROL Continue]**.

## コンポーネントを追加

1. 次に、コンポーネント（ディメンション、指標）をデータビューに追加します（仮想レポートスイートのキュレーションエクスペリエンスと同様）。データセット内の各フィールドがディメンションまたは指標に変換されます。 ディメンションと指標をパネルまたは **[!UICONTROL [すべて選択]にドラッグし、すべてのコンポーネントを** 追加します。

   ![](assets/add-all-components.png)

1. データビューにデ **[!UICONTROL Add Components]** ィメンションと指標を追加するには、タブをクリックします。

   ![](assets/add-all-components2.png)

1. （オプション）コンポーネントの名前をわかりやすい名前に変更したり、コンポーネントを選択して設定を編集することで、アトリビューション設定を変更したりできます。 基本名は保持されます。 詳しくは、データビューとアトリビ [ューションの設定を参照してください](/help/data-views/configure-dataviews.md)。

1. 次の手順は、コンポーネントとア [トリビューションの設定を指定することで](/help/data-views/configure-dataviews.md)す。