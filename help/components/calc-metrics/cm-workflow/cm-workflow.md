---
description: 計算指標の作成方法を説明します。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: b3c7ceedec7b3f6a916e97bab38fd55f1d6c7f51
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 25%

---

# 計算指標の作成

デフォルトでは、計算指標を作成できるのは管理者のみです。 ユーザーには、他のコンポーネント（セグメント、注釈など）の表示方法と同様に、計算指標を表示する権限があります。

ただし、管理者は、[Admin Console **[!UICONTROL を介して、]** CJA Workspace アクセスの権限の編集 **[!UICONTROL にある**&#x200B;[!UICONTROL &#x200B; レポートツール &#x200B;]&#x200B;**の]** 計算指標の作成 ](/help/technotes/access-control.md#user-level-access) 権限をユーザーに付与できます。


計算指標は次の方法で作成できます。

![ 指標の作成方法 ](assets/create-metric.png)

* **A**。メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 計算指標]**」を選択します。 ![ 計算指標 ](/help/assets/icons/AddCircle.svg) マネージャー [&#128279;](/help/components/calc-metrics/cm-workflow/cm-manager.md) から「[!UICONTROL AddCircle][!UICONTROL **[!UICONTROL Add]**]」を選択します。
* **B**。Workspace プロジェクトの左側のコンポーネント パネルで、「![ イベント ](/help/assets/icons/Event.svg) **指標**」の「![ 追加 ](/help/assets/icons/Add.svg)」を選択します。
* **C**。Workspace プロジェクトの指標列ヘッダーのコンテキストメニューで、「**[!UICONTROL 選択から指標を作成]**」を選択します。 サブメニューから、関数を選択するか、「**[!UICONTROL 計算指標ビルダーで開く]**」を選択できます。 <br/> 関数を選択すると、計算指標はプロジェクトのみの指標として定義されます。 後でこの指標を編集する際に、[ コンポーネント情報 ](/help/components/use-components-in-workspace.md#component-info) ポップアップを通じて、[ 計算指標ビルダー ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) に通知が表示されます。
* **D**。Workspace プロジェクトで、メニューから **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL 指標を作成]** を選択します。
* **E**. Workspace プロジェクトで、ショートカットキー **[!UICONTROL shift+cmd+c]** （macOS）または **[!UICONTROL shift+ctrl+c]** （Windows）を使用します。

新しい計算指標を定義するには、[ 計算指標ビルダー ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) を使用します。


## ワークフロー

計算指標を作成する前に、次のワークフローを慎重に検討してください。

| ワークフロータスク | 説明 |
| --- | --- |
| 計算指標の計画 | 特に、正式に「承認」される指標については、広く使用される計算指標とその定義方法の概要を確認しておくことが重要です。 |
| 計算指標の [ 作成 ](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | [!DNL Customer Journey Analytics] コンポーネントで使用するために、計算指標と高度な計算指標を作成および編集します。 |
| [ タグ付け ](cm-tagging.md) 計算指標 | 整理および共有が容易に行えるように計算指標にタグを付けます。簡易検索および詳細検索と整理について詳しくは、タグの計画および割り当て方法に関する説明を参照してください。 |
| [ 承認 ](cm-approving.md) 計算指標 | 計算指標を正規の指標として承認します。 |
| 計算指標の使用 | プロジェクトで計算指標を使用します。 |
| [ 共有 ](cm-sharing.md) 計算指標 | 他の個人、グループまたは組織と計算指標を共有します。 |
| [ フィルター ](cm-filter.md) 計算指標 | タグ、所有者、その他のフィルターで計算指標をフィルタリングします（「すべて表示」、「自分が所有」、「自分と共有」、「お気に入り」、「承認済み」を選択）。 |
| 計算指標を [ お気に入り ](cm-finding.md) としてマーク | 指標を使いやすく整理するための 1 つの方法として、指標をお気に入りに登録することができます。 |

