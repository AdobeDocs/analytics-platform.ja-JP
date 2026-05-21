---
description: 同じビジュアライゼーション内で指標を比較できる個々の指標をセグメント化する方法について説明します。
title: セグメント化指標
feature: Calculated Metrics
exl-id: 37cc93df-9f51-42b3-918f-ed5864991621
TQID: https://experienceleague.adobe.com/dOOOOGytHT-5IMC9LNcNlBKLufs9PUkvjBoAgw38bEI
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: b1f5d324-a668-4e51-a59b-6fc0862d7310id: bc7a5a86-1a70-451f-985c-037b65f091d1id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 504
ht-degree: 1%

---

# セグメント化指標

[計算指標ビルダー](cm-build-metrics.md#definition-builder)では、指標の定義内にセグメントを適用できます。 セグメントの適用は、分析でデータのサブセットに指標を使用する場合に役立ちます。

>[!NOTE]
>
>セグメント定義は、[ セグメントビルダー](/help/components/segments/seg-builder.md)を通じて更新されます。 セグメントに変更を加えると、セグメントが計算指標の定義の一部であるかどうかも含め、そのセグメントが使用されるあらゆる場所で自動的に更新されます。
>

自社と接触したドイツ人と、それ以外の国や地域の人との指標を比較します。 例えば、次のような質問に答えることができます。

1. 最も人気のある[ ページを訪問しているドイツ人と外国人の数](#popular-pages)。
1. 今月、オンラインで自社と接触したドイツ人と外国人の数（[合計](#totals)）を比較します。
1. あなたの人気ページにアクセスしたドイツ人と外国人の[ パーセンテージ ](#percentages)は何ですか？

以下のセクションでは、セグメント化された指標がこれらの質問に対する回答にどのように役立つかを示しています。 必要に応じて、より詳細なドキュメントを参照します。

## 人気ページ

1. [Workspace プロジェクトから`German people`という名前の計算指標](cm-workflow.md)を作成します。
1. [計算指標ビルダー](cm-build-metrics.md)内から、[CRM データのCRM国フィールドを使用して、人物の出身地を決定する`Germany`というタイトルのセグメント ](/help/components/segments/seg-builder.md)を作成します。

   >[!TIP]
   >
   >計算指標ビルダーでは、コンポーネントパネルを使用して直接セグメントを作成できます。
   >   

   セグメントは次のようになります。

   ![ セグメントドイツ ](assets/filter-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![計算指標ドイツ ](assets/calculated-metric-germany.png)

計算指標の国際バージョンについて、上記の手順を繰り返します。

1. Workspace プロジェクトから、`International people`というタイトルの計算指標を作成します。
1. 計算指標ビルダー内から、`Not Germany`というタイトルのセグメントを作成します。このセグメントは、CRM データからCRMの国フィールドを使用して、ユーザーがどこから来たのかを判断します。

   セグメントは次のようになります。

   ![ セグメントドイツ ](assets/filter-not-germany.png)

1. 計算指標ビルダーに戻り、セグメントを使用して計算指標を更新します。

   ![計算指標ドイツ ](assets/calculated-metric-notgermany.png)


1. Analysis Workspaceでプロジェクトを作成します。ここでは、ドイツ人と外国人が訪問したページを見ることができます。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人と外国人が表示されている](assets/workspace-german-vs-international.png)


## 合計

1. 総計に基づいて、2つの新しい計算指標を作成します。 以前に作成した各セグメントを開き、セグメント名を変更し、**[!UICONTROL 人物]**&#x200B;の&#x200B;**[!UICONTROL 指標タイプ]**&#x200B;を&#x200B;**[!UICONTROL グランド合計]**&#x200B;に設定し、**[!UICONTROL 別名で保存]**&#x200B;を使用して、新しい名前を使用してセグメントを保存します。 例：

   ![ ドイツの合計指標](assets/calculated-metric-germany-total.png)

1. Workspace プロジェクトに新しいフリーフォームテーブルのビジュアライゼーションを追加し、今月の合計ページを表示します。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人対国際総人数を表示](assets/workspace-german-vs-international-totals.png)


## 割合

1. 先ほど作成した計算指標から割合を計算する、2つの新しい計算指標を作成します。

   ![Workspace自由形式テーブルのビジュアライゼーションでドイツ語と国際合計の人数割合を表示](assets/calculated-metric-germany-total-percentage.png)


1. Workspace プロジェクトを更新します。

   ![Workspace自由形式テーブルのビジュアライゼーションで、ドイツ人対国際総人数を表示](assets/workspace-german-vs-international-totals-percentage.png)



>[!BEGINSHADEBOX]

デモ動画については、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [ セグメント化された計算指標を実装のない指標として使用](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/components/calculated-metrics/calculated-metrics-segmented-metrics){target="_blank"}を参照してください。

{{videoaa}}

>[!ENDSHADEBOX]

