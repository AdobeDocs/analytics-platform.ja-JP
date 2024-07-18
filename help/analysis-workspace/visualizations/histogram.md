---
description: ヒストグラムは、棒グラフに似ていますが、数値を範囲（バケット）にグループ化します。
title: ヒストグラム
feature: Visualizations
exl-id: 5901eb15-51cf-45a0-a80b-5824adf33bdd
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 80%

---

# ヒストグラム

ヒストグラムは、棒グラフに似ていますが、数を範囲（グループ）でグループ化します。Analytics は、数から範囲への「グループ化」を自動化しますが、[詳細設定](#section_09D774C584864D4CA6B5672DC2927477)で設定を変更できます。

## ヒストグラムのビルド {#section_74647707CC984A1CB6D3097F43A30B45}

ヒストグラムを作成するには

1. 左側のパネルで、 **[!UICONTROL ビジュアライゼーション]** をクリックします。
1. **[!UICONTROL ヒストグラム]**&#x200B;をパネルにドラッグします。
1. 指標を選択してヒストグラムビジュアライゼーションにドラッグし、「**[!UICONTROL ビルド]**」をクリックします。

![ 「指標を下にドロップ」フィールドを表示する、空のヒストグラムパネル。](assets/histogram.png)

>[!NOTE]
>
>ヒストグラムは、計算指標ではなく、標準指標のみをサポートします。

ここでは、ユニーク訪問者数ごとにページビュー数指標を使用しました。最初（左）のバケットは一意のユーザーごとに 1 つのページビューに対応し、2 番目のバケットは 2 つのページビューに対応します。

![](assets/histogram2.png)

## 詳細設定 {#section_09D774C584864D4CA6B5672DC2927477}

ヒストグラム設定を調整するには、右上隅の設定（「ギア」）アイコンをクリックします。変更できる設定を次に示します。

| ヒストグラムの設定 | 説明 |
|---|---|
| 開始グループ | どのグループからヒストグラムが始まるかを決定します。1 がデフォルトです。開始の数を 0 から無限大まで（負の数はなし）設定できます。 |
| 指標グループ | データ範囲（グループ）の数を増減できます。グループの最大数は 50 です。 |
| 指標グループのサイズ | 各グループのサイズを設定できます。例えば、グループサイズを 1 ページビューから 2 ページビューに変更できます。 |
| カウント方法 | [訪問者](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=ja)、[訪問](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=ja)、ヒットタイプから選択できます。例えば、訪問ごとのページビュー、ユーザーごとのページビュー、イベントごとのページビューなどです。 ヒットの場合、フリーフォームテーブルの y 軸指標として、「回数」が使用されます。 |

<!--Russ or Meike - Check Hit Type link above. -->

**例**：

* 開始グループ：1、指標グループ：5、指標グループのサイズ：2 は、1～2、3～4、5～6、7～8、9～10 というヒストグラムになります。
* 開始グループ：0、指標グループ：3、指標グループのサイズ：5 は、0～4、5～9、10～14 というヒストグラムになります。

## ヒストグラムデータの表示と編集 {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

ヒストグラムのデータソースを表示または変更するには、ヒストグラムヘッダーの隣の点をクリックして、 **[!UICONTROL データソース設定]**／**[!UICONTROL データソースを表示]** に移動します。

![ 「データSourceを表示」および「選択をロック」が選択された状態の「データSource設定」オプション ](assets/manage-data-source.png)

テーブルに表示される事前定義済みフィルターは、内部フィルターで、フィルターセレクターには表示されません。フィルター名の横にある「i」アイコンをクリックし、「**[!UICONTROL 公開する]**」をクリックしてフィルターを公開します。

![ 編集ウィンドウと「公開する」リンクを表示するセグメント。](assets/prebuilt_segments.png)

データを分類するなど、フリーフォームデータテーブルおよびその他のビジュアライゼーションを管理するその他の方法については、[こちら](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html?lang=ja)を参照してください。

## ブログ投稿

[ ヒストグラムを使用して予期しないデータ値を識別する ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-histograms-to-identify-unexpected-data-values/ba-p/596168) に関する情報については、このブログ投稿を参照してください。
