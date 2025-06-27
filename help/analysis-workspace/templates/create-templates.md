---
description: Analysis Workspaceでテンプレートを作成および管理する方法について説明します。
title: テンプレートの作成と管理
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '1851'
ht-degree: 99%

---

# テンプレートの作成と管理

管理者はテンプレートを作成し、ログイン会社内の他のユーザーが使用できるように保存できます。

ログイン会社の人物が、これらの会社テンプレートを使用するには、[テンプレートの使用](/help/analysis-workspace/templates/use-templates.md)を参照してください。

## テンプレートの作成 {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Journey Optimizer でのテンプレートの使用"
>abstract="Journey Optimizer でこのテンプレートを使用すると、Customer Journey Analytics でこのテンプレートで選択されているデータビューに関係なく、Adobe Journey Optimizer でデフォルトのデータビューとして設定されているデータビューが使用されます。"

<!-- markdownlint-enable MD034 -->

ログイン会社の人物が使用できる新しいテンプレートを作成するには：

1. Analysis Workspace で、プロジェクトを目的の状態に作成します。

1. [!UICONTROL **プロジェクト**]／**[!UICONTROL テンプレートとして保存]**&#x200B;を選択します。

   ![会社テンプレート](assets/company-template-save.png)

1. [!UICONTROL テンプレートとして保存]ダイアログボックスで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | テンプレートのわかりやすい名前を入力します。 |
   | **[!UICONTROL 説明]** | テンプレートの使用目的を説明する短い説明を入力します。 |
   | **[!UICONTROL このテンプレートを使用する理由]** | このテンプレートの使用方法について組織内の人物に通知する、短い説明を入力します。この説明は、テンプレートのプレビューページに表示されます。 |
   | **[!UICONTROL チャネル]** | このテンプレートに適用される、該当のチャネルを選択します。複数のチャネル（**[!UICONTROL web]**、**[!UICONTROL モバイル]**、**[!UICONTROL クロスチャネル]**、**[!UICONTROL コールセンター]**、**[!UICONTROL ストア内]**）を選択できます。<p>選択した項目によって、テンプレートが表示される場所と、組織テンプレートページからそのテンプレートにアクセスするユーザーに適用されるセグメントが決定します。</p> |
   | **[!UICONTROL ユースケース]** | このテンプレートに適用されるユースケースを選択します。**[!UICONTROL エンゲージメント]**、**[!UICONTROL コンバージョン]**、**[!UICONTROL オーディエンス]**、**[!UICONTROL 獲得]**、**[!UICONTROL Journey Optimizer]** など、複数のユースケースを選択できます。 <p>選択した項目によって、組織テンプレートページのテンプレートの位置が決まります。 ユーザーは、テンプレートに移動するか、ユースケース別にリストをフィルタリングできます。 </p><p>**メモ：**「**[!UICONTROL Journey Optimizer]**」オプションを選択すると、テンプレートを Adobe Journey Optimizer で使用できるようになります。Journey Optimizer では、**[!UICONTROL レポート]**&#x200B;ページにドロップダウンメニューがあるので、ユーザーはこのテンプレートまたはデフォルトのテンプレートを選択できます。詳しくは、Journey Optimizer ドキュメントの[更新されたレポートエクスペリエンスの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja)を参照してください。</p><p>「Journey Optimizer」オプションを選択する場合は、次の点を考慮してください。</p><ul><li>このオプションを使用できるのは、Customer Journey Analytics で使用しているデータビューに Journey Optimizer データが存在する場合のみです。</li><li>Journey Optimizer でこのテンプレートを使用すると、Customer Journey Analytics でこのテンプレートに選択されているデータビューに関係なく、Adobe Journey Optimizer でデフォルトのデータビューとして設定されているデータビューが使用されます。<br/>データビューを Journey Optimizer のデフォルトのデータビューとして設定する方法については、[データビューの作成または編集[の](/help/data-views/create-dataview.md#compatibility)互換性](/help/data-views/create-dataview.md)を参照してください。</li></ul> |
   | **[!UICONTROL Journey Optimizer アクティビティタイプ]** | このテンプレートに関連付ける Journey Optimizer アクティビティタイプ（**[!UICONTROL キャンペーン]**、**[!UICONTROL ジャーニー]**、**[!UICONTROL ランディングページ]**、**[!UICONTROL レポート]**&#x200B;または&#x200B;**[!UICONTROL サブスクリプション]**）を選択します。 <p>このテンプレートをすべてのアクティビティタイプに関連付ける場合は、このフィールドを空白のままにします。</p><p>このフィールドは、「**[!UICONTROL ユースケース]**」フィールドで **[!UICONTROL Journey Optimizer]** を選択した場合にのみ表示されます。</p> |
   | **[!UICONTROL Journey Optimizer アクティビティ]** | このテンプレートに関連付ける Journey Optimizer アクティビティを選択します。 <p>このテンプレートを選択したアクティビティタイプのすべてのアクティビティに関連付ける場合は、このフィールドを空白のままにします。</p><p>このフィールドは、「**[!UICONTROL ユースケース]**」フィールドで **[!UICONTROL Journey Optimizer]** を選択した場合にのみ表示されます。</p> |
   | **[!UICONTROL タグ]** | テンプレートに適用するタグを指定します。ここで追加したタグによって、ユーザーはテンプレートのリストをフィルタリングできます。 |

