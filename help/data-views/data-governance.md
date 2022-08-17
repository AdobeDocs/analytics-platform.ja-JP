---
title: ラベルとポリシー
description: AEP で定義されたデータラベルとポリシーが、CJA のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# ラベルとポリシー

データセットをExperience Platformで作成する際に、 [データ使用ラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) の一部またはすべての要素が含まれている場合。 これまで、これらのラベルは CJA では公開されていませんでした。 このリリースでは、CJA でこれらのラベルとポリシーを表示できます。

CJA にとって特に重要なラベルは次のとおりです。

* この `C8` ラベル — **[!UICONTROL 測定なし]**. このラベルは、組織の Web サイトやアプリでデータを分析に使用できないことを示します。

* この `C12` ラベル — **[!UICONTROL 一般的なデータの書き出しがありません]**. この方法でラベル付けされたスキーマフィールドは、CJA から（レポート、書き出し、API などを介して）書き出したりダウンロードしたりすることはできません。

ラベル付け自体は、これらのデータ使用ラベルが適用されるという意味ではありません。 それが政策の目的です ポリシーは、 [ポリシーサービス API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform

CJA では、次の 2 つのAdobe定義ポリシーが表示され、レポートおよびダウンロード/共有に影響します。

* **[!UICONTROL Analytics の適用]** ポリシー
* **[!UICONTROL ダウンロードを強制]** ポリシー

## CJA データビューでのデータラベルの表示

Experience Platformで作成したデータラベルは、データビューユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、次の操作を示します [!UICONTROL データ使用ラベル] 現在、次のフィールドに適用されます。<p>![](assets/data-label-left.png) |
| の下の右パネル [コンポーネント設定](/help/data-views/component-settings/overview.md) | 任意 [!UICONTROL データ使用ラベル] 以下に示します。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | 次の項目を追加できます。 [!UICONTROL データ使用ラベル] 列で [!UICONTROL 含まれるコンポーネント] データビューの列 列セレクターアイコンをクリックし、「 」を選択します。 **[!UICONTROL データ使用ラベル]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側の基準線のフィルターアイコンをクリックし、次の条件でデータビューコンポーネントをフィルタリングします。 **[!UICONTROL データガバナンス]** およびのタイプ **[!UICONTROL ラベル]**:

![](assets/filter-labels.png)

クリック **[!UICONTROL 適用]** を使用して、どのコンポーネントにラベルがアタッチされているかを確認します。

## データビューのデータガバナンスポリシーに対するフィルタリング

分析または書き出しの目的で特定の CJA データビュー要素の使用をブロックするポリシーがオンになっているかどうかを確認できます。

再度、左側のパネルのフィルターアイコンをクリックし、の下に表示します。 **[!UICONTROL データガバナンス]**&#x200B;をクリックし、 **[!UICONTROL ポリシー]**:

![](assets/filter-policies.png)

クリック **[!UICONTROL 適用]** 有効化されているポリシーを確認する。

## 有効なポリシーがデータビューに与える影響

この **[!UICONTROL Analytics の適用]** または **[!UICONTROL ダウンロードを強制]** ポリシーがオンになると、特定のデータラベル（C8 や C12 など）が関連付けられているスキーマコンポーネントは、データビューに追加できません。

これらのコンポーネントは、左側のパネルでグレー表示されます [!UICONTROL スキーマフィールド] リスト：

![](assets/component-greyed.png)

また、フィールドがブロックされたデータビューは保存できません。

>[!MORELIKETHIS]
>[機密データのダウンロード](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Report Builderの制限ラベル](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)

