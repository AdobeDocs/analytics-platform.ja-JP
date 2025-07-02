---
title: 注釈を作成
description: Analysis Workspaceでの注釈の作成方法
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
source-git-commit: f3c9a000ae5baa19cb5a6cf0e0343de3a9685b56
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 86%

---

# 注釈を作成

デフォルトでは、管理者のみが注釈を作成できます。ユーザーには、他のコンポーネント（セグメント、計算指標など）と同様に、注釈を表示する権限があります。

ただし、管理者は、Admin Console を介して、**[!UICONTROL CJA Workspace アクセスの権限を編集]**&#x200B;の&#x200B;**[!UICONTROL レポートツール]**&#x200B;に対する&#x200B;**[!UICONTROL 注釈の作成]**&#x200B;権限をユーザーに付与できます。詳しくは、[ユーザーレベルのアクセス制御](/help/technotes/access-control.md#user-level-access)を参照してください。

注釈は、次の方法で作成できます。

![注釈の作成](assets/create-annotation.png)

* **A**。メインインターフェイスで、「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 注釈]**」を選択します。[[!UICONTROL 注釈]マネージャー](/help/components/annotations/manage-annotations.md)から 「![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL 追加]**]」を選択します。
* **B**。Workspace プロジェクトで、ビジュアライゼーションのコンテキストメニューから、「**[!UICONTROL 選択から注釈を作成]**」を選択します。
* **C**。Workspace プロジェクトで、折れ線グラフのコンテキストメニューから、「**[!UICONTROL 選択に注釈を付ける]**」を選択します。
* **D**。Workspace プロジェクトで、メニューから「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 注釈を作成]**」を選択します。
* **E**。Workspace プロジェクトで、ショートカット **[!UICONTROL Ctrl + Shift + O キー]**（Windows）または **[!UICONTROL Shift + Command + O キー]**（macOS）を使用します。