1. 「[!UICONTROL **テンプレートとして保存**]」を選択します。

ユーザーがテンプレートに基づいてプロジェクトを作成する方法については、[テンプレートの使用](/help/analysis-workspace/templates/use-templates.md)の[テンプレートに基づくプロジェクトの作成](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template)を参照してください 。

## テンプレートの編集または削除

管理者は、会社テンプレートを編集または削除できます。

1. Analysis Workspace で、「[!UICONTROL **Workspace**]」タブを選択し、左側のパネルの&#x200B;**[!UICONTROL テンプレート]**&#x200B;の下で、**[!UICONTROL _login_company_name _テンプレート]**を選択します。

1. 列表示 ![列表示アイコン](assets/column-view-icon.png) でテンプレートを表示している場合：

   1. 編集または削除するテンプレートに移動し、テンプレート名の横にある情報アイコンを選択します。

      ![会社テンプレート情報](assets/company-template-info.png)

   1. 「**[!UICONTROL プレビュー]**」を選択します。

   1. その他アイコンを選択し、「**[!UICONTROL 編集]**」または「**[!UICONTROL 削除]**」を選択します。

      ![テンプレートの編集または削除](assets/company-template-edit-delete.png)

1. カードビュー ![カードビューアイコン](assets/card-view-icon.png) でテンプレートを表示している場合：

   1. 編集または削除するテンプレートを見つけます。

      ![会社テンプレートカードビュー](assets/company-template-cards.png)

   1. テンプレートにポインタを合わせて、「**[!UICONTROL プレビュー]**」を選択します。

   1. その他アイコンを選択し、「**[!UICONTROL 編集]**」または「**[!UICONTROL 削除]**」を選択します。

      ![会社テンプレートカードの編集または削除](assets/company-template-card-edit-delete.png)

1. テンプレートを編集している場合は、目的の編集を行ってから、[!UICONTROL **プロジェクト**]／**[!UICONTROL テンプレートとして保存...]** を選択します。

   ![会社テンプレート](assets/company-template-save.png)

