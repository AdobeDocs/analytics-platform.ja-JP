---
description: タッチポイントからセグメントを作成したり、セグメントをタッチポイントとして追加したり、Analysis Workspace の様々なセグメントにわたって主なワークフローを比較したりできます。
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: フォールアウト分析でのセグメントの適用
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 17%

---


# フォールアウト分析でのフィルターの適用

>[!NOTE]
>
>Customer Journey Analytics内のAnalysis Workspaceに関するドキュメントを表示している。 この機能セットは、従来のAdobeAnalyticsの [Analysis Workspaceとは少し異なります](https://docs.adobe.com/content/help/ja-JP/analytics/analyze/analysis-workspace/home.html)。 [詳細情報...](/help/getting-started/cja-aa.md)

タッチポイントからフィルターを作成したり、セグメントをタッチポイントとして追加したり、Analysis Workspace内の様々なフィルター間で主要なワークフローを比較したりできます。

>[!IMPORTANT]
>
>フォールアウトでチェックポイントとして使用されるフィルターは、フォールアウトビジュアライゼーションの全体的なコンテキストよりも低いレベルのコンテナを使用する必要があります。 訪問者コンテキストのフォールアウトを使用する場合、チェックポイントとして使用されるフィルターは、訪問またはヒットベースのフィルターである必要があります。 訪問コンテキストのフォールアウトでは、フィルターをチェックポイントとして使用する場合、ヒットベースのセグメントである必要があります。 無効な組み合わせを使用すると、フォールアウトは 100％になります。非互換のフィルターをタッチポイントとして追加した場合に表示される、フォールアウトビジュアライゼーションに警告を追加しました。 無効なフィルターコンテナの組み合わせによっては、次のような無効なフォールアウト図が生じる場合があります。

* 訪問者に基づくフィルターを、訪問者コンテキストのフォールアウトビジュアライゼーション内のタッチポイントとして使用する
* 訪問者ベースのフィルターを、訪問コンテキストのフォールアウトビジュアライゼーション内のタッチポイントとして使用する
* 訪問コンテキストフォールアウトビジュアライゼーション内のタッチポイントとしての訪問ベースのフィルターの使用

## Create a filter from a touchpoint {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. 特に関心があり、他のレポートに適用するのに役立つ特定のタッチポイントからフィルターを作成します。 You do this by right-clicking the touchpoint and selecting **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   フィルタービルダーが開き、選択したタッチポイントに一致する、事前にビルドされた順次フィルターが事前に設定されます。

   ![](assets/segment-builder.png)

1. フィルターにタイトルと説明を入力し、保存します。

   これで、任意のプロジェクトでこのフィルターを使用できます。

## Add a filter as a touchpoint {#section_17611C1A07444BE891DC21EE8FC03EFC}

例えば、米国のユーザーのトレンドとフォールアウトへの影響を確認する場合は、米国のユーザーフィルターをフォールアウトにドラッグします。

![](assets/segment-touchpoint.png)

または、USユーザーフィルターを別のチェックポイントにドラッグして、ANDタッチポイントを作成できます。

## Compare filters in fallout {#section_E0B761A69B1545908B52E05379277B56}

フォールアウトビジュアライゼーションでは、無制限の数のフィルターを比較できます。

1. Select the segments you want to compare from the [!UICONTROL Filter] rail on the left. この例では、US Users と Non-US Users の 2 つのセグメントを選択しています。
1. 上部のフィルタードロップゾーンにドラッグします。

   ![](assets/segment-drop.png)

1. オプション：「すべての訪問」をデフォルトのコンテナとして維持することも、削除することもできます。

   ![](assets/seg-compare.png)

1. あるフィルターが他のフィルターよりもパフォーマンスが優れている場所や他のインサイトなど、2つのフィルターにわたるフォールアウトを比較できるようになりました。
