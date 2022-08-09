---
title: Adobe Experience Platform Data Governance に対する CJA のサポート
description: AEP で定義されたデータラベルとポリシーが CJA のレポートに与える影響について説明します。
mini-toc-levels: 3
source-git-commit: 82060862c64aae10ea6dd375a8cd65d67ee21704
workflow-type: tm+mt
source-wordcount: '845'
ht-degree: 1%

---


# Adobe Experience Platform Data Governance に対する CJA のサポート

>[!NOTE]
>
>この機能は、現在、[限定的にテスト中](/help/release-notes/releases.md)です。

CJA との統合 [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) では、機密性の高い CJA データのラベル付けとプライバシーポリシーの実施を可能にします。

Experience Platformが使用するデータセットで作成されたプライバシーラベルとポリシーは、 CJA データビューワークフローで表示できます。 これらのラベルは、機密性の高いフィールドから指標やディメンションを作成するユーザーに対して、停止または警告を出します。

また、データが CJA から（レポート、書き出し、API などを介して）書き出されると、警告またはラベルが追加され、特定の方法で処理する必要のある機密情報がレポートに含まれていることをユーザーに通知します。

この統合により、コンプライアンスをより簡単に管理できます。 組織のデータ管理人は、使用を制限するポリシーを設定できます。 その結果、CJA ユーザーは、データ管理人が定義したポリシーに準拠していることを知り、より自信を持ってデータを使用できます。

## Adobe Experience Platformでのラベル付けとポリシー

データセットをExperience Platformで作成する際に、 [データ使用ラベル](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) の一部またはすべての要素が含まれている場合。 これまで、これらのラベルは CJA では公開されていませんでした。 このリリースでは、これらのラベルを CJA で表示できます。 CJA にとって特に重要なラベルは次のとおりです。

* この `C8` ラベル — **[!UICONTROL 測定なし]**. このラベルは、組織の Web サイトやアプリでデータを分析に使用できないことを示します。

* この `C12` ラベル — **[!UICONTROL 一般的なデータの書き出しがありません]**. この方法でラベル付けされたスキーマフィールドは、CJA から（レポート、書き出し、API などを介して）書き出したりダウンロードしたりすることはできません。

ラベル付け自体は、これらのデータ使用ラベルが適用されるという意味ではありません。 それが政策の目的です ポリシーは、 [ポリシーサービス API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) Experience Platform

ポリシーには次の 2 つのコンポーネントがあります。制限されたデータ使用ポリシーのコンテキスト内でデータコンシューマーが実行できるデータラベルとマーケティングアクション。 CJA のコンテキストでは、2 つのAdobe定義 [マーケティングアクション](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix) は重要です。

* Analytics — 組織のサイトやアプリの消費者使用状況の測定、分析、レポートなど、分析目的でデータを使用します。

* データをサードパーティ ( つまり、Adobe環境外 ) に書き出す。

ポリシーと共にラベルとマーケティングアクションを結び付け、ポリシーをオンにします。 このポリシーは、ラベルとマーケティングアクションを使用し、次のように記述します。この制限を適用します。 CJA では、次の 2 つのAdobe定義ポリシーが表示され、レポートおよびダウンロード/共有に影響します。

* Analytics ポリシーの適用
* ダウンロードポリシーの適用


### CJA データビューでのデータラベルの表示

Experience Platformで作成したデータラベルは、データビューユーザーインターフェイスで次の 3 つの場所に表示されます。

| 場所 | 説明 |
| --- | --- |
| スキーマフィールドの情報ボタン | このボタンをクリックすると、現在フィールドに適用されているデータ使用ラベルが示されます。<p>![](assets/data-label-left.png) |
| の下の右パネル [コンポーネント設定](/help/data-views/component-settings/overview.md) | データ使用ラベルは次のとおりです。<p>![](assets/data-label-right.png) |
| データラベルを列として追加 | データビューの「含まれるコンポーネント」列にデータラベルを列として追加できます。 列セレクターアイコンをクリックして、「データ使用状況ラベル」を選択します。<p>![](assets/data-label-column.png) |

### データビューのデータガバナンスラベルに対するフィルター

データビューエディターで、左側のトレールのフィルターアイコンをクリックし、データビューコンポーネントをデータガバナンスラベルでフィルターします。

![](assets/filter-labels.png)

クリック **[!UICONTROL 適用]** を使用して、どのコンポーネントにラベルがアタッチされているかを確認します。

### データビューのデータガバナンスポリシーに対するフィルタリング

分析または書き出しの目的で特定の CJA データビュー要素の使用をブロックするポリシーがオンになっているかどうかを確認できます。

再度、左側のパネルでフィルターアイコンをクリックし、「データガバナンス」で「ポリシー」をクリックします。

![](assets/filter-policies.png)

クリック **[!UICONTROL 適用]** 有効なポリシーを確認するには _このデータビューの_

### 方法 [!UICONTROL Analytics の適用] ポリシーが Workspace プロジェクトに影響する

このポリシーをオンにした場合、特定のデータラベル（C8 など）が関連付けられているこれらのスキーマフィールドは、CJA Workspace 内の分析目的に使用できません。

レポートの場合は、

* これらのフィールドは、データビューに追加できず、左側のパネルでグレー表示されます [!UICONTROL スキーマフィールド] リスト。
* フィールドがブロックされたデータビューは保存できません。

分析が禁止されている項目を含むデータビューに対して Workspace 分析を実行しようとすると、次のような通知が表示されます。

![](assets/policy-enforce.png)

個々のコンポーネントでは、メッセージは次のようになります。

![](assets/policy-enforce2.png)

### 方法 [!UICONTROL ダウンロードを強制] ポリシーが Workspace プロジェクトに影響する

このポリシーをオンにした場合、Workspace プロジェクトのダウンロード（電子メールや PDF の共有など）は機密フィールドをハッシュ化します。 引き続き Workspace のこれらのフィールドで分析を実行できますが、電子メールで送信しようとした場合や、プロジェクトを共有しようとした場合、ブロックされたフィールドは.pdf ファイル内でハッシュ化された項目として表示されます。

ここにスクリーンショットを追加します。

### ラベルをReport Builder

詳しくは、 _この節_ を参照してください。 （クリスティンのドキュメントへのリンク）
