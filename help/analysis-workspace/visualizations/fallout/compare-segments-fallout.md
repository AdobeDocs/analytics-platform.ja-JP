---
description: タッチポイントからフィルターを作成したり、フィルターをタッチポイントとして追加したり、Analysis Workspace の様々なフィルターについて主なワークフローを比較したりできます。
keywords: フォールアウトとフィルター、フォールアウト分析でのフィルター、フォールアウトでのフィルターの比較
title: フォールアウト分析でのフィルターの適用
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 76%

---

# フォールアウト分析でのフィルターの適用

タッチポイントからフィルターを作成したり、フィルターをタッチポイントとして追加したり、Analysis Workspace の様々なフィルターについて主なワークフローを比較したりできます。

>[!IMPORTANT]
>
>フォールアウトでチェックポイントとして使用されるフィルターでは、フォールアウトビジュアライゼーションの全体的なコンテキストよりも低いレベルのコンテナを使用する必要があります。ユーザーコンテキストのフォールアウトを使用する場合、チェックポイントとして使用するフィルターは、訪問またはイベントベースのフィルターである必要があります。 訪問コンテキストフォールアウトを使用する場合、チェックポイントとして使用するフィルターはイベントベースのフィルターである必要があります。 無効な組み合わせを使用すると、フォールアウトは 100% になります。互換性のないフィルターをタッチポイントとして追加すると表示される警告を、フォールアウトビジュアライゼーションに追加しました。フィルターコンテナの特定の無効な組み合わせ（例えば次のような場合）では、無効なフォールアウト図が生じます。

* 人物ベースのフィルターを人物コンテキストのフォールアウトビジュアライゼーション内のタッチポイントとして使用
* 訪問コンテキストのフォールアウトビジュアライゼーション内のタッチポイントとしてのユーザーベースのフィルターの使用
* 訪問ベースのフィルターを訪問コンテキストのフォールアウトビジュアライゼーション内のタッチポイントとして使用する

## タッチポイントからのフィルターの作成 {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 特に関心があり、他のレポートに適用するのに便利そうな特定のタッチポイントからフィルターを作成します。それには、タッチポイントを右クリックし、「**[!UICONTROL タッチポイントからフィルターを作成]**」をクリックします。

   ![タッチポイントからセグメントを作成をハイライト表示したタッチポイントドロップダウンメニュー。](assets/segment-from-touchpoint.png)

   フィルタービルダーが開き、選択したタッチポイントに合致する事前定義済みの順次フィルターがあらかじめ設定されています。

   ![フィルタービルダーに、事前に設定された順次フィルターと事前に作成された順次フィルターが表示されます。](assets/segment-builder.png)

1. フィルターにタイトルと説明を入力して、保存します。

   これで、希望する任意のプロジェクトでこのフィルターを使用できます。

## タッチポイントとしてのフィルターの追加 {#section_17611C1A07444BE891DC21EE8FC03EFC}

例えば、米国のユーザーのトレンドとフォールアウトへの影響を確認したい場合は、US Users フィルターをフォールアウトにドラッグするだけです。

![米国のユーザーフィルターが選択され、強調表示されて、フォールアウトにドラッグします。](assets/segment-touchpoint.png)

または、US Users フィルターを別のチェックポイントにドラッグすることで、AND タッチポイントを作成できます。

## フォールアウトでのフィルターの比較 {#section_E0B761A69B1545908B52E05379277B56}

フォールアウトビジュアライゼーションでは、フィルターを何個でも比較できます。

1. 比較するフィルターを左側の[!UICONTROL フィルター]パネルから選択します。この例では、US Users と Non-US Users の 2 つのフィルターを選択しています。
1. それらを上部のフィルタードロップゾーンにドラッグします。

   ![選択したフィルターと、フィルタードロップゾーンを指す赤い矢印を使用したフォールアウトビジュアライゼーション。](assets/segment-drop.png)

1. オプション：「すべての訪問」をデフォルトのコンテナとして維持することも、削除することもできます。

   ![前の手順でドラッグした 2 つのフィルターと共に、すべての訪問を示すフォールアウト。](assets/seg-compare.png)

1. これで、一方のフィルターがもう一方のフィルターよりパフォーマンスが優れているような 2 つのフィルターや他のインサイトについてフォールアウトを比較できます。
