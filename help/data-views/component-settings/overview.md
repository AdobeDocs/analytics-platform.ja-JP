---
title: コンポーネント設定
description: データビューコンポーネントのコア設定を表示します。
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7bf74e02db581bdf11b7efe31b62f018320c7f22
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 97%

---

# コンポーネント設定 {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="コンポーネント設定"
>abstract="名前、説明、コンポーネントに関連するその他の設定を表示および設定します。このボックスをオンにすると、レポートで管理者以外のユーザーに対してこのコンポーネントが非表示になります。管理者は、Workspace プロジェクトで「**[!UICONTROL すべてのコンポーネントを表示]**」を選択して、コンポーネントにアクセスできます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="コンテキストラベル"
>abstract="コンテキストラベルを削除すると、コンポーネントが必要な特定のパネルまたはレポートに影響を与える可能性があります。"

<!-- markdownlint-enable MD034 -->


次の情報では、データビューコンポーネントが使用する設定について説明します。

![この節で説明するコンポーネント設定](../assets/component-settings.png)

| 設定 | 説明／使用例 |
| --- | --- |
| [!UICONTROL コンポーネントの種類] | 必須。コンポーネントを指標からディメンションに、またはその逆に変更できます。このドロップダウンの選択を変更すると、コンポーネントがそれぞれに含まれているコンポーネント領域で変更します。 |
| [!UICONTROL &#x200B; コンポーネント名 &#x200B;] | 必須。Analysis Workspace に表示されるわかりやすい名前を指定できます。コンポーネントの名前を変更して、データビューに固有の名前を付けることができます。 |
| [!UICONTROL 説明] | オプション（推奨）。 コンポーネントに関する情報を他のユーザーに提供します。 |
| [!UICONTROL コンテキストラベル] | （任意）。コンポーネントに適用できる、使用可能なシステム定義のラベルのドロップダウンメニュー。 <p>これらのラベルは、次の状況で必要になる場合があります。</p> <ul><li>Analysis Workspace プロジェクトの[実験パネル](/help/analysis-workspace/c-panels/experimentation.md)を使用して、実験レポートで使用できる一連のコンポーネントを定義する場合。<p>詳しくは、[Journey Optimizer との統合](/help/integrations/ajo.md#data-view)および[ターゲットレポート](/help/integrations/at.md)を参照してください。</p></li><li>アドビが提供するテンプレートを使用する場合。デフォルトでは、アドビが提供する一部のテンプレートは、データビューにないコンポーネントが含まれているので機能しません。<p>欠落している各コンポーネントに対して、一致するコンテキストラベルがデータビューで使用できます。データビューに既に存在するコンポーネントに一致するコンテキストラベルを追加するか、データビューに新しいコンポーネントを追加して、このコンポーネントにコンテキストラベルを追加する必要があります。</p><p>詳しくは、[テンプレートの作成と管理](/help/analysis-workspace/templates/create-templates.md)の記事の[特定のテンプレートのデータビューへの欠落しているコンポーネントの追加](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template)を参照してください。</p> |
| [!UICONTROL スキーマフィールド名] | スキーマフィールドの名前。 |
| [!UICONTROL データセットタイプ] | 必須。コンポーネントの元となるデータセットタイプ（イベント、参照、プロファイル）を示す編集不可のフィールド。 |
| [!UICONTROL データセット] | コンポーネントの元のデータセットを示す編集不可のフィールド。 このフィールドには、複数のデータセットを含めることができます。 |
| [!UICONTROL スキーマタイプ] | コンポーネントのデータタイプを示す編集不可のフィールド。Platform では、サポートされているスキーマフィールドタイプを使用できますが、Customer Journey Analytics でサポートされていないフィールドタイプもあります。次のデータタイプがサポートされています。`Integer`、`Int`、`Long`、`Double`、`Float`、`Number`、`Short`、`Byte`、`String` および `Boolean` です。現在、ルックアップデータセットでは `String` スキーマデータタイプのみを使用できます。 |
| [!UICONTROL コンポーネント ID] | 必須。[Customer Journey Analytics API](https://adobe.io/cja-apis/docs) は、このフィールドを使用してコンポーネントを参照します。データビューの各コンポーネントは、一意である必要があります。アドビは、各コンポーネントの ID を自動的に生成します。ただし、編集アイコンをクリックして、コンポーネント ID を変更することはできます。コンポーネント ID を変更すると、このコンポーネントを含む既存の Workspace プロジェクトがすべて機能しなくなります。単一のデータビュー内では各コンポーネントに一意の ID が必要ですが、他のデータビュー内では同じコンポーネント ID を使用できます。 他のデータビューで同じコンポーネント ID を使用すると、データビューをまたいで Workspace プロジェクトに互換性を持たせることができます。<br/>プロファイルとルックアップベースのコンポーネントの場合、コンポーネント ID には、データセット ID に基づく ID 接頭辞が付きます（例：`642b28fcc1f0ee1c074265a0.person.name.firstName`）。Workspace プロジェクトでプロファイルやルックアップベースのコンポーネント（`person.name.firstName` など）を再利用し、このコンポーネントを様々なデータビューで設定する場合は、データビュー全体で確実にコンポーネント ID を一意の名前に変更します（`myUniqueID.person.name.firstName` など）。 |
| [!UICONTROL パス] | 必須。コンポーネントの元となるスキーマパスを示す編集不可のフィールド。 |
| [!UICONTROL データ使用状況ラベル] | Adobe Experience Platform でこのコンポーネントに割り当てられたデータ使用状況ラベル。 [詳細情報](/help/data-views/data-governance.md)。 |
| [!UICONTROL レポートでコンポーネントを非表示] | 管理者以外のユーザー向けデータビューからコンポーネントをキュレートできます。 管理者は、Analysis Workspace プロジェクトで「[!UICONTROL すべてのコンポーネントを表示]」をクリックしてアクセスできます。 |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

デモビデオについて詳しくは、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [コンポーネントタイプ設定](https://video.tv.adobe.com/v/3412937/?quality=12&learn=on&captions=jpn){target="_blank"}を参照してください。

>[!ENDSHADEBOX]


