---
description: Analysis Workspace のデータ要素を使用すると、Analysis Workspace の様々なコンポーネント（使用目的、承認済み、重複など）をカタログ化して追跡できます。
title: コンポーネント情報の表示
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 61%

---

# コンポーネント情報の表示

データ要素を使用すると、コンポーネントの説明、類似のコンポーネント、コンポーネントが頻繁に使用される他のコンポーネントなど、コンポーネントに関する情報を表示できます。

データ要素でコンポーネントに関する情報を表示するには：

1. 表示するコンポーネントを含む Analysis Workspace プロジェクトに移動します。

1. Analysis Workspaceの左側のパネルにある「[!UICONTROL **データ要素**]」アイコンを選択します （データ要素にアクセスする別の方法については、[データ要素の概要](/help/components/data-dictionary/data-dictionary-overview.md)の「データ要素へのアクセス」を参照してください）。

   データ要素ウィンドウが表示されます。

   ![ ディメンション、指標、セグメントおよび日付範囲のクイックセグメントを表示するデータ要素ウィンドウ ](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. 表示するコンポーネントを含むデータビューがドロップダウンメニューで選択されていることを確認します。 デフォルトでは、既に存在するデータビューが表示されます。

1. （オプション）検索フィールドに、表示するコンポーネントの名前の入力します。

   コンポーネントのタイプは、カラーとアイコンの両方で識別できます。**ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。Adobe アイコン ![Adobe アイコン ](assets/default-calc-metric-icon.png) は計算指標テンプレートまたはセグメントテンプレートのいずれか、電卓アイコン ![ 電卓アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は組織の Analytics 管理者によって作成された計算指標を示します。

1. （オプション） **フィルター** アイコン ![ データ要素のフィルターアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択し、次のセグメントオプションのいずれかを選択して、コンポーネントのリストをセグメント化します。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | お気に入りのリストにあるコンポーネントのみを表示します。お気に入りのリストにコンポーネントを追加する方法については、[コンポーネントの概要](/help/components/overview.md)を参照してください。 |
   | [!UICONTROL **ディメンション**] | ディメンションであるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に [!UICONTROL **クイックセグメント**] タブでも使用できます）。 |
   | [!UICONTROL **指標**] | 指標であるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に [!UICONTROL **クイックセグメント**] タブでも使用できます）。 |
   | [!UICONTROL **セグメント**] | セグメントであるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に [!UICONTROL **クイックセグメント**] タブでも使用できます）。 |
   | [!UICONTROL **日付範囲**] | 日付範囲であるコンポーネントのみを表示します（このオプションは、最初にデータ要素にアクセスした際に [!UICONTROL **クイックセグメント**] タブでも使用できます）。 |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントの表示。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者が承認済みとしてまだマークしていないコンポーネントのみを表示します。レビューと承認が必要なコンポーネントを管理者が識別する際に役立ちます。このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **説明がありません**] | 「説明」フィールドにまだ説明がないコンポーネントのみを表示します。このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **重複の表示**] | 選択したデータビュー内の別のコンポーネントと同じ名前または同じ説明を持つコンポーネントのみを表示します。 これには、ユーザー作成のコンポーネントとAdobeが提供するコンポーネントが含まれます。 重複として表示するには、名前または説明が完全に一致している必要があります。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **最近のデータがありません**] | 過去 90 日間にデータを収集していないコンポーネントのみを表示します。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **作成者：Adobe**]<!-- I don't see this option--> | アドビが作成したコンポーネントのみを表示します。組織内の管理者または別のユーザーが作成したコンポーネントは表示しません。 |

   {style="table-layout:auto"}