1. [!UICONTROL テンプレートとして保存]ダイアログボックスで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | テンプレートのわかりやすい名前を入力します。 |
   | **[!UICONTROL 説明]** | テンプレートの使用目的を説明する短い説明を入力します。 |
   | **[!UICONTROL このテンプレートを使用する理由]** | このテンプレートの使用方法について組織内の人物に通知する、短い説明を入力します。この説明は、テンプレートのプレビューページに表示されます。 |
   | **[!UICONTROL チャネル]** | このテンプレートに適用される、該当のチャネルを選択します。複数のチャネル（**[!UICONTROL Web]**、**[!UICONTROL モバイル]**、**[!UICONTROL クロスチャネル]**、**[!UICONTROL コールセンター]**、**[!UICONTROL ストア内]**）を選択できます。チャネルを選択していない場合、テンプレートはすべてのチャネルに含まれます。<p>選択した項目によって、テンプレートが表示される場所と、組織テンプレートページからそのテンプレートにアクセスするユーザーに適用されるフィルターが決定します。</p> |
   | **[!UICONTROL ユースケース]** | このテンプレートに適用されるユースケースを選択します。**[!UICONTROL エンゲージメント]**、**[!UICONTROL コンバージョン]**、**[!UICONTROL オーディエンス]**、**[!UICONTROL 獲得]**、**[!UICONTROL Journey Optimizer]** など、複数のユースケースを選択できます。 <p>選択した項目によって、組織テンプレートページのテンプレートの位置が決まります。 ユーザーは、テンプレートに移動するか、ユースケース別にリストをフィルタリングできます。 </p><p>**メモ：**「**[!UICONTROL Journey Optimizer]**」オプションを選択すると、テンプレートを Adobe Journey Optimizer で使用できるようになります。Journey Optimizer では、**[!UICONTROL レポート]**&#x200B;ページにドロップダウンメニューがあるので、ユーザーはこのテンプレートまたはデフォルトのテンプレートを選択できます。詳しくは、Journey Optimizer ドキュメントの[更新されたレポートエクスペリエンスの基本を学ぶ](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja)を参照してください。</p><p>「Journey Optimizer」オプションを選択する場合は、次の点を考慮してください。</p><ul><li>このオプションを使用できるのは、Customer Journey Analytics で使用しているデータビューに Journey Optimizer データが存在する場合のみです。</li><li>Journey Optimizer でこのテンプレートを使用すると、Customer Journey Analytics でこのテンプレートに選択されているデータビューに関係なく、Adobe Journey Optimizer でデフォルトのデータビューとして設定されているデータビューが使用されます。<br/>データビューを Journey Optimizer のデフォルトのデータビューとして設定する方法については、[データビューの作成または編集[の](/help/data-views/create-dataview.md#compatibility)互換性](/help/data-views/create-dataview.md)を参照してください。</li></ul> |
   | **[!UICONTROL Journey Optimizer アクティビティタイプ]** | このテンプレートに関連付ける Journey Optimizer アクティビティタイプ（**[!UICONTROL キャンペーン]**、**[!UICONTROL ジャーニー]**、**[!UICONTROL ランディングページ]**、**[!UICONTROL レポート]**&#x200B;または&#x200B;**[!UICONTROL サブスクリプション]**）を選択します。 <p>このテンプレートをすべてのアクティビティタイプに関連付ける場合は、このフィールドを空白のままにします。</p><p>このフィールドは、「**[!UICONTROL ユースケース]**」フィールドで **[!UICONTROL Journey Optimizer]** を選択した場合にのみ表示されます。</p> |
   | **[!UICONTROL Journey Optimizer アクティビティ]** | このテンプレートに関連付ける Journey Optimizer アクティビティを選択します。 <p>このテンプレートを選択したアクティビティタイプのすべてのアクティビティに関連付ける場合は、このフィールドを空白のままにします。</p><p>このフィールドは、「**[!UICONTROL ユースケース]**」フィールドで **[!UICONTROL Journey Optimizer]** を選択した場合にのみ表示されます。</p> |
   | **[!UICONTROL タグ]** | テンプレートに適用するタグを指定します。ここで追加したタグによって、ユーザーはテンプレートのリストをフィルタリングできます。 |

1. 「[!UICONTROL **テンプレートとして保存**]」を選択します。

## テンプレートの名前変更、タグ付け、承認

管理者は、会社テンプレートの名前変更、タグ付け、承認を行うことができます。

1. Adobe Analytics で、「[!UICONTROL **Workspace**]」タブを選択し、左側のパネルで「**[!UICONTROL プロジェクト]**」タブを選択します。

1. フィルターアイコンを選択して、プロジェクトのリストをフィルタリングします。

1. フィルターパネルで、「**[!UICONTROL その他のフィルター]**」を選択し、「**[!UICONTROL 会社テンプレート]**」を選択します。

   会社テンプレートのリストが表示されます。すべての標準プロジェクトは、ピン留めされていない限り、表示されません。

   会社テンプレートは、テンプレート名の前にある ![テンプレートアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) で識別できます。

   ![会社テンプレートフィルターを表示](assets/company-templates-filter.png)

1. テンプレートの横にある「**…**」省略記号アイコンをクリックして、使用可能なオプションを表示します。

   ![会社テンプレートアクション](assets/company-templates-actions.png)

