---
description: 計算指標の作成方法を説明します。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
TQID: https://experienceleague.adobe.com/8xHrnqI8ZUf3qwy4Im3Qa-ESAokGMs3XPOYmpFF6Dx0
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 12%

---

# 計算指標の作成

デフォルトでは、計算指標を作成できるのは管理者のみです。 ユーザーには、他のコンポーネント（セグメント、注釈など）を表示する方法と同様に、計算指標を表示する権限があります。

ただし、管理者は、[Admin Console](/help/technotes/access-control.md#user-level-access)を介してユーザーに対して、**[!UICONTROL CJA Workspace Access]**&#x200B;の編集権限で&#x200B;**[!UICONTROL Reporting Tools]**&#x200B;の&#x200B;**[!UICONTROL 計算指標作成]**&#x200B;権限を付与できます。


計算指標は、次の方法で作成できます。

![指標を作成する方法](assets/create-metric.png)

* **A**。メインインターフェイスで、**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 計算指標]**&#x200B;を選択します。 [[!UICONTROL 計算指標] マネージャー](/help/components/calc-metrics/cm-workflow/cm-manager.md)から![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]を選択します。
* **B**。Workspace プロジェクトで、「コンポーネント」左パネルから、![&#x200B; イベント &#x200B;](/help/assets/icons/Event.svg) **指標**&#x200B;の![追加](/help/assets/icons/Add.svg)を選択します。
* **C**。Workspace プロジェクトで、メトリクス列ヘッダーのコンテキストメニューから「**[!UICONTROL 選択範囲からメトリクスを作成]**」を選択します。 サブメニューから、関数を選択するか、計算指標ビルダーで&#x200B;**[!UICONTROL 開く]**&#x200B;を選択できます。 <br/>関数を選択すると、計算指標はプロジェクトのみの指標として定義されます。 後でこの指標を編集すると、[&#x200B; コンポーネント情報](/help/components/use-components-in-workspace.md#component-info) ポップアップを使用して、[計算指標ビルダー](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)に通知が表示されます。
* **D**。Workspace プロジェクトで、メニューから「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 指標を作成]**」を選択します。
* **E**。Workspace プロジェクトでは、ショートカット **[!UICONTROL shift+cmd+c]** （macOS）または&#x200B;**[!UICONTROL shift+ctrl+c]** （Windows）を使用します。

新しい計算指標を定義するには、[計算指標ビルダー](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)を使用します。


## ワークフロー

計算指標を作成する前に、次のワークフローを慎重に検討してください。

| ワークフロータスク | 説明 |
| --- | --- |
| 計算指標の計画 | 特に、正式に承認される指標の場合、どの計算指標を広く使用し、どのように定義するかを概説することは合理的です。 |
| [&#x200B; ビルド &#x200B;](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)計算指標 | [!DNL Customer Journey Analytics] コンポーネントで使用するために、計算指標と高度な計算指標を作成および編集します。 |
| [&#x200B; タグ &#x200B;](cm-tagging.md)計算指標 | 計算指標にタグを付けて、容易に整理および共有。 簡易検索および詳細検索と整理について詳しくは、タグの計画および割り当て方法に関する説明を参照してください。 |
| [計算指標の承認](cm-approving.md) | 計算された指標を承認し、規範的なものにします。 |
| 計算指標の使用 | プロジェクトで計算指標を使用します。 |
| [計算指標を共有](cm-sharing.md)する | 計算指標を他の個人、グループ、組織と共有します。 |
| [&#x200B; フィルター](cm-filter.md)計算指標 | タグ、所有者、その他のフィルター（すべて表示、自分、自分と共有、お気に入り、承認済み）で計算指標をフィルタリングします。 |
| 計算指標をお気に入り[としてマーク &#x200B;](cm-finding.md) | 指標を使いやすく整理するための 1 つの方法として、指標をお気に入りに登録することができます。 |

