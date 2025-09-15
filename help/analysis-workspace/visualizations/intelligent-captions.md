---
description: インテリジェントキャプションを使用して自然言語のインサイトを生成し、ビジュアライゼーション内のトレンドを表示する方法を説明します。
title: インテリジェントキャプション
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 98%

---

# インテリジェントキャプション {#intelligent-captions}

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="インテリジェントキャプション"
>abstract="このビジュアライゼーションのデータをより簡単に理解および解釈できるように、自然言語形式でインサイトを生成します。"


インテリジェントキャプション機能は、高度な生成 AI を使用して、自然言語で最も頻繁に使用される Workspaceのビジュアライゼーションに関する重要なインサイトを提供します。

インテリジェントキャプションは、次のユーザーを対象としています。

* 他のユーザーと共有するナラティブを必要とするアナリスト。アナリストがユーザーにコンテキストを提供するには、これらのインサイトが必要です。
* 高レベルの要点をすばやく見つけたいビジネスユーザー。

>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [インテリジェントキャプション](https://video.tv.adobe.com/v/3443139/?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


## インテリジェントキャプションの起動 {#launch}

ビジュアライゼーションに対して自動生成されたインテリジェントキャプションを起動するには、ビジュアライゼーションの右上にある ![インテリジェントキャプション](/help/assets/icons/AI.svg) を選択します。この選択により、自然言語のインサイトが生成されます。

![製品ビューのトレンドに関するインテリジェントキャプションを表示する分析を起動ウィンドウ。](assets/intelligent-captions.gif)


次の点に注意してください。

* キャプションを正常に生成するには、3 つ以上のデータポイントが必要です。そうでない場合は、**[!UICONTROL 分析するのに十分なデータがありません]**&#x200B;などのエラーが発生する可能性があります。

* キャプションは、ビジュアライゼーションを強化するテーブルで選択された基になるデータが変更されるたびに生成されます。

* 関連付けられているフリーフォームテーブルに複数の指標がある場合、キャプションは最初の指標またはユーザーが現在選択している指標に対してのみ生成されます。ただし、折れ線グラフと面グラフのビジュアライゼーションでは、複数の指標に対してキャプションを生成できます。

* プロジェクトを特定の時点で保存し、後で再び読み込むと、キャプションは新しいデータで自動更新されます。スケジュールされたプロジェクトや、プロジェクトから書き出された PDF ファイルにも同じことが当てはまります。


## ビジュアライゼーション {#visualizations}

インテリジェントキャプションは、次のビジュアライゼーションでサポートされています。

* [折れ線グラフ](line.md)（複数の折れ線グラフを含む）
* [棒グラフ](bar.md)
* [横棒グラフ](horizontal-bar.md)
* [面グラフ](area.md) （複数の面グラフを含む）
* [ドーナツ](donut.md)
* [フォールアウト](fallout/fallout-flow.md)
* [フロー](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## アクション

インテリジェントキャプションでは次のアクションを実行できます。

### クリップボードにコピー {#copy}

キャプションをクリップボードにコピーして、PowerPoint やその他のツールにペーストできます。個々のキャプションを 1 つずつビューでコピーすることも、すべてのキャプションを一度に拡張キャプションビューでコピーすることもできます。

* キャプションをコピーするには、キャプションダイアログの右上にある ![クリップボードにキャプションをコピー](/help/assets/icons/Copy.svg) を選択します。

### すべてまたは個々のインテリジェントキャプションの表示  {#show-all-or-individual}

すべてのインテリジェントキャプションを一度に拡張ビューで表示することも、個々のインテリジェントキャプションを 1 つずつビューで表示することもできます。

* すべてのインテリジェントキャプションを表示するには、![すべてのインテリジェントキャプションを表示](/help/assets/icons/Maximize.svg) を選択します。
* 個々のインテリジェントキャプションを 1 つずつ表示するには、![個々のインテリジェントキャプションを表示](/help/assets/icons/Minimize.svg) を選択します。

### 表示の編集 {#edit}

特定のカテゴリのインサイトの非表示や非表示解除など、キャプションの表示を編集できます。

1. インテリジェントキャプションダイアログで ![インテリジェントキャプションの表示を編集](/help/assets/icons/EditInLight.svg) を選択します。

1. ![表示を切り替え](/help/assets/icons/Visibility.svg)を切り替えて特定のインサイト（**[!UICONTROL 最小値]**&#x200B;など）を表示するか、![表示を切り替え](/help/assets/icons/VisibilityOff.svg)を切り替えて特定のインサイト（**[!UICONTROL スパイク]**&#x200B;など）を非表示にします。

   ![インテリジェントキャプションを編集](assets/edit-intelligent-captions.png)

1. 「**[!UICONTROL 適用]**」を選択します。


### フィードバックの提供

生成されたインテリジェントキャプションに関するフィードバックを提供できます（フィードバックは拡張キャプションビューでのみ提供できます）。

1. インテリジェントキャプションダイアログで ![その他のアクション](/help/assets/icons/More.svg) を選択します。

1. ![応答が良い](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 応答が良い]**、![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 応答が悪い]** または ![フラグ](/help/assets/icons/Flag.svg) **[!UICONTROL レポート]**&#x200B;を選択します。

1. **[!UICONTROL フィードバックをいただきありがとうございました]**&#x200B;ダイアログでフィードバックを入力し、「**[!UICONTROL 送信]**」を選択してフィードバックを送信します。

### 書き出し {#export}

生成されたインテリジェントキャプションと共にプロジェクトが保存されている限り、インテリジェントキャプションを PDF の一部として書き出すことができます。

### オフへの切り替え {#toggle}

インテリジェントキャプションを表示しない場合は、この機能をオフに切り替えることができます。

1. [ビジュアライゼーションの環境設定](/help/analysis-workspace/user-preferences.md#visualizations-preferences)に移動します。
1. **[!UICONTROL インテリジェントキャプションを表示]**&#x200B;をオフにします。

   ![ インテリジェントキャプションを表示をオフにするオプションを表示する折れ線グラフのビジュアライゼーションオプション。](assets/toggle-captions.png)

1. 「**[!UICONTROL 保存]**」を選択して環境設定を保存します。


## モバイルスコアカードのインテリジェントキャプション

インテリジェントキャプションは、Customer Journey Analytics [モバイルスコアカード](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)でも使用できます。

## 機能アクセス

インテリジェントキャプションへのアクセスは、次のパラメーターによって制御されます。

* **ソリューションアクセス**：インテリジェントキャプション機能は、Customer Journey Analytics では使用できますが、Adobe Analytics では使用できません。

* **契約上のアクセス**：インテリジェントキャプションを使用できない場合は、組織の管理者またはアドビアカウント担当者（管理者）にお問い合わせください。組織でインテリジェントキャプションを使用する前に、生成 AI に関する特定の法的条件に同意する必要があります。

* **権限**：[!UICONTROL Adobe Admin Console] では、[!UICONTROL レポートツール]の&#x200B;**[!UICONTROL インテリジェントキャプション]**&#x200B;権限によってアクセスが決まります。[製品プロファイル管理者](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html)は、[!UICONTROL Admin Console] で次の手順に従う必要があります。
   1. **[!UICONTROL Admin Console]**／**[!UICONTROL 製品とサービス]**／**[!UICONTROL Customer Journey Analytics]**／**[!UICONTROL 製品プロファイル]**&#x200B;に移動します。
   1. インテリジェントキャプションへのアクセスを提供する製品プロファイルのタイトルを選択します。
   1. 特定の製品プロファイルで、「**[!UICONTROL 権限]**」を選択します。
   1. ![編集](/help/assets/icons/Edit.svg) を選択して、**[!UICONTROL レポートツール]**&#x200B;を編集します。
   1. ![AddCircle](/help/assets/icons/AddCircle.svg) を選択して、**[!UICONTROL 含まれる権限項目]**&#x200B;に&#x200B;**インテリジェントキャプション**&#x200B;を追加します。

      ![権限を追加](./assets/intelligent-captions-permissions.png)

   1. 「**[!UICONTROL 保存]**」を選択して権限を保存します。

詳しくは、[アクセス制御](/help/technotes/access-control.md#access-control)を参照してください。