1. 「**[!UICONTROL 名前変更]**」、「**[!UICONTROL タグ付け]**」または「**[!UICONTROL 承認]**」を選択します。

   テンプレートを削除することもできます。また、テンプレートを削除するには、[テンプレートの編集または削除](#edit-or-delete-templates)を参照してください。

1. （オプション）通常の表示に戻るには、フィルターパネルで「**[!UICONTROL 会社テンプレート]**」を選択解除します。

## 特定のテンプレートのデータビューへの欠落しているコンポーネントの追加

デフォルトでは、アドビが提供する一部のテンプレートは、データビューにないコンポーネントが含まれているので使用できません。

欠落している各コンポーネントに対して、一致するコンテキストラベルがデータビューで使用できます。データビューに既に存在するコンポーネントに一致するコンテキストラベルを追加するか、データビューに新しいコンポーネントを追加して、このコンポーネントにコンテキストラベルを追加する必要があります。

欠落しているコンポーネントをテンプレートに追加するには：

1. Analysis Workspaceで、「[!UICONTROL **Workspace**]」タブを選択し、左側のパネルの&#x200B;**[!UICONTROL テンプレート]**&#x200B;の下で、「**[!UICONTROL Adobe テンプレート]**」を選択します。

1. フィルターアイコンを選択して、テンプレートのリストをフィルタリングします。

1. データビューにないコンポーネントを必要とするテンプレートを表示するには、「**[!UICONTROL 使用準備が整っていません]**」を選択します。

   ![コンポーネントが欠落しているテンプレートを使用](assets/template-not-ready.png)

1. データビューでまだ使用する準備が整っていないテンプレートを見つけます。

1. 次のいずれかの操作を行います。

   * **列表示** ![列表示アイコン](assets/column-view-icon.png) でテンプレートを表示している場合：

      1. データビューでまだ使用する準備が整っていないテンプレートに移動し、テンプレート名の横にある情報アイコンを選択します。

         ![会社テンプレート情報](assets/company-template-info.png)

      1. 「**[!UICONTROL プレビュー]**」を選択します。

         ![テンプレートのプレビューページ](assets/template-preview.png)

   * **カードビュー** ![カードビューアイコン](assets/card-view-icon.png) でテンプレートを表示している場合：

      1. データビューでまだ使用する準備が整っていないテンプレートを見つけます。

         ![会社テンプレートカードビュー](assets/company-template-cards.png)

      1. テンプレートにポインタを合わせて、「**[!UICONTROL プレビュー]**」を選択します。

         ![テンプレートのプレビューページ](assets/template-preview.png)

1. 「**[!UICONTROL 欠落しているコンポーネント]**」セクションには、データビューに欠落しているコンポーネントのリストが表示されます。「**[!UICONTROL これらのコンポーネントをデータビューに追加]**」を選択します。

   データビューの設定ページが新しいタブに表示されます。

1. データビューの「**[!UICONTROL コンポーネント]**」タブを選択します。

   ![データビューの「コンポーネント」タブ](assets/template-dataview.png)

1. テンプレートに欠落しているものとして一覧表示されている各コンポーネントについて、「**[!UICONTROL コンポーネント]**」 タブで次のいずれかの操作を行います。

   * 「**[!UICONTROL 含まれるコンポーネント]**」セクションで、欠落しているコンポーネントに使用する、データビューに既に含まれているコンポーネントを選択します。

   * 欠落しているコンポーネントに使用する新しいコンポーネントをデータビューに追加し、このコンポーネントを選択します。

     データビューに新しいコンポーネントを追加するには、スキーマフィールドのリストを検索し、「**[!UICONTROL 含まれるコンポーネント]**」セクションにドラッグします。

1. コンポーネントを選択した状態で、右側の列にある&#x200B;**[!UICONTROL コンテキストラベル]**&#x200B;ドロップダウンメニューを見つけます。

   ![データビューの「コンポーネント」タブ](assets/template-dataview-context-label.png)

1. **[!UICONTROL コンテキストラベル]**&#x200B;ドロップダウンメニューで、欠落しているコンポーネントと同じ名前のコンテキストラベルを選択します。

1. 「**[!UICONTROL 保存して続行]**」を選択します。

1. 欠落している各コンポーネントに対して、一致するコンテキストラベルをデータビューのコンポーネントに追加するプロセスを繰り返します。


## 会社テンプレートへのアクセス

アドビが提供するテンプレートと同様に、組織内のユーザーは管理者が作成したテンプレートにアクセスできます。

会社テンプレートへのアクセス方法について詳しくは、[テンプレートの使用](/help/analysis-workspace/templates/use-templates.md)の[テンプレートへのアクセスと実行](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)を参照してください。

## 「テンプレート」タブの非表示

管理者は、組織内のすべてのユーザーの「テンプレート」タブを非表示にできます。

1. **[!UICONTROL Customer Journey Analytics]**／**[!UICONTROL コンポーネント]**／**[!UICONTROL 環境設定]**／**[!UICONTROL 会社]**&#x200B;に移動します。
1. 「**[!UICONTROL 「テンプレート」タブを非表示]**」オプションを選択します。
