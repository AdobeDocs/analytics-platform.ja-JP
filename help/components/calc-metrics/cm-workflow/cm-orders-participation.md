---
description: 注文の促進に役立つマーケティングチャネルを示す指標の作成方法を説明します。
title: より複雑な計算指標の構築
feature: Calculated Metrics
exl-id: 33cb441d-d003-408d-ba67-1bcdd0e821ff
TQID: https://experienceleague.adobe.com/T5hA3-IeRUfDR53RL6TnJUslUI7XxRSZN2KpPKAz7k0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 3%

---

# より複雑な計算指標の構築

この記事では、計算指標のより複雑な例を説明します。 この計算指標は、どのマーケティングチャネルが注文の促進に役立っているかを示しています。 このタイプの計算指標は、あらゆるディメンションや成功イベントに適応させることができます。

1. [指標の作成](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)の説明に従って、計算指標の作成を開始します。

1. 計算指標ビルダーで、指標`Assisted Online Orders`などの名前を付けます。

1. **[!UICONTROL 指標]** コンポーネントから&#x200B;**[!UICONTROL オンライン注文]**&#x200B;指標を選択し、指標を&#x200B;**[!UICONTROL 定義]**&#x200B;領域にドラッグします。

   1. 指標に「![Setting](/help/assets/icons/Setting.svg)」を選択します。
   1. 「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を選択します。
   1. **[!UICONTROL 列アトリビューションモデル]**&#x200B;でアトリビューションモデルを調整します。
      1. **[!UICONTROL モデル]**&#x200B;の&#x200B;**[!UICONTROL カスタム]**&#x200B;を選択します。 **[!UICONTROL Starter]**&#x200B;を`0`に、**[!UICONTROL Player]**&#x200B;を`100`に、**[!UICONTROL Closer]**&#x200B;を`0`に設定します。
      1. **[!UICONTROL コンテナ]**&#x200B;の&#x200B;**[!UICONTROL 訪問者]**&#x200B;を選択します。
      1. **[!UICONTROL ルックバックウィンドウ]**&#x200B;の&#x200B;**[!UICONTROL 30日]**&#x200B;を選択します。

      1. 「**[!UICONTROL 適用]**」を選択します。

      ![列属性モデル &#x200B;](assets/complex-calculated-metric.png)

1. 計算指標を保存するには、**[!UICONTROL 保存]**&#x200B;を選択します。

計算指標を使用するには：

1. Analysis Workspaceで、**[!UICONTROL マーケティングチャネル]** ディメンション、**[!UICONTROL オンラインオーダー]**、新しい&#x200B;**[!UICONTROL アシストオンラインオーダー]**&#x200B;指標を含むフリーフォームテーブルを作成します。

   ![&#x200B; マーケティングチャネル支援オンライン注文](assets/marketing-channel-assists.png)

1. （オプション）計算指標の共有[計算指標の共有](/help/components/calc-metrics/cm-workflow/cm-sharing.md)の説明に従って、組織内の他のユーザーと指標を共有します。

これは、注文を促進するのに役立ったマーケティングチャネルを容易に把握する方法です。 または、フリーフォームテーブルから任意の指標を選択し、コンテキストメニューからテーブルから直接アトリビューションモデルを調整することもできます。
