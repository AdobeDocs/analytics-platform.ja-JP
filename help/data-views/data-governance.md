---
title: ラベルとポリシー
description: AEP で定義されたデータラベルとポリシーが、CJA のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 7962114aaab42a283f1cb35a312b0a707038c31a
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# ラベルとポリシー

Experience Platform でデータセットを作成する場合、データセットの一部またはすべての要素に対して[データ使用状況ラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=ja)を作成できます。これまで、これらのラベルは CJA では公開されていませんでした。このリリースでは、CJA でこれらのラベルとポリシーを表示できます。

CJA にとって特に重要なラベルは次のとおりです。

* `C8` ラベル - **[!UICONTROL 測定なし]**。このラベルは、組織の web サイトやアプリで分析に対してデータが使用できないことを示します。

* `C12` ラベル - **[!UICONTROL 一般的なデータの書き出しがありません]**。この方法でラベル付けされたスキーマフィールドは、CJA から（レポート、書き出し、API などを介して）書き出しまたはダウンロードはできません。

「ラベル付け」自体は、これらのデータ使用状況ラベルが適用されるという意味ではありません。これを行うにはポリシーを使用します。 Experience Platform で [Policy Service API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=ja) を介してポリシーを作成します。

CJA では、次の 2 つのアドビが定義するポリシーが表示され、レポートおよびダウンロード／共有に影響します。

* **[!UICONTROL Analytics の適用]** ポリシー
* **[!UICONTROL ダウンロードの適用]**&#x200B;ポリシー

## CJA データビューでのデータラベルの表示

Experience Platform で作成したデータラベルは、データビューのユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用される[!UICONTROL データ使用状況ラベル]が表示されます。<p>![](assets/data-label-left.png) |
| [コンポーネント設定](/help/data-views/component-settings/overview.md)の下の右パネル | すべての[!UICONTROL データ使用状況ラベル]はここに一覧表示されます。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「[!UICONTROL 含まれるコンポーネント]」列に、「[!UICONTROL データ使用状況ラベル]」を列として追加できます。列セレクターアイコンをクリックし、「**[!UICONTROL データ使用状況ラベル]**」を選択します。<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側のパネルのフィルターアイコンをクリックし、**[!UICONTROL データガバナンス]**&#x200B;および&#x200B;**[!UICONTROL ラベル]**&#x200B;のタイプで、データビューコンポーネントをフィルタリングします。

![](assets/filter-labels.png)

「**[!UICONTROL 適用]**」をクリックして、どのコンポーネントにラベルが付いているかを確認します。

## データビューでデータガバナンスポリシーをフィルタリング

分析または書き出しの目的で特定の CJA データビュー要素の使用をブロックするポリシーがオンになっているかどうかを確認できます。

再度、左側のパネルの&#x200B;**[!UICONTROL データガバナンス]**&#x200B;下のフィルターアイコン、「**[!UICONTROL ポリシー]**」の順にクリックします。

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
>[Report Builder の制限ラベルとは](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=ja)


