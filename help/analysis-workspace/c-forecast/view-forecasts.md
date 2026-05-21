---
description: 表または折れ線グラフで予測を表示する方法を説明します。
title: 予測の表示
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
TQID: https://experienceleague.adobe.com/fihJQOI-CyvGccQsB0VxvwR-iV0OkJSMENaiciYrgFc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
subfeature_v2:
  - id: d13dba12-733d-4914-8d92-d643658bbe5d
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 372
ht-degree: 5%

---

# 予測を表示

フリーフォームテーブルまたは折れ線グラフで予測を表示できます。

## テーブルでの予測の表示

時系列フリーフォームテーブルで予測を表示できます。 [!UICONTROL 予測を表示]が[&#x200B; ユーザー設定](../user-preferences.md)でフリーフォームテーブルに対して有効になっている場合、予測は、テーブルに追加された最初の指標列に対して自動的に表示されます。 追加の列の場合：

1. 列ヘッダーの列設定アイコン ![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)を選択し、オプションのリストで&#x200B;**[!UICONTROL 予測を表示]**&#x200B;が選択されていることを確認します。 詳しくは、[列設定](../visualizations/freeform-table/column-row-settings/column-settings.md)を参照してください。

1. **[!UICONTROL 列設定]** メニューの外側をクリックして、設定を保存し、更新されたテーブルを表示します。

予測は、次の表に示されています。

![&#x200B; テーブルに予測を表示](assets/show-forecast-table.png)

* 各セルの予測値と割合は、**ダークグレー**&#x200B;で表示されます。
* 予測値を示すには、予測記号![ForecastAnalytics](/help/assets/icons/ForecastAnalytics.svg)がセルの右上隅に表示されます。


## 折れ線グラフでの予測の表示

折れ線グラフは、予測を表示できる唯一のビジュアライゼーションです。

1. ビジュアライゼーションヘッダーの設定アイコン ![列設定](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)を選択し、オプションのリストで&#x200B;**[!UICONTROL 予測を表示]**&#x200B;が選択されていることを確認します。

1. （オプション）予測でグラフを適切に拡大/縮小できるようにするには、**[!UICONTROL 予測でY軸を拡大/縮小する]**&#x200B;を選択します。 このオプションは、読みにくいグラフをレンダリングする場合があるため、デフォルトでは選択されません。

1. **[!UICONTROL 設定]** メニューの外側をクリックして、更新された折れ線グラフを表示します。

予測は、次のように折れ線グラフに表示されます。

![折れ線グラフに予測を表示](assets/show-forecast-linechart.png)

* 折れ線グラフの指標の現在の値は、縦棒で示されます。 垂直線の上にカーソルを合わせると、最後の現在の日付が表示されます。
* 1つ以上の指標の予測値は、点線を使用して垂直バーから直接表示されます。 指標の任意のデータポイントにカーソルを合わせることができます。 ポップアップに次の内容が表示されます。
   * 予測の日付
   * 指標の予測値
   * 指標の予測値の上限
   * 指標の予測値の下限
* シェーディングされた領域は、予測の信頼帯を示します。
