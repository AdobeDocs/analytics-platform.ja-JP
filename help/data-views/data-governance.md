---
title: ラベルとポリシー
description: Adobe Experience Platform で定義されたデータラベルとポリシーが、Customer Journey Analytics のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 950c121e6c889e202f048d4a33e8fecde3cd9efe
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 67%

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

Customer Journey Analytics では、次の 2 つのアドビが定義するポリシーが表示され、レポートおよびダウンロード／共有に影響します。

* **[!UICONTROL Analytics の適用]** ポリシー
* **[!UICONTROL ダウンロードの適用]**&#x200B;ポリシー

## Customer Journey Analytics データビューでのデータラベルの表示

自分または他のユーザーがExperience Platformで作成したデータラベルは、データビューのユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用される[!UICONTROL データ使用状況ラベル]が表示されます。<p>![](assets/data-label-left.png) |
| [コンポーネント設定](/help/data-views/component-settings/overview.md)の下の右パネル | すべての[!UICONTROL データ使用状況ラベル]はここに一覧表示されます。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「[!UICONTROL 含まれるコンポーネント]」列に、「[!UICONTROL データ使用状況ラベル]」を列として追加できます。列セレクターアイコンをクリックし、「**[!UICONTROL データ使用状況ラベル]**」を選択します。<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側のパネルの[!UICONTROL フィルター]アイコンをクリックし、**[!UICONTROL データガバナンス]**&#x200B;および&#x200B;**[!UICONTROL ラベル]**&#x200B;のタイプで、データビューコンポーネントをフィルタリングします。

![](assets/filter-labels.png)

「**[!UICONTROL 適用]**」をクリックして、どのコンポーネントにラベルが付いているかを確認します。

## データビューでデータガバナンスポリシーをフィルタリング

あるポリシー（例えば、Analytics の適用という名前のポリシー）がオンになっているかどうか、およびそのポリシーが Analytics 用の特定のCustomer Journey Analyticsデータビュー要素の使用をブロックしているかどうかを確認できます。

再度、左側のパネルの&#x200B;**[!UICONTROL データガバナンス]**&#x200B;下の [!UICONTROL フィルター] アイコン、「**[!UICONTROL ポリシー]**」の順にクリックします。

![「Analytics を適用」が選択されていることを示すリストで含まれるコンポーネントをフィルタリングする](assets/filter-policies.png)

クリック **[!UICONTROL 適用]** を使用して、有効になっているポリシーを確認します。

## 有効なポリシーがデータビューに与える影響

**[!UICONTROL Analytics の適用]**&#x200B;ポリシーがオンになると、特定のデータラベル（C8 など）が関連付けられているスキーマコンポーネントは、データビューに追加できません。

これらのコンポーネントは左側のパネルでグレー表示されます [!UICONTROL スキーマフィールド] リスト :

![グレー表示されたコンポーネントと、データの使用を制限するポリシーがこのフィールドに適用されていることを示すポリシーメッセージ](assets/component-greyed.png)

また、ブロックされたフィールドがあるデータビューは保存できません。

データビューで既にコンポーネントを定義しているExperience Platform内のフィールドまたはフィールドグループに、アクセスラベルとデータガバナンスラベルを適用する場合は注意が必要です。 このダイアログが表示される場合があります。

![違反](assets/violation.png)

最初に違反を解決する必要があります（例えば、データビューからコンポーネントを削除するなど）。


>[!MORELIKETHIS]
>
>[機密データのダウンロード](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder の制限ラベルとは？](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


