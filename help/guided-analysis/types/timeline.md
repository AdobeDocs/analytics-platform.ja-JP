---
title: タイムライン分析
description: ユーザーレベルのセッションイベントを経時的に監視し、エクスペリエンスパターンを見つけます。
feature: Adobe Product Analytics, Guided Analysis
keywords: Product Analytics
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!UICONTROL  タイムライン ] 分析 {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_timeline_button"
>title="タイムライン"
>abstract="ユーザーレベルのセッションイベントの推移を確認します。"

<!-- markdownlint-enable MD034 -->

![ タイムライン ](/help/assets/icons/Timeline.svg)**[!UICONTROL タイムライン]** 分析を使用すると、ユーザーレベルのセッションイベントを経時的に監視して、エクスペリエンスパターンを見つけ、より良いユーザーストーリーを伝えることができます。 左側のパネルでは、プロパティ値とセグメントでストリームをフィルタリングできます。 右側のパネルでは、フィルター条件に一致するユーザーのランダム化リストから選択できます。 中央の領域には、選択したユーザーのセッション別ストリームが表示されます。このストリームは、タイムスタンプ、プロパティ値、期間で構成されます。 特定のセッションの最後のイベントには期間を使用できません。


>[!NOTE]
>
>[!UICONTROL  タイムライン ] 分析では、**[!UICONTROL ユーザー ID]** 標準コンポーネントを [ データビュー ](/help/data-views/component-reference.md#optional) で使用できる必要があります。 データビューへのユーザー ID の組み込みは、Customer Journey Analytics管理者が管理するもので、このデータにアクセスできるユーザーを組織で完全にプライバシーが保護されます。
><br/>データビューに [!UICONTROL  ユーザー ID] コンポーネントが追加されていない場合は、次のメッセージが表示されます。
>
>* **Admins**: *この分析には、PersonID プロパティが必要です。 データビューにユーザー ID を追加してください。*
>* **管理者以外**: *この分析には PersonID プロパティが必要です。 Customer Journey Analytics管理者と協力して、ユーザー ID をデータビューに追加してください。*

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)



## ユースケース

この分析のユースケースには、次のものがあります。

* **摩擦の調査**: [ ファネル分析 ](funnel.md) 分析で大幅な低下が見つかった場合は、それらのユーザーのセグメントを作成し、この分析でセグメントを適用して、潜在的な原因を調査できます。
* **エラーの動作**：製品エラーが発生した場合は、そのエラーが表示される前または後にユーザーが行っていた操作を確認できます。
* **データ収集の検証**：データ管理者は、この分析を独自のユーザー ID にフィルタリングして、組織の実装が期待どおりに機能していることを検証できます。

## インターフェイス

ガイド付き分析インターフェイスの概要については、[ インターフェイス ](../overview.md#interface) を参照してください。 次の設定は、この分析に固有です。

### クエリパネル

クエリパネルでは、次のコンポーネントを設定できます。

* **[!UICONTROL Dimension]**: ストリーミング値を表示するディメンション。 中央のストリームには、選択したディメンションの値が表示されます。 また、フィルターを適用して、より関連性の高いデータにストリームを絞り込むこともできます。 フィルターの有効な演算子には、[!UICONTROL Equals]、[!UICONTROL Not equal]、[!UICONTROL Starts with]、[!UICONTROL Ends with]、[!UICONTROL Contains]、[!UICONTROL Does not contains]、[!UICONTROL Exists]、および [!UICONTROL Does not exists] があります。
* **[!UICONTROL セグメント]**：分析するセグメント。 選択したセグメントでは、セグメント条件に一致する個人にのみフォーカスするようにデータをフィルタリングします。 分析を特定のユーザー ID に絞り込む場合は、右側のパネルでそのユーザー ID をフィルタリングできます。 この分析では、1 つのセグメントがサポートされています。

### グラフ設定

[!UICONTROL  タイムライン ] 分析には次のグラフ設定が用意されており、グラフ上のメニューで調整できます。

* **[!UICONTROL 表示方法]**：目的のプロパティ値を表示します。
   * [!UICONTROL  すべてを表示 ]：セッション内のすべてのプロパティ値を表示します。
   * [!UICONTROL  ハイライト表示 ]：セッション内のプロパティ値のうち、クエリフィルターに一致する値を視覚的にハイライト表示します。
   * [!UICONTROL  表示のみ ]：クエリフィルターに一致するセッションのプロパティ値のみを表示します。

### 日付範囲

分析に必要な日付範囲。 この設定には、次の 2 つのコンポーネントがあります。

* **[!UICONTROL 間隔]**：トレンドデータの表示に使用する日付の精度。 この設定は、タイムラインなど、トレンドのない分析には影響しません。
* **[!UICONTROL 日付]**：開始日と終了日。 周期的な日付範囲のプリセットと以前に保存したカスタム範囲は便利に使用できます。または、カレンダーセレクターを使用して固定された日付範囲を選択できます。


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
