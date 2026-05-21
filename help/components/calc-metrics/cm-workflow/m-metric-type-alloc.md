---
description: 指標タイプとアトリビューションについて説明します。
title: 指標タイプとアトリビューション
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
TQID: https://experienceleague.adobe.com/aRrDxJeaU4xEzn2egBC5X-kUysJ00lrmfMUb7VE1CSc
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
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 620
ht-degree: 99%

---

# 指標タイプとアトリビューション

計算指標定義で指標の指標タイプと[アトリビューションモデル](#attribution-models)を設定できます。

1. 指標コンポーネントで「![設定](/help/assets/icons/Setting.svg)」を選択します。
1. ポップアップダイアログで以下を行います。

   ![指標タイプとアトリビューション](assets/cm-type-alloc.png)

   * 「**[!UICONTROL 指標タイプ]**」を指定します。

     | 指標タイプ | 定義 |
     |---|---|
     | **[!UICONTROL 標準]** | 1 つの標準指標で構成される数式は、その標準指標に対応する計算指標以外の指標と同じデータを表示します。 標準指標は、個々の行項目に固有の計算指標を作成する場合に役立ちます。 <p>例えば、![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 注文件数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL セッション]**&#x200B;は、その特定の行項目の注文件数をその特定の行項目のセッション数で除算します。 |
     | **[!UICONTROL 総計]** | 各行項目のレポート期間の&#x200B;**[!UICONTROL 総計]**&#x200B;を使用します。 数式が 1 つの総計指標で構成される場合、計算指標は行項目ごとに同じ総計数を表示します。 総計指標は、合計データと比較する計算指標を作成する場合に役立ちます。 <p>例えば、![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 注文件数]** ![除算](/help/assets/icons/Divide.svg) ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計セッション数]**&#x200B;は、特定の行項目に対するセッションだけでなく、すべてのセッションに対する注文件数の割合を示します。 この例では、計算指標で **[!UICONTROL イベント]** **[!UICONTROL セッション数]** ![指標の](/help/assets/icons/Event.svg)総計を指定し、それが自動的に ![イベント](/help/assets/icons/Event.svg) **[!UICONTROL 合計セッション数]**&#x200B;に変わります。 |

   * 「**[!UICONTROL アトリビューション]**」を指定します。

      1. 以下のいずれかを実行できます。

         * 30 日間のルックバックウィンドウを持つデフォルトの列アトリビューションモデル（ラストタッチ）を使用する場合は、「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を無効にします。
         * 「**[!UICONTROL デフォルト以外のアトリビューションモデルを使用]**」を有効にします。 **[!UICONTROL 列アトリビューションモデル]**&#x200B;ダイアログで以下を行います。

            * [アトリビューションモデル](#attribution-models)から&#x200B;**[!UICONTROL モデル]**&#x200B;を選択します。
            * 「**[!UICONTROL コンテナ]**」オプションから「[コンテナ](#container)」を選択します。
            * 「**[!UICONTROL ルックバックウィンドウ]**」オプションから「[ルックバックウィンドウ](#lookback-window)」を選択します。 「**[!UICONTROL カスタム時間]**」を選択した場合は、期間を「**[!UICONTROL 分]**」から「**[!UICONTROL 四半期]**」までの単位で定義できます。

      1. デフォルト以外のアトリビューションモデルを適用するには、「**[!UICONTROL 適用]**」を選択します。 キャンセルするには、「キャンセル」を選択します。

     デフォルト以外のアトリビューションモデルを既に定義してある場合は、「**[!UICONTROL 編集]**」を選択して、選択項目を変更します。

アトリビューションモデル、コンテナ、ルックバックウィンドウの使用例については、[例](#example)を参照してください。


## アトリビューションモデル {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="デフォルト以外のアトリビューションモデルを使用"
>abstract="選択した指標に対してデフォルト以外のアトリビューションモデルを有効にします。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="モデル"
>abstract="指標のアトリビューションモデルを選択します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="ラストタッチ"
>abstract="訪問者が閲覧した最後のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="ファーストタッチ"
>abstract="訪問者が閲覧した最初のディメンション値に、クレジットの 100％を割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="線形"
>abstract="クレジットはすべてのディメンション値に均等に配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="パーティシペーション"
>abstract="訪問者が閲覧したすべてのディメンション値に 100%クレジットされます。<br/>列の合計は誇張されています。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="同じタッチ"
>abstract="コンバージョンと同じイベントで発生するディメンション値にのみ、クレジットを割り当てます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U 字型"
>abstract="最初のディメンション値に 40%、最後のディメンション値に 40%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J カーブ"
>abstract="最後のディメンション値に 60%、最初のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="逆 J 形"
>abstract="最初のディメンション値に 60%、最後のディメンション値に 20%、中央の値に 20%のクレジットが配分されます。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="タイムディケイ"
>abstract="コンバージョンに最も近いディメンション値に、最も多くのクレジットを付与します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="カスタム"
>abstract="独自の位置ベースのアトリビューションの重み付けを定義します。"

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="アルゴリズム"
>abstract="クレジットは、統計的アルゴリズムに基づいて動的に決定されます。"

{{attribution-models-details}}


## コンテナ {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="コンテナ"
>abstract="コンテナを選択して、アトリビューションに必要な範囲を設定します。"

{{attribution-container}}


## ルックバックウィンドウ {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="ルックバックウィンドウ"
>abstract="この設定により、各コンバージョンに適用されるデータアトリビューションの期間が決まります。"

{{attribution-lookback-window}}




## 例

{{attribution-example}}

>[!MORELIKETHIS]
>
>[属性コンポーネント設定](/help/data-views/component-settings/attribution.md)
>[パーティシペーション指標](participation-metric.md)
>

