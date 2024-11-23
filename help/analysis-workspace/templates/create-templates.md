---
description: Analysis Workspaceでのデフォルトテンプレートの使用方法の概要です。
title: テンプレートを使用
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 96844fae07734e979e9dd4689d5eded6a7a3b926
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 4%

---

# テンプレートの作成と管理

管理者は、テンプレートを作成し、ログイン会社の他のユーザーが使用できるように保存できます。

ログイン会社のユーザーは、「テンプレートの使用 [ で説明しているように、これらの会社テンプレートを使用でき ](/help/analysis-workspace/templates/use-templates.md) す。

## テンプレートの作成

<!-- is this only admins? -->

ログイン会社のユーザーが使用できる新しいテンプレートを作成するには：

1. Analysis Workspaceで、目的のステートにプロジェクトをビルドします。

1. [!UICONTROL **プロジェクト**]/**[!UICONTROL テンプレートとして保存]** を選択します。

   ![会社レポート](assets/company-template-save.png)

1. [!UICONTROL  テンプレートとして保存 ] ダイアログボックスで、次の情報を指定します。

   | フィールド | 説明 |
   |---------|----------|
   | **[!UICONTROL 名前]** | テンプレートのわかりやすい名前を指定します。 |
   | **[!UICONTROL 説明]** | テンプレートの使用目的を説明する短い説明を入力します。 |
   | **[!UICONTROL このテンプレートを使用する理由]** | このテンプレートの使用方法について組織内のユーザーに通知するための短い説明を入力します。 |
   | **[!UICONTROL チャネル]** | このテンプレートに適用される適用可能なチャネルを選択します。 複数のチャネル（**[!UICONTROL Web]**、**[!UICONTROL モバイル]**、**[!UICONTROL クロスチャネル]**、**[!UICONTROL コールセンター]** および **[!UICONTROL 店舗]**）を選択できます。<p>選択した項目によって、テンプレートの表示場所と、そのテンプレートにアクセスするユーザーに対して「組織テンプレート」ページから適用されるフィルターが決まります。</p> |
   | **[!UICONTROL ユースケース]** | このテンプレートに適用されるユースケースを選択します。 **[!UICONTROL エンゲージメント]**、**[!UICONTROL コンバージョン]**、**[!UICONTROL オーディエンス]**、**[!UICONTROL 獲得]** など、複数のユースケースを選択できます。 <p>選択した項目によって、テンプレートの表示場所と、そのテンプレートにアクセスするユーザーに対して「組織テンプレート」ページから適用されるフィルターが決まります。</p> |
   | **[!UICONTROL タグ]** | テンプレートに適用するタグを指定します。 ユーザーは、追加するタグでテンプレートのリストをフィルタリングできます。 |

1. [!UICONTROL **テンプレートとして保存**] を選択します。

ユーザーがテンプレートに基づいてプロジェクトを作成する方法については、[ テンプレートの使用 [ の「テンプレートに基づいてプロジェクトを作成する ](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) を参照してください ](/help/analysis-workspace/templates/use-templates.md)。

## 会社テンプレートの管理

管理者は、会社テンプレートを削除、名前変更、タグ付けおよび承認できます。

会社テンプレートを表示および管理するには：

1. Analysis Workspaceで、「[!UICONTROL **Workspace**]」タブを選択し、左パネルで **[!UICONTROL 「プロジェクト」タブ]** を選択します。

1. フィルターアイコンを選択して、プロジェクトのリストをフィルタリングします。

1. フィルターパネルでは、**その他のフィルター** を選択してから、**会社テンプレート** を選択します。

   会社テンプレートのリストが表示されます。 すべての標準プロジェクトは、ピン留めされていない限り、表示されません。

   会社テンプレートは、テンプレート名の前に付く ![ テンプレートアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) によって識別できます。

   <!-- Update screenshot -->

   ![ 会社テンプレートフィルターを表示 ](assets/company-reports-filter.png)

1. テンプレートリストで、1 つ以上の会社テンプレートを選択します。

1. テンプレートの横にある **...** 省略記号アイコンをクリックして、使用可能なオプションを表示します。

   <!-- Update screenshot -->

   ![ 会社テンプレートのアクション ](assets/company-reports-actions.png)

1. 「**[!UICONTROL 削除]**」、「**[!UICONTROL 名前を変更]**」、「**[!UICONTROL タグ]**」または「**[!UICONTROL 承認]**）を選択します。

1. （任意）通常の表示に戻すには、フィルターパネルで「**[!UICONTROL 会社テンプレート]**」の選択を解除します。

## 会社テンプレートへのアクセス

Adobeから提供されるテンプレートと同様に、組織内のユーザーが作成したテンプレートにアクセスできます。

会社テンプレートへのアクセス方法について詳しくは、[ テンプレートの使用 [ の「テンプレートへのアクセスと実行 ](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) を参照してください ](/help/analysis-workspace/templates/use-templates.md)。