1. （オプション） **並べ替え** アイコン ![ コンポーネントを並べ替えアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のセグメントオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

   {{components-sort-options}}

1. コンポーネントのリストから、表示するコンポーネントを選択します。

   コンポーネントに関する次の情報が表示されます。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | <p>コンポーネントが管理者にレビューおよび承認されたことを示します。</p><p>管理者には、「未承認 [!UICONTROL **のオプションが表示され**] す。 このオプションを選択すると、ユーザーに対してコンポーネントが「未承認」としてマークされます。</p> |
   | [!UICONTROL **未承認**] | <p>コンポーネントがまだ管理者にレビューおよび承認されていないことを示します。</p><p>管理者には、「[!UICONTROL **承認**]」オプションが表示されます。このオプションを選択すると、ユーザーに対してコンポーネントが「承認済み」としてマークされます。</p> |
   | [!UICONTROL **コンテキストラベル**] | このフィールドは、コンポーネントのコンテキストラベルがデータビューで更新された場合にのみ表示されます。 <p>詳しくは、[ コンポーネント設定 ](/help/data-views/component-settings/overview.md) を参照してください。 </p> |
   | [!UICONTROL **説明**] | コンポーネントの意図された機能について説明します（この情報は、[コンポーネントの説明の追加](/help/components/add-component-descriptions.md)で説明しているように、Analytics 管理者が追加します）。 |
   | [!UICONTROL **次でよく使用される**] | <p>表示しているコンポーネントと最も一緒に使用されるコンポーネントを表示します。</p><p>指標、計算指標、ディメンション、セグメントおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>このリストは、過去 90 日間のデータに基づいています。表示するアクセス権を持つコンポーネントのみを表示します。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。ユーザーに表示されるコンポーネントをキュレートする前に、最初に **すべて表示** セグメントを適用して、共有されていないコンポーネントのうち、別の管理者によって追加された可能性のあるものを表示します。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p> |
   | [!UICONTROL **類似**] | <p>表示しているコンポーネントと同様の名前を持つコンポーネントを表示します。</p><p>指標、計算指標、ディメンション、セグメントおよび日付範囲の 5 つの主要なコンポーネントタイプで最大 5 つのコンポーネントを表示します。</p><p>表示するためのアクセス権を持つコンポーネントのみを表示します。</p><p>データビューで重複するコンポーネントはすべてここに表示されます。 [データ要素の正常性の監視](/help/components/data-dictionary/monitor-data-dictionary-health.md)で説明しているように、Analytics 管理者はすべての重複するコンポーネントを特定して削除する必要があります。</p><p>管理者は、「[!UICONTROL **常に含める**]」および「[!UICONTROL **常に除外**]」ドロップダウンフィールドで目的のコンポーネントを選択することにより、このセクションでユーザーに表示されるコンポーネントをキュレートできます。ユーザーに表示されるコンポーネントをキュレートする前に、最初に **すべて表示** セグメントを適用して、共有されていないコンポーネントのうち、別の管理者によって追加された可能性のあるものを表示します。<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**メモ：**&#x200B;現在、「**類似**」セクションには、ユーザー作成のコンポーネントのみが含まれており、アドビ提供のコンポーネントは含まれていません。アドビ提供のコンポーネントは、今後のリリースで追加される予定です。</p> |
   | [!UICONTROL **製品の互換性**] | Customer Journey Analytics内でこの計算指標を使用できる場所を示します。 <p>使用可能な値は次のとおりです。</p><ul><li>[!UICONTROL **Customer Journey Analyticsのすべての場所**]：計算指標は、Analysis WorkspaceやReport Builderなど、Customer Journey Analytics全体で使用できます。</li><li>[!UICONTROL **Customer Journey Analytics のすべての場所 (実験を除く)**]：計算指標は、実験パネルを除く Adobe Customer Journey Analytics 全体で使用できます。</li> <p>計算指標が実験で使用できるかどうかを決定する条件について詳しくは、[ 実験パネル ](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) の [ 実験パネルで計算指標を使用 ](/help/analysis-workspace/c-panels/experimentation.md) を参照してください。</p></ul> |
   | [!UICONTROL **タグ**] | コンポーネントに適用されているすべてのタグを表示します。管理者アクセス権を持つユーザーは、コンポーネントの編集時にタグを追加できます。 |
   | [!UICONTROL **コンポーネントの種類**] | ディメンション、指標、セグメント、または日付範囲のいずれかであるコンポーネントのタイプをリストします。 |
   | [!UICONTROL **作成者**] | コンポーネントを作成したユーザーの名前を表示します。 |
   | [!UICONTROL **プレビュー**] | Analysis Workspace でのコンポーネントの外観のプレビューを表示します。 |
   | [!UICONTROL **最終変更日**] | コンポーネントの最終変更日を表示します。 このセクションは、セグメント、指標、計算指標および日付範囲を表示する際に表示されます。 |

   {style="table-layout:auto"}

1. （オプション）データ要素から Analysis Workspace にコンポーネントをドラッグします。
