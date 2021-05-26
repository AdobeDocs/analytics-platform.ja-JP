---
title: Customer Journey Analytics のデータビューの使用例
description: Customer Journey Analytics でのデータビューの柔軟性と能力を示す複数の使用例
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
source-git-commit: 27e472f534590112194ce46b28a15b655c9caf2b
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 46%

---

# データビューの使用例

これらの使用例では、Customer Journey Analytics におけるデータビューの柔軟性と能力を示しています。

## 1. pageTitle（文字列）スキーマフィールドから注文指標を作成する

例えば、データビューを作成する場合、文字列の [!UICONTROL pageTitle] スキーマフィールドから [!UICONTROL 注文件数]指標を作成できます。手順は次のとおりです。

1. 「コンポーネント」タブで、[!UICONTROL pageTitle] を「[!UICONTROL 含まれるコンポーネント]」の下の「[!UICONTROL 指標]」セクションにドラッグします。
   ![](assets/use-case1a.png)
1. ドラッグした指標を強調表示し、右側の「[!UICONTROL コンポーネント設定]」の下で名前を変更します。
   ![](assets/orders.png)
1. 右側の[!UICONTROL 値を含む / 除外する]ダイアログを開き、次の内容を指定します。
   ![](assets/orders2.png)

   「confirmation」フレーズは、これが注文であることを示します。これらの条件が満たされたページタイトルをすべて確認すると、インスタンスごとに「1」がカウントされます。結果は、（計算指標ではなく）新しい指標になります。値を含めた／除外した指標は、他の指標を使用できるすべての場所で使用できます。Attribution IQ、フィルターなど、標準指標を使用できるあらゆる場所で機能します。
1. [!UICONTROL セッション]を[!UICONTROL ルックバックウィンドウ]として、[!UICONTROL ラストタッチ]など、この指標のアトリビューションモデルをさらに指定できます。
また、同じフィールドから別の[!UICONTROL 注文件数]指標を作成し、その指標に対して別のアトリビューションモデル（[!UICONTROL ファーストタッチ]など）と別の[!UICONTROL ルックバックウィンドウ]（[!UICONTROL 30 日]など）を指定できます。

## 2.ディメンションに整数を使用する

以前は、整数は CJA で指標として自動的に扱われていました。現在は、数値（Adobe Analytics のカスタムイベントを含む）をディメンションとして扱うことができます。次に例を示します。

1. [!UICONTROL call_length_min] 整数を「[!UICONTROL 含まれるコンポーネント]」の下の「[!UICONTROL ディメンション]」セクションにドラッグします。

   ![](assets/integers.png)

1. これで、「[!UICONTROL 値のグループ化]」を追加して、このディメンションをグループ化してレポートに表示できます（グループ化を使用しない場合、このディメンションの各インスタンスは Workspace レポートに行項目として表示されます）。

   ![](assets/bucketing.png)

## 3.フロー図で数値ディメンションを「指標」として使用する

数値ディメンションを使用して、[!UICONTROL フロー]ビジュアライゼーションに「指標」を取り込むことができます。

1. データビュー[「コンポーネント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) 」タブで、[!UICONTROL マーケティングチャネル]スキーマフィールドを[!UICONTROL 「含まれるコンポーネント]」の下の[!UICONTROL 指標]領域にドラッグします。
2. Workspaceレポートでは、このフローは、[!UICONTROL マーケティングチャネル]が[!UICONTROL 注文]に流れ込むことを示します。

![](assets/flow.png)

## 4.サブイベントのフィルタリングを実行する

イベントをフィルタリングして、表示したいもののみを表示できます。 例えば、データビューの含める/除外機能を使用して、50ドルを超える売上を生んだ製品のみに焦点を当てます。 したがって、50ドルの製品購入と25ドルの製品購入を含む注文がある場合、我々は全体の注文ではなく、25ドルの製品購入のみを削除します。

1. データビュー[「コンポーネント](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-component-settings) 」タブで、[!UICONTROL 売上高]スキーマフィールドを[!UICONTROL 「含まれるコンポーネント]」の下の[!UICONTROL 指標]領域にドラッグします。
1. 指標を選択し、右側で次の項目を設定します。
a.「[!UICONTROL 形式]」で、「[!UICONTROL 通貨]」を選択します。
b.「[!UICONTROL 通貨]」で、「USD」を選択します。
c. 「[!UICONTROL 含む/除外する値]」で、「[!UICONTROL 含める/除外する値を設定]」の横にあるチェックボックスをオンにします。
d.「[!UICONTROL 一致]」で、「[!UICONTROL すべての条件が満たされた場合]」を選択します。
e.「[!UICONTROL 条件]」で、「[!UICONTROL 次よりも大きいか等しい]」を選択します。
f.値として「50」を指定します。

これらの新しい設定では、価値の高い売上高のみを表示し、50ドルを下回るものはすべて除外できます。

## 5. 「[!UICONTROL 値なしオプション]」設定を利用します

会社は、ユーザーのトレーニングに費やして、レポートで「未指定」と表示される時間を費やしている可能性があります。 データビューのデフォルトは「値なし」です。 データビューUIで、「値なし」を「未指定」に[変更できるようになりました。](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#configure-no-value-options-settings)

## 6. [!UICONTROL 複製]機能を使用します

指標を複製して特定の設定を変更すると、1つのスキーマフィールドから複数の指標またはディメンションを簡単に作成できます。

右上にある指標またはディメンションの名前の下にある「重複」設定を選択します。

![](assets/duplicate.png)

## 異なるアトリビューション設定を持つ複数の指標の作成

上記の[!UICONTROL 重複]機能を使用して、[!UICONTROL ファーストタッチ]、[!UICONTROL ラストタッチ]、[!UICONTROL アルゴリズム]など、様々なアトリビューション設定を持つ複数の売上高指標を作成します。

「アルゴリズムの売上高」などの違いを反映するために、各指標の名前を忘れないでください。

![](assets/algo-revenue.png)

その他のデータビューの設定について詳しくは、「[データビューの作成](/help/data-views/create-dataview.md)」を参照してください。
データビューの概念的な概要については、「[データビューの概要](/help/data-views/data-views.md)」を参照してください。