---
title: ラベルとポリシー
description: AEP で定義されたデータラベルとポリシーが、CJA のデータビューとレポートに与える影響について説明します。
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: a28247e861e2f8853a6e2d2b81e7f6ed221caec0
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 2%

---

# ラベルとポリシー

>[!NOTE]
>
>この機能は、現在、[限定的にテスト中](/help/release-notes/releases.md)です。

データセットをExperience Platformで作成する際に、 [データ使用ラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) の一部またはすべての要素が含まれている場合。 これまで、これらのラベルは CJA では公開されていませんでした。 このリリースでは、これらのラベルを CJA で表示できます。 CJA にとって特に重要なラベルは次のとおりです。

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
| データラベルを列として追加 | 次の項目を追加できます。 [!UICONTROL データラベル] 列で [!UICONTROL 含まれるコンポーネント] データビューの列 列セレクターアイコンをクリックし、「 」を選択します。 **[!UICONTROL データ使用ラベル]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側のトレールのフィルターアイコンをクリックし、データビューコンポーネントをデータガバナンスラベルでフィルターします。

![](assets/filter-labels.png)

クリック **[!UICONTROL 適用]** を使用して、どのコンポーネントにラベルがアタッチされているかを確認します。

## データビューのデータガバナンスポリシーに対するフィルタリング

分析または書き出しの目的で特定の CJA データビュー要素の使用をブロックするポリシーがオンになっているかどうかを確認できます。

再度、左側のパネルでフィルターアイコンをクリックし、「データガバナンス」で「ポリシー」をクリックします。

![](assets/filter-policies.png)

クリック **[!UICONTROL 適用]** 有効化されているポリシーを確認する。

## 方法 [!UICONTROL Analytics の適用] ポリシーが Workspace プロジェクトに影響する

このポリシーをオンにした場合、特定のデータラベル（C8 など）が関連付けられているこれらのスキーマフィールドは、CJA Workspace 内の分析目的に使用できません。

レポートの場合は、

* これらのフィールドは、データビューに追加できず、左側のパネルでグレー表示されます [!UICONTROL スキーマフィールド] リスト。
* フィールドがブロックされたデータビューは保存できません。

分析が禁止されている項目を含むデータビューに対して Workspace 分析を実行しようとすると、次のような通知が表示されます。

![](assets/policy-enforce.png)

個々のコンポーネントでは、メッセージは次のようになります。

![](assets/policy-enforce2.png)

## 方法 [!UICONTROL ダウンロードを強制] ポリシーが Workspace プロジェクトに影響する

このポリシーをオンにした場合、Workspace プロジェクトの書き出しやダウンロード（PDF の電子メール送信や共有など）は、機密フィールドをハッシュ化します。 引き続き Workspace のこれらのフィールドで分析を実行できますが、電子メールで送信しようとした場合や、プロジェクトを共有しようとした場合、ブロックされたフィールドは.pdf ファイル内でハッシュ化された項目として表示されます。

ここにスクリーンショットを追加します。

## ラベルをReport Builder

詳しくは、 _この節_ を参照してください。 （クリスティンのドキュメントへのリンク）
