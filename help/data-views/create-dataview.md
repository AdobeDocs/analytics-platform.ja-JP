---
title: データレイヤーの作成
description: Customer Journey Analytics （CJA）で、プラットフォームデータセットへのデータビューを作成する方法について説明します。
translation-type: tm+mt
source-git-commit: de265170126c1a9fc1f66364a79a74ff487d0b71
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 100%

---


# データレイヤーの作成

データビューは、データの「フィルター処理済み」の表示であるという意味で、Analytics の仮想レポートスイートと似ています。同じ接続に対して異なるデータビューを作成し、訪問のタイムアウト、アトリビューションなどに関する設定を変えることができます。1 つのデータセットに対して複数のデータビューを作成できます。例えば、すべてのディメンションが「ラストタッチ」に設定されたデータビューと、すべてのディメンションが「ファーストタッチ」に設定された別のデータビュー（同じデータセットに基づく）を同時に作成できます。

Customer Journey Analytics の Workspace プロジェクトは、データビューに基づいています。

ビデオの概要については、[こちら](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/basic-configuration-for-data-views.html)をクリックしてください。

## 前提条件

データビューを作成する前に、[Experience Platform データセットへの接続を 1 つ以上設定する必要があります](/help/connections/create-connection.md)。

## 設定する

1. Customer Journey Analytics で、「**[!UICONTROL データビュー]**」タブに移動します。

1. 「**[!UICONTROL 追加]**」をクリックしてデータビューを追加し、その設定をおこないます。

   | セッションの設定 | 定義 |
   |---|---|
   | 接続 | このフィールドは、データビューを、以前確立した接続（[!UICONTROL Experience Platform] データセットを含む）にリンクします。 |
   | 名前 | データビューに名前を付ける必要があります。 |
   | 説明 | 詳細な説明は必須ではありませんが、推奨します。 |
   | タグを追加 | タグを使用すると、データビューをカテゴリ別に整理できます。 |
   | タイムゾーン | データビューのタイムゾーンを選択します。 |
   | セッションタイムアウト | 「セッション」の定義を選択します。セッションタイムアウト設定では、各訪問者がどのくらいの時間非アクティブであった場合に新しいセッションを自動的に開始するかを定義します。デフォルト値は 30 分です。例えば、セッションタイムアウトを 45 分に設定した場合、収集された一連のヒットの後に非アクティブな時間が 45 分続くと、新しいセッションが開始されます。<!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.--> |
   | イベントで新しいセッションを開始 | セッションがタイムアウトしているかどうかに関係なく、イベントの発生時に新しいセッションが開始されます。新しく作成されたセッションには、そのセッションを開始したイベントが含まれます。さらに、複数のイベントを使用して 1 つのセッションを開始できます。新しいセッションは、これらのイベントのいずれかがデータに検出された場合に開始されます。この設定は、セッション（以前の「訪問」）セグメントコンテナ、およびディメンションの訪問有効期間ロジックにも影響します。 |
   | フィルターを追加 | 「フィルター」は、Customer Journey Analytics の「セグメント」を指します。データをフィルターする場合は、左側のナビゲーションバーから該当するフィルターをここにドラッグします。フィルターを選択しない場合、データビューにはすべてのデータが含まれます。 |

1. 「**[!UICONTROL 続行]**」をクリックします。

## コンポーネントを追加

1. 次に、コンポーネント（ディメンション、指標）をデータビューに追加します（仮想レポートスイートのキュレーションと同様）。データセット内の各フィールドがディメンションまたは指標に変換されるようになりました。ディメンションと指標をパネルまたは「**[!UICONTROL すべて選択]**」にドラッグして、すべてのコンポーネントを追加します。

   ![](assets/add-all-components.png)

1. データビューにディメンションと指標を追加するには、「**[!UICONTROL コンポーネントを追加]**」タブをクリックします。

   ![](assets/add-all-components2.png)

1. （オプション）コンポーネントの名前をわかりやすい名前に変更したり、コンポーネントを選択して設定を編集することで、アトリビューション設定を変更したりできます。基になる名前は保持されます。詳しくは、[データビューとアトリビューションの設定](/help/data-views/configure-dataviews.md)を参照してください。

1. 次の手順では、[コンポーネントとアトリビューションの設定を指定](/help/data-views/configure-dataviews.md)します。