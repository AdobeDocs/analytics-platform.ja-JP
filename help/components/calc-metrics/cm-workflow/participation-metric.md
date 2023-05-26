---
description: 計算指標ビルダーを使用して、誰でもパーティシペーション指標を作成できます。
title: パーティシペーション指標
feature: Calculated Metrics
exl-id: 0d102f0f-3bcc-4f3a-93d2-c2b991c636cb
source-git-commit: 5fbffb01c08b5f8069b2670742f7ae3836ad8357
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 42%

---

# 「パーティシペーション」指標の作成

次の情報では、注文を含む訪問に貢献した（または関係した）ページを示す指標の作成方法を説明します。

このタイプの情報は、コンテンツ所有者にとって役立つ場合があります。

>[!NOTE]
>
>パーティシペーション指標は管理ツールで有効にできますが、カスタムイベント 1 ～ 100 に対してのみ有効です。

1. 指標の作成を開始します ( [指標の作成](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).
1. 計算指標ビルダーで、指標に「パーティシペーション」などの名前を付けます
1. 成功イベント「注文」を「定義」キャンバスにドラッグします。
1. [設定](/help/components/calc-metrics/cm-workflow/m-metric-type-alloc.md)ギアアイコンの下にある、そのイベントの&#x200B;**[!UICONTROL アトリビューションモデル]**&#x200B;を&#x200B;**[!UICONTROL パーティシペーション]**&#x200B;に変更します。「**[!UICONTROL 訪問]**」のルックバックを選択します。定義は次のようになるはずです。

   ![](assets/participation.png)

1. 選択 [!UICONTROL **保存**] 指標を保存します。
1. **[!UICONTROL ページ]**&#x200B;レポートで計算指標を使用します。

   ![](assets/participation-pages.png)

1. （任意）指標を組織内の他のユーザーと共有します。
