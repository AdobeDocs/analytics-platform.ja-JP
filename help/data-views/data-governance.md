---
title: ラベルとポリシー
description: Adobe Experience Platform で定義されたデータラベルとポリシーが、Customer Journey Analytics のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
hold: true
autotag-review: '2026-05-19T08:59:31.818Z'
TQID: 'https://experienceleague.adobe.com/SoIHLRSx90B4j8EkHWBVt3rVtt-968TN8ocWU2zuYN4'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4id: eb00932f-4d46-46bc-b1d8-10de7588db8did: b3197353-f189-4932-8378-3f3bc40e6071
subfeature_v2: id: e1471301-a189-438e-8d48-264a8db508a6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 1254207526535e44c848dfeed0052339fbd8d65d
workflow-type: tm+mt
source-wordcount: 745
ht-degree: 66%

---

# ラベル、ポリシー、マーケティング活動

Experience Platform でデータセットを作成する場合、データセットの一部またはすべての要素に対して[データ使用状況ラベル](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/labels/reference)を作成できます。 これらのラベルとポリシーは、Customer Journey Analytics で表示できます。

次のラベルとマーケティングアクションは、Customer Journey Analyticsにとって特に重要です。


| ラベル | マーケティングアクション | 定義 |
|---------|----------|---------|
| `C2` | [!UICONTROL  サードパーティに書き出し] | ラベルと関連するマーケティングアクションは、対応するDULE ポリシーが有効になっている場合、データをサードパーティに書き出せないことを示します。 |
| `C3` | [!UICONTROL 直接識別可能なデータと組み合わせる] | ラベルと関連するマーケティングアクションは、対応するDULE ポリシーが有効になっている場合、データを組み合わせたり、直接識別可能な情報と使用したりできないことを示します。 |
| `C8` | [!UICONTROL Analytics] | ラベルと関連するマーケティングアクションは、対応するDULE ポリシーが有効になっている場合、組織のweb サイトまたはアプリでの分析にデータを使用できないことを示します。 |
| `C9` | [!UICONTROL  データサイエンス ] | ラベルと関連するマーケティングアクションは、対応するDULE ポリシーが有効になっている場合、データサイエンスワークフローでデータを使用できないことを示します。 |
| `C12` | [!UICONTROL  データの書き出し] | ラベルと関連するマーケティングアクションは、対応するDULE ポリシーが有効になっている場合、この方法でラベル付けされたスキーマフィールドをCustomer Journey Analyticsから（レポート、エクスポート、APIなどを介して）エクスポートまたはダウンロードできないことを示します。 |

>[!NOTE]
>
>データ使用状況ラベルは、ステッチされたデータセットに自動的に生成されません。 ただし、手動で追加することはできます。

「ラベル付け」自体は、これらのデータ使用状況ラベルが適用されるという意味ではありません。 これを行うにはポリシーを使用します。 ポリシーは、[Experience Platform UI](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/policies/user-guide) を使用するか、Experience Platform で [Policy Service API](https://experienceleague.adobe.com/ja/docs/experience-platform/data-governance/api/overview) を介して作成できます。

Customer Journey Analyticsで表示され、レポートとデータの書き出しに影響する、Adobeで定義された5つのポリシーをExperience Platformで使用できます。


| ポリシー | ラベル |
|---------|----------|
| [!UICONTROL  サードパーティデータの書き出しを制限] | `C2` |
| [!UICONTROL 直接識別可能なデータの組み合わせを制限] | `C3` |
| [!UICONTROL 使用状況分析とユーザーベースの測定を制限] | `C8` |
| [!UICONTROL  データサイエンスの制限] | `C9` |
| [!UICONTROL  データ書き出しを制限] | `C12` |


## Customer Journey Analytics データビューでのデータラベルの表示

Experience Platform で自分または他のユーザーが作成したデータラベルは、データビューのユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用される[!UICONTROL データ使用状況ラベル]が表示されます。<p>![](assets/data-label-left.png) |
| [コンポーネント設定](/help/data-views/component-settings/overview.md)の下の右パネル | すべての[!UICONTROL データ使用状況ラベル]はここに一覧表示されます。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「[!UICONTROL 含まれるコンポーネント]」列に、「[!UICONTROL データ使用状況ラベル]」を列として追加できます。 列セレクターアイコンを選択し、「**[!UICONTROL データ使用状況ラベル]**」を選択します。<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側のパネルの[!UICONTROL フィルター]アイコンを選択し、**[!UICONTROL データガバナンス]**&#x200B;および&#x200B;**[!UICONTROL ラベル]**&#x200B;のタイプで、データビューコンポーネントをフィルタリングします。

![](assets/filter-labels.png)

「**[!UICONTROL 適用]**」をクリックして、どのコンポーネントにラベルが付いているかを確認します。

## データビューでデータガバナンスポリシーをフィルタリング

ポリシー（例えば、自身が作成した、「**[!UICONTROL Analytics の適用]**」という名前のポリシー）がオンになっているかどうかを確認できます。 また、そのポリシーによって、分析またはデータの書き出しのための特定の Customer Journey Analytics データビュー要素の使用がブロックされるかどうかも確認できます。

再度、左側のパネルの&#x200B;**[!UICONTROL データガバナンス]**&#x200B;下の [!UICONTROL フィルター] アイコン、「**[!UICONTROL ポリシー]**」の順に選択します。

![「使用状況分析とユーザーベースの測定を制限」が選択されていることを示すリストで含まれるコンポーネントをフィルタリングする](assets/filter-policies.png)

「**[!UICONTROL 適用]**」をクリックし、有効になっているポリシーを確認します。

## 有効なポリシーがデータビューに与える影響

1つ以上のポリシーがC1、C2、C3、C8、C9またはC12 ラベルでオンになっている場合、特定のデータラベルが適用されているスキーマコンポーネントをデータビューに追加することはできません。

これらのコンポーネントは、左側のパネルの[!UICONTROL スキーマフィールド]リストでグレー表示されます。

![グレー表示されたコンポーネントと、データの使用を制限するポリシーがこのフィールドに適用されていることを示すポリシーメッセージ](assets/component-greyed.png)

また、ブロックされたフィールドがあるデータビューは保存できません。

データビューで既にコンポーネントが定義されている Experience Platform のフィールドまたはフィールドグループに、アクセスラベルとデータガバナンスラベルを（ポリシーを通じて）適用する場合は注意が必要です。 このダイアログが表示される可能性があります。

![違反](assets/violation.png)

まず、違反を解決する必要があります（例えば、データビューからコンポーネントを削除するなど）。


>[!MORELIKETHIS]
>
>[機密データのダウンロード](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Report Builder の制限ラベルとは？](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