注釈を定義するには、[[!UICONTROL &#x200B; 注釈ビルダー &#x200B;]](#annotation-builder) を使用します。

<!-- Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## 注釈ビルダー {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="注釈の詳細"
>abstract="注釈を使用すると、コンテキストデータのニュアンスとインサイトを組織に効果的に伝えることができます。 注釈を使用すると、カレンダーイベントを特定のディメンションと指標に関連付けることができます。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="範囲"
>abstract="範囲を使用すると、どのデータに注釈を適用するかをカスタマイズできます。 計算指標とセグメントは、その定義で使用されるコンポーネントに適用される注釈を自動的に継承しません。 既存の注釈の範囲セクションに新しい計算指標を追加できます。新しいセグメントには新しい注釈が必要です。"

<!-- markdownlint-enable MD034 -->


**[!UICONTROL 注釈ビルダー]**&#x200B;ダイアログは、新しい注釈の作成または既存の注釈の編集に使用します。ダイアログのタイトルは、[[!UICONTROL 注釈]マネージャー](/help/components/annotations/manage-annotations.md)から作成または管理する注釈の場合、**[!UICONTROL 新しい注釈]**&#x200B;または&#x200B;**[!UICONTROL 注釈を編集]**&#x200B;になります。


>[!BEGINTABS]

>[!TAB 注釈ビルダー]

![次の節で説明するフィールドとオプションを表示する注釈の詳細ウィンドウ。](assets/annotation-builder.png){zoomable="yes"}

>[!TAB 注釈   編集] 

![次の節で説明するフィールドとオプションを表示する注釈の詳細ウィンドウ。](assets/create-edit-annotation.png){zoomable="yes"}

>[!ENDTABS]

1. 次の詳細を指定します（![必須](/help/assets/icons/Required.svg)は必須です）。

   | 要素 | 説明 |
   | --- | --- |
   | **[!UICONTROL データビュー]** | 注釈のデータビューを選択できます。定義した注釈は、選択したデータビューに基づいて、Workspace プロジェクトで注釈として使用できます。この選択は、「[!UICONTROL すべてのデータビューに適用]」を有効にしたときに無効になります。 |
   | **[!UICONTROL プロジェクトのみの注釈]** | 作成する注釈が作業中の Workspace プロジェクトにのみ表示されることを説明する情報ボックス。「**[!UICONTROL この注釈をすべてのプロジェクトで使用できるようにする]**」を有効にして、注釈をすべてのプロジェクトで表示します。この情報ボックスは、Workspace プロジェクト内から注釈を作成する場合にのみ表示されます。 |
   | **[!UICONTROL タイトル]** ![必須](/help/assets/icons/Required.svg) | 注釈に名前を付けます（例：`Needs further investigation`）。 |
   | **[!UICONTROL 説明]** | 注釈に説明を付けます（例：`We never expected such a fluctuation in numbers.`）。 |
   | **[!UICONTROL タグ]** | 1 つ以上のタグを作成または適用して、注釈を整理します。入力を開始して、選択可能な既存のタグを検索します。または、**[!UICONTROL Enter]** キーを押して新しいタグを追加します。「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、タグを削除します。 |
   | **[!UICONTROL 適用日]** ![必須](/help/assets/icons/Required.svg) | 注釈を表示するのに必要な日付または日付範囲を選択します。ショートカットを使用して注釈を作成すると、注釈はデフォルトでその日の日付範囲に設定されます。ビジュアライゼーション内の選択を使用して注釈を作成する場合、注釈はデフォルトでビジュアライゼーションが属するパネルの日付範囲に基づいて日付範囲に設定されます。 |
   | **[!UICONTROL カラー]** | 注釈にカラーを適用します。注釈は、選択されたカラーでプロジェクトに表示されます。カラーを使用すると、祝日、外部イベント、トラッキングの問題などの注釈を分類できます。 |
   | **[!UICONTROL 範囲]** | 注釈をトリガーするコンポーネントパネルから指標をドラッグ＆ドロップします。例えば、人物、セッション、イベントなどです。 次に、セグメントとして機能するディメンションまたはセグメントをコンポーネントパネルからドラッグ＆ドロップして、注釈を表示するかどうかを決定します。範囲を指定しない場合、注釈はすべてのデータに適用されます。<br/>次の 2 つのオプションがあります。<ul><li>**[!UICONTROL これらの指標のいずれかが存在する場合]**：注釈を表示するトリガーとなる指標を最大 10 個までドラッグ＆ドロップします。<br/> 例えば、売上高指標が特定の日付範囲のデータ収集を停止したとします。 売上高指標をこのボックスにドラッグします。</li><li>**[!UICONTROL これらすべてのセグメントを使用]**：注釈が表示されるかどうかをセグメント化するディメンションまたはセグメントを最大 10 個までドラッグ＆ドロップします。</li></ul><p><p>**メモ：**&#x200B;コンポーネントに適用された注釈で、計算指標またはセグメント定義の一部として使用されるものは、注釈を自動的には継承しません。注釈を表示するには、目的の計算指標を範囲セクションに追加する必要もあります。ただし、同じ情報で注釈を付けるセグメントに対しては、新しい注釈を作成する必要があります。例えば、特定の日に[!UICONTROL 注文]に注釈を適用します。次に、同じ日付範囲の計算指標で[!UICONTROL 注文]を使用します。新しい計算指標では、注文の注釈は自動的には表示されません。また、表示する注釈の範囲セクションに計算指標を追加します。 |
   | **[!UICONTROL すべてのデータビューに適用]** | デフォルトでは、注釈は元のデータビューに適用されます。このチェックボックスをオンにすると、会社内のすべてのデータビューに注釈を適用できます。 |

   {style="table-layout:auto"}

1. 選択
   * 「**[!UICONTROL 保存]**」を選択して、注釈を保存します。
   * 「**[!UICONTROL 名前を付けて保存]**」を選択して、注釈のコピーを保存します。
   * 「**[!UICONTROL 削除]**」を選択して、注釈を削除します。
   * 「**[!UICONTROL キャンセル]**」を選択して、注釈に対して行った変更をキャンセルするか、新しい注釈の作成をキャンセルします。
