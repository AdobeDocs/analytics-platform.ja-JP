---
title: Customer Journey Analyticsのデータ表示の使用例
description: Customer Journey Analytics内のデータ表示の柔軟性と能力を示す複数の使用例
translation-type: tm+mt
source-git-commit: b260930c5ffd50a428e5502695e159538ff8cb73
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 1%

---


# データ表示の使用例

>[!IMPORTANT]
>
>この機能は、現在、制限付きのテストになっています。

Customer Journey Analyticsにおけるデータ表示の柔軟性と能力を示す使用例です。

## pageTitle（文字列）スキーマフィールドからの注文指標の作成

例えば、データ表示を作成する場合、文字列の[!UICONTROL pageTitle]スキーマフィールドから[!UICONTROL Orders]指標を作成できます。 次の手順を実行します。

1. 「コンポーネント」タブで、[!UICONTROL pageTitle]を[!UICONTROL 「含まれるコンポーネント」]の下の[!UICONTROL 指標]セクションにドラッグします。
   ![](assets/use-case1a.png)
1. ドラッグした指標を強調表示し、右側の[!UICONTROL コンポーネント設定]の下で名前を変更します。
   ![](assets/orders.png)
1. 右側の[!UICONTROL 値を含む/除外]ダイアログを開き、次の内容を指定します。
   ![](assets/orders2.png)

   「確認」フレーズは、これが注文であることを示します。 これらの条件が満たされたページタイトルをすべて確認すると、インスタンスごとに「1」がカウントされます。 結果は、（計算指標ではなく）新しい指標になります。 Attribution IQ、フィルターなど、標準指標を使用できるあらゆる場所で機能します。
1. [!UICONTROL ラストタッチ]など、この指標のアトリビューションモデルをさらに指定できます。[!UICONTROL ルックバックウィンドウ]は[!UICONTROL セッション]です。
また、同じフィールドから別の[!UICONTROL 注文件数]指標を作成し、その指標に対して別のアトリビューションモデル（[!UICONTROL ファーストタッチ]、[!UICONTROL 30日]など）を指定できます。

## ディメンションに整数を使用

以前は、整数はCJAで指標として自動的に扱われていました。 現在は、数字(Adobe Analyticsのカスタムイベントを含む)をディメンションとして扱うことができます。 次に例を示します。

1. [!UICONTROL call_length_min]整数を[!UICONTROL 「含まれるコンポーネント]」の下の[!UICONTROL Dimension]セクションにドラッグします。
   ![](assets/integers.png)

1. これで、[!UICONTROL 値のグループ化]を追加して、このディメンションをレポート的にグループ化して表示できます。 そうしないと、このディメンションの各インスタンスがWorkspaceの行項目として表示されます。
   ![](assets/bucketing.png)
