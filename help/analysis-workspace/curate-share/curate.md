---
description: キュレーションを使用すると、プロジェクトを共有する前にコンポーネントを制限できます。
keywords: Analysis Workspace キュレーション
title: プロジェクトのキュレーション
feature: Curate and Share
exl-id: f9636191-8414-458c-9881-8c03f3d45efb
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: ht
source-wordcount: '509'
ht-degree: 100%

---

# プロジェクトのキュレーション

キュレーションを使用すると、プロジェクトを共有する前にコンポーネント（ディメンション、指標、セグメント、日付範囲）を制限できます。受信者がプロジェクトを開くと、キュレーションされたコンポーネントの制限付きセットが表示されます。キュレーションはオプションですが、プロジェクトを共有する前に行うことをお勧めします。

>[!NOTE]
> 製品プロファイルは、ユーザーに表示されるコンポーネントを管理する主要メカニズムです。[Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=ja) で管理されます。キュレーションはセカンダリセグメントです。

## プロジェクトキュレーションの適用

1. **[!UICONTROL 共有]**／**[!UICONTROL プロジェクトデータをキュレート]** をクリックします。
プロジェクトで使用されるコンポーネントが自動的に追加されます。
1. （オプション）他のコンポーネントを追加するには、共有するコンポーネントを左側のパネルから「[!UICONTROL コンポーネントをキュレート]」フィールドにドラッグします。
1. 「**[!UICONTROL 完了]**」をクリックします。

キュレーションは、[!UICONTROL 共有]メニューで「**[!UICONTROL キュレーションと共有]**」をクリックして適用することもできます。このオプションは、プロジェクト内で使用されているコンポーネントに合わせて、プロジェクトを自動的にキュレーションします。上記の手順に従って、追加のコンポーネントを追加できます。

![プロジェクトで使用されているコンポーネントを表示するコンポーネントをキュレートウィンドウ。](assets/curation-field.png)

## キュレーションされたプロジェクトの表示

キュレーションされたプロジェクトを受信者が開くと、ユーザーには、定義したキュレーション済みのコンポーネントのセットのみが表示されます。

![定義したコンポーネントを表示する共有済みのキュレートされたプロジェクト。](assets/curate-project.png)

## プロジェクトキュレーションの削除

プロジェクトのキュレーションを削除し、左側のパネルでコンポーネントの完全なセットを復元するには：

1. **[!UICONTROL 共有]**／**[!UICONTROL プロジェクトデータをキュレート]**&#x200B;をクリックします。
1. 「**[!UICONTROL キュレーションを削除]**」をクリックします。
1. 「**[!UICONTROL 完了]**」をクリックします。

## コンポーネントキュレーションオプション

キュレートされたプロジェクトでは、受信者に、左側のパネルに&#x200B;**[!UICONTROL すべてのコンポーネントを表示]**&#x200B;するオプションが表示されます。「[!UICONTROL すべてを表示]」では、以下に応じて異なるコンポーネントセットを表示します。

* ユーザーの権限レベル（管理者／非管理者）
* プロジェクトの役割（所有者／編集者／その他）
* 適用されるキュレーションのタイプ（プロジェクトレベル）

| キュレーションのタイプ | 管理者への表示範囲 | 管理者以外のプロジェクト所有者（または編集の役割）への表示範囲 | 管理者以外の重複の役割への表示範囲 |
| --- | --- | --- | --- |
| **データビューから「非表示」になるコンポーネント** | レポートに使用できるすべてのデータビューコンポーネント（非表示のコンポーネントでは「すべて表示」をクリックする必要があります） | レポートに使用できません | レポートに使用できません |
| **データビューに追加またはデータビューから削除されたコンポーネント** | データビューに追加されたコンポーネントのみ（非表示か非表示でないかを問わず）。 管理者は、データビューで定義されていないフィールドやコンポーネントについてレポートすることはできません。 | データビューに追加されたコンポーネント、またはユーザーが所有または共有するコンポーネントのみ。 非表示のコンポーネントは使用できません（仮想レポートスイートキュレーションなど）。 | DV に追加されたコンポーネントのみが非表示にならず、プロジェクトキュレーションに含まれる。 |
| **プロジェクト内のキュレートされたコンポーネント** | レポートに使用できるすべてのデータビューコンポーネント（非表示のコンポーネントでは「すべて表示」をクリックする必要があります） | 非表示以外のすべてのデータビューコンポーネント（「すべて表示」をクリックする必要があります） | キュレートされたコンポーネントと、ユーザーが所有または共有するコンポーネントのみ |
| **非表示のコンポーネントを含むデータビューを使用してキュレートされたプロジェクト** | レポートに使用できるすべてのデータコンポーネント（非表示およびキュレートされていないコンポーネントでは、「すべて表示」をクリックする必要があります） | キュレートされていないすべてのプロジェクトコンポーネント、非表示でないすべてのデータビューコンポーネントおよびユーザーが所有または共有するすべてのコンポーネント | キュレートされたコンポーネントと、ユーザーが所有または共有するコンポーネントのみ |
