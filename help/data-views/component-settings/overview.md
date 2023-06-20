---
title: コンポーネント設定
description: データビューコンポーネントのコア設定を表示します。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 70%

---

# コンポーネント設定

データビューコンポーネントで使用されるコア設定。

![コンポーネント設定](../assets/component-settings.png)

| 設定 | 説明／使用例 |
| --- | --- |
| [!UICONTROL コンポーネントの種類] | 必須。コンポーネントを指標からDimensionに変更するか、その逆の方法で変更できます。 このドロップダウン選択を変更すると、コンポーネントが、含まれる各コンポーネント領域に移動します。 |
| [!UICONTROL コンポーネント名] | 必須。Analysis Workspace に表示されるわかりやすい名前を指定できます。コンポーネントの名前を変更して、データビューに固有の名前を付けることができます。 |
| [!UICONTROL 説明] | オプション（推奨）。 コンポーネントに関する情報を他のユーザーに提供します。 |
| [!UICONTROL タグ] | （任意）。Analysis Workspace UI で検索／フィルタリングを行いやすくするために、カスタムタグまたは標準搭載のタグでコンポーネントにタグを付けることができます。 |
| [!UICONTROL コンテキストラベル] | （任意）。コンポーネントに適用できる、使用可能なシステム定義のラベルのドロップダウンリストです。 これらのラベルは、Analysis Workspace のプロジェクトまたはパネルでのレポートに使用されるコンポーネントのセットを定義するために必要になる場合があります。 |
| [!UICONTROL スキーマフィールド名] | スキーマフィールドの名前。 |
| [!UICONTROL データセットタイプ] | 必須。コンポーネントの元となるデータセットタイプ（イベント、参照、プロファイル）を示す編集不可のフィールド。 |
| [!UICONTROL データセット] | コンポーネントの元のデータセットを示す編集不可のフィールド。 このフィールドには、複数のデータセットを含めることができます。 |
| [!UICONTROL スキーマタイプ] | コンポーネントのデータタイプを示す編集不可のフィールド。 Platform では、サポートされている任意のスキーマフィールドタイプを使用できますが、Platform では、一部のフィールドタイプがサポートされているわけではありません。Customer Journey Analytics 次のデータタイプがサポートされています。`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` および `Boolean` です。 次の項目のみ `String` スキーマデータタイプは、現在、参照データセットで使用できます。 |
| [!UICONTROL コンポーネント ID] | 必須。この [Customer Journey AnalyticsAPI](https://adobe.io/cja-apis/docs) は、このフィールドを使用してコンポーネントを参照します。 データビューの各コンポーネントは、一意である必要があります。アドビは、各コンポーネントの ID を自動的に生成します。ただし、編集アイコンをクリックして、コンポーネント ID を変更することはできます。コンポーネント ID を変更すると、このコンポーネントを含む既存の Workspace プロジェクトがすべて機能しなくなります。単一のデータビュー内では各コンポーネントに一意の ID が必要ですが、他のデータビュー内では同じコンポーネント ID を使用できます。 他のデータビューで同じコンポーネント ID を使用すると、データビューをまたいで Workspace プロジェクトに互換性を持たせることができます。<br/>プロファイルおよび参照ベースのコンポーネントの場合、コンポーネント ID には、データセット ID に基づく ID プレフィックスが付きます ( 例： `642b28fcc1f0ee1c074265a0.person.name.firstName`) をクリックします。 プロファイルや参照ベースのコンポーネントを再利用する場合（例： ）。 `person.name.firstName`を Workspace プロジェクトに追加し、このコンポーネントを異なるデータビューで設定する場合は、コンポーネント ID の名前を一意に変更してください ( 例： `myUniqueID.person.name.firstName`) を含める必要があります。 |
| [!UICONTROL パス] | 必須。コンポーネントの元となるスキーマパスを示す編集不可のフィールド。 |
| [!UICONTROL データ使用状況ラベル] | Adobe Experience Platform でこのコンポーネントに割り当てられたデータ使用状況ラベル。 [詳細情報](/help/data-views/data-governance.md) |
| [!UICONTROL レポートでコンポーネントを非表示] | 管理者以外のユーザー向けデータビューからコンポーネントをキュレートできます。 管理者は、Analysis Workspace プロジェクトで「[!UICONTROL すべてのコンポーネントを表示]」をクリックしてアクセスできます。 |

{style="table-layout:auto"}

次に、データビューのコンポーネント設定に関するビデオを示します。

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
