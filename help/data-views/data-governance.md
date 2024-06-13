---
title: ラベルとポリシー
description: Adobe Experience Platform で定義されたデータラベルとポリシーが、Customer Journey Analytics のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 6526ca2b7caaf64acf29d97c859c3e813d003d2d
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 45%

---

# ラベルとポリシー

Experience Platformでデータセットを作成する場合は、以下を作成できます [データ使用ラベル](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) データセットの一部またはすべての要素。 これらのラベルとポリシーは、Customer Journey Analytics で表示できます。

次のラベルは、Customer Journey Analytics にとって特に重要です。

* `C8` ラベル - **[!UICONTROL 測定なし]**。このラベルは、組織の web サイトやアプリで分析に対してデータが使用できないことを示します。

* この `C12` ラベル - **[!UICONTROL 一般的なデータの書き出しがありません]**. この方法でラベル付けされたスキーマフィールドは、Customer Journey Analytics から（レポート、書き出し、API などを介して）書き出しまたはダウンロードはできません。

>[!NOTE]
>
>データ使用状況ラベルは、ステッチされたデータセットに自動的に生成されません。ただし、手動で追加することはできます。

「ラベル付け」自体は、これらのデータ使用状況ラベルが適用されるという意味ではありません。これを行うにはポリシーを使用します。ポリシーを作成するには、 [EXPERIENCE PLATFORMUI](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) または経由 [Policy Service API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) Experience Platformで。

Experience Platformでは、次の 2 つのAdobe定義のポリシーを使用できます。これらのポリシーは、Customer Journey Analyticsに表示され、レポートやデータの書き出しに影響を与える可能性があります。

* **[!UICONTROL 使用分析とユーザーベースの測定を制限]** ポリシー、使用する `C8` ラベル、
* **[!UICONTROL データの書き出しを制限]** ポリシー、使用する `C12` ラベル。

## Customer Journey Analytics データビューでのデータラベルの表示

自分または他のユーザーがExperience Platformで作成したデータラベルは、データビューのユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用される[!UICONTROL データ使用状況ラベル]が表示されます。<p>![](assets/data-label-left.png) |
| [コンポーネント設定](/help/data-views/component-settings/overview.md)の下の右パネル | すべての[!UICONTROL データ使用状況ラベル]はここに一覧表示されます。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「[!UICONTROL 含まれるコンポーネント]」列に、「[!UICONTROL データ使用状況ラベル]」を列として追加できます。列セレクターアイコンを選択し、 **[!UICONTROL データ使用ラベル]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、 [!UICONTROL フィルター] アイコンをクリックし、データビューコンポーネントを次の基準でフィルタリングします **[!UICONTROL データガバナンス]** およびタイプ **[!UICONTROL ラベル]**:

![](assets/filter-labels.png)

「**[!UICONTROL 適用]**」をクリックして、どのコンポーネントにラベルが付いているかを確認します。

## データビューでデータガバナンスポリシーをフィルタリング

ポリシー（自分で作成した、という名前のポリシーなど）があるかどうかを確認できます **[!UICONTROL Analytics の適用]**）がオンになっています。 また、特定のCustomer Journey Analyticsデータビュー要素の分析またはデータ書き出しの使用をポリシーがブロックしているかどうかも考慮されます。

もう一度選択します [!UICONTROL フィルター] アイコンが左パネルの下に表示されます。 **[!UICONTROL データガバナンス]**&#x200B;を選択 **[!UICONTROL ポリシー]**:

![「使用制限の分析」と「ユーザーベースの測定」が選択されていることを示すリストによるフィルターの含まれるコンポーネント](assets/filter-policies.png)

クリック **[!UICONTROL 適用]** を使用して、有効になっているポリシーを確認します。

## 有効なポリシーがデータビューに与える影響

C8 または C12 ラベルの付いた 1 つ以上のポリシーをオンにすると、特定のデータラベルが適用されたスキーマコンポーネントは、データビューに追加できません。

これらのコンポーネントは左側のパネルでグレー表示されます [!UICONTROL スキーマフィールド] リスト :

![グレー表示されたコンポーネントと、データの使用を制限するポリシーがこのフィールドに適用されていることを示すポリシーメッセージ](assets/component-greyed.png)

また、ブロックされたフィールドがあるデータビューは保存できません。

データビューで既にコンポーネントを定義しているExperience Platform内のフィールドまたはフィールドグループに、（ポリシーを通じて）アクセスラベルとデータガバナンスラベルを適用する場合は、注意が必要です。 このダイアログが表示される場合があります。

![違反](assets/violation.png)

最初に違反を解決する必要があります（例えば、データビューからコンポーネントを削除するなど）。


>[!MORELIKETHIS]
>
>[機密データのダウンロード](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder の制限ラベルとは？](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


