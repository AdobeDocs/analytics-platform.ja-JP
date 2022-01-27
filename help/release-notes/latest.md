---
title: 現在のCustomer Journey Analyticsリリースノート
description: 最新の CJA リリースノート
source-git-commit: 400b392b1b13e25f33970edddc3ae35e0153fbe6
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 89%

---


# 最新のCustomer Journey Analyticsリリースノート

| 機能 | 説明 | ターゲット日 |
| ----------- | ---------- | ----- |
| ディメンションのバインドと指標のバインドの「[!UICONTROL 永続性]」オプション | データビューを作成または編集する際に、ディメンションの永続性を別のディメンションまたは指標にバインドできます。 この概念は、Reports &amp; Analytics での _マーチャンダイジング_ として知られ、CJA でサポートされるようになりました。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#binding-dimension) | 2022年1月19日（PT） |
| [!UICONTROL 最初の事例] および [!UICONTROL 最後の事例] 配分モデル | これら 2 つの新しい配分モデルでは、指定した永続性の範囲内のディメンションの最初または最後に観測された値（ルックバックを含むセッション、ユーザーまたはカスタム期間）を取得します。 次に、指定した範囲内のすべてのイベントに配分モデルを適用します。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/persistence.html?lang=ja#allocation-settings) | 2022年1月19日（PT） |
| ディメンションとしての [!UICONTROL PersonID] および [!UICONTROL PersonID 名前空間] | `personID`（または `customerID`、または接続内のデータセットの結合に使用する ID など）をデータビューのディメンションとして公開します。この機能強化により、`personID` を接続から取り込み、データビューのディメンションとして含めやすくなりました。[詳細情報](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-reference.html?lang=ja#optional-standard-components) | 2022年1月19日（PT） |

{style=&quot;table-layout:auto&quot;}

>[!MORELIKETHIS]
>[Customer Journey Analyticsドキュメントの更新](/help/doc-changes.md)
