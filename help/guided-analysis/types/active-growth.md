---
title: アクティブな増加分析
description: 新規、継続、再来訪または休眠状態のユーザーを特定します。
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
source-git-commit: be617c59cd2fced0031fda1130b86e638bee8f68
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 91%

---

# [!UICONTROL アクティブな成長]分析 {#active-growth}

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_activegrowth_button"
>title="アクティブな増加"
>abstract="新規、継続、再来訪または休眠状態のユーザーを特定します。"



![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL アクティブな増加]**&#x200B;分析は、特定の期間におけるユーザーの増加と獲得に関するインサイトを提供します。横軸は時間間隔、縦軸はユーザーの測定値です。ユーザーは次の 4 つのカテゴリに分類されます。

* **[!UICONTROL 新規]**：ユーザーは現在の期間中はアクティブでしたが、以前はアクティブではありませんでした。グラフの凡例の&#x200B;_[!UICONTROL 新規ユーザー]_&#x200B;にカーソルを合わせて、分析が遡る範囲を確認します。ルックバック範囲は、選択した日付範囲と間隔に基づいて動的に決定されます。
* **[!UICONTROL 繰り返し]**：ユーザーが現在の期間と直前の期間でアクティブでした。
* **[!UICONTROL 復帰]**：ユーザーは現在の期間ではアクティブで、直前の期間ではアクティブではありませんでしたが、以前はある時点でアクティブでした。グラフの凡例の&#x200B;_[!UICONTROL 再来訪ユーザー]_&#x200B;にカーソルを合わせて、分析が遡る範囲を確認します。ルックバック範囲は、選択した日付範囲と間隔に基づいて動的に決定されます。
* **[!UICONTROL 休眠状態]**：ユーザーは直前の期間ではアクティブでしたが、現在の期間ではアクティブではありません。休眠状態のユーザーは、アクティブユーザーの合計数にカウントされません。

すべてのアクティブユーザー（新規 + 繰り返し + 復帰）は、横軸の上にティールの網掛けとして表示され、すべての休眠状態のユーザーは、横軸の下にオレンジで表示されます。


>[!VIDEO](https://video.tv.adobe.com/v/3423396/?quality=12&learn=on&captions=jpn)

## ユースケース

この分析のユースケースには、次のようなものがあります。

* **ユーザーリテンションとチャーン：**&#x200B;ユーザーリテンションが高い期間または低い期間を明確に視覚化します。リテンションの高い期間または低い期間を認識することで、リテンションの高い製品を決定したり、チャーンを最小限に抑えたりすることができます。
* **キャンペーンの評価**：特定のキャンペーンを表示すると、生成されたトラフィックの量と、それがユーザーのエンゲージメントの維持にどの程度役立ったかを把握するのに役立ちます。
* **ユーザーライフサイクル分析**：ユーザーライフサイクル全体を通してアクティブなユーザーの増加を分析すると、ユーザーエンゲージメントが低下する特定の段階を特定するのに役立ちます。例えば、オンボーディング段階で個人に対する休眠状態のユーザーの割合が高い場合、ユーザビリティの問題や、製品内ガイダンスを改善する必要性が示される可能性があります。

## インターフェイス

ガイド付き分析インターフェイスの概要については、[インターフェイス](../overview.md#interface)を参照してください。次の設定は、この分析に固有です。

### クエリパネル

クエリパネルでは、次のコンポーネントを設定できます。

* **[!UICONTROL 表示]**：この分析と[純増加率](net-growth.md)を切り替えます。
* **[!UICONTROL イベント]**：測定するイベントです。この分析はユーザーベースなので、期間内にイベントを 1 回操作したユーザーはアクティブユーザーとしてカウントされます。クエリには 1 つのイベントを含めることができます。
* **[!UICONTROL 次としてカウント]**：選択したイベントに適用するカウント方法。 <ul><li>**[!UICONTROL オプション]** には、[!UICONTROL &#x200B; ユーザー数 &#x200B;] および [!UICONTROL &#x200B; ユーザーの割合 &#x200B;] が含まれます。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}Customer Journey Analytics B2B editionでは、[!UICONTROL &#x200B; グローバルアカウント &#x200B;]、[!UICONTROL &#x200B; アカウント &#x200B;]、[!UICONTROL &#x200B; 購入グループ &#x200B;]、[!UICONTROL &#x200B; 商談 &#x200B;]、[!UICONTROL &#x200B; グローバルアカウントの割合 &#x200B;]、[!UICONTROL &#x200B; アカウントの割合 &#x200B;]、[!UICONTROL &#x200B; 購入グループの割合 &#x200B;]、および [!UICONTROL &#x200B; 商談の割合 &#x200B;] という追加の **&#x200B;**&#x200B;B2B オプションを使用できます。</li></ul>
* **[!UICONTROL セグメント]**：データのセグメント化の基準にするセグメント。 クエリには 1 つのセグメントを含めることができます。

### グラフ設定

[!UICONTROL アクティブな増加]分析には次のグラフ設定が用意されており、グラフの上にあるメニューで調整できます。

* **[!UICONTROL グラフのタイプ]**：使用するビジュアライゼーションのタイプ。オプションには[!UICONTROL 積み重ね棒グラフ]および[!UICONTROL 積み重ね面グラフ]があります。

### 時間比較

{{apply-time-comparison}}

### 日付範囲

分析に対する目的の日付範囲。この設定には、次の 2 つのコンポーネントがあります。

* **[!UICONTROL 間隔]**：トレンドデータの表示に使用する日付の精度。有効なオプションには、毎時、毎日、毎週、毎月、四半期ごとが含まれます。同じ日付範囲に異なる間隔を設定すると、グラフのデータポイント数とテーブルの列数に影響を与える場合があります。例えば、毎日の精度で 3 日間にわたる分析を表示すると、3 つのデータポイントのみが表示されますが、毎時の精度で 3 日間にわたる分析を表示すると、72 のデータポイントが表示されます。
* **[!UICONTROL 日付]**：開始日と終了日。便宜上、周期的な日付範囲のプリセットと以前に保存したカスタム範囲を使用できます。または、カレンダーセレクターを使用して固定日付範囲を選択することもできます。

<!--
## Example

See below for an example of the analysis.

![Active time compare](../assets/active-growth-compare.png)

-->
