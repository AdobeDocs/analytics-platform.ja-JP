---
title: ラベルとポリシー
description: Adobe Experience Platformで定義されたデータラベルとポリシーが、Customer Journey Analyticsのデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 60%

---

# ラベルとポリシー

Experience Platform でデータセットを作成する場合、データセットの一部またはすべての要素に対して[データ使用状況ラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=ja)を作成できます。これらのラベルとポリシーをCustomer Journey Analyticsで表示できます。

次のラベルは、Customer Journey Analyticsにとって特に重要です。

* `C8` ラベル - **[!UICONTROL 測定なし]**。このラベルは、組織の Web サイトやアプリでデータを分析に使用できないことを示します。

* `C12` ラベル - **[!UICONTROL 一般的なデータの書き出しがありません]**。この方法でラベル付けされたスキーマフィールドは、（レポート、エクスポート、API などを介して）Customer Journey Analyticsからエクスポートまたはダウンロードすることはできません。

>[!NOTE]
>
>データ使用ラベルは、ステッチされたデータセットに自動的には反映されません。 ただし、手動で追加することはできます。

「ラベル付け」自体は、これらのデータ使用状況ラベルが適用されるという意味ではありません。それが政策の目的です Experience Platform で [Policy Service API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=ja) を介してポリシーを作成します。

2 つのAdobe定義のポリシーがCustomer Journey Analyticsで表示され、レポートおよびダウンロード/共有に影響を与えます。

* **[!UICONTROL Analytics の適用]** ポリシー
* **[!UICONTROL ダウンロードの適用]**&#x200B;ポリシー

## データビューでのデータラベルのCustomer Journey Analytics

Experience Platform で作成したデータラベルは、データビューのユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用される[!UICONTROL データ使用状況ラベル]が表示されます。<p>![](assets/data-label-left.png) |
| [コンポーネント設定](/help/data-views/component-settings/overview.md)の下の右パネル | すべての[!UICONTROL データ使用状況ラベル]はここに一覧表示されます。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「[!UICONTROL 含まれるコンポーネント]」列に、「[!UICONTROL データ使用状況ラベル]」を列として追加できます。列セレクターアイコンをクリックし、「**[!UICONTROL データ使用状況ラベル]**」を選択します。<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、 [!UICONTROL フィルター] 左側のトレールのアイコンを使用し、次の条件でデータビューコンポーネントをフィルタリングします。 **[!UICONTROL データガバナンス]** およびのタイプ **[!UICONTROL ラベル]**:

![](assets/filter-labels.png)

「**[!UICONTROL 適用]**」をクリックして、どのコンポーネントにラベルが付いているかを確認します。

## データビューでデータガバナンスポリシーをフィルタリング

分析または書き出しの目的で特定のCustomer Journey Analyticsデータビュー要素の使用をブロックするポリシーがオンになっているかどうかを確認できます。

再度、 [!UICONTROL フィルター] アイコン（左側のレールとの下） **[!UICONTROL データガバナンス]**&#x200B;をクリックし、 **[!UICONTROL ポリシー]**:

![](assets/filter-policies.png)

「**[!UICONTROL 適用]**」をクリックし、有効になっているポリシーを確認します。

## 有効なポリシーがデータビューに与える影響

**[!UICONTROL Analytics の適用]**&#x200B;ポリシーまたは&#x200B;**[!UICONTROL ダウンロードの適用]**&#x200B;ポリシーがオンになると、特定のデータラベル（C8 や C12 など）が関連付けられているスキーマコンポーネントは、データビューに追加できません。

これらのコンポーネントは、左側のパネルの[!UICONTROL スキーマフィールド]リストでグレー表示されます。

![](assets/component-greyed.png)

また、ブロックされたフィールドがあるデータビューは保存できません。

>[!MORELIKETHIS]
>[機密データのダウンロード](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Report Builder の制限ラベルとは?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=ja)


