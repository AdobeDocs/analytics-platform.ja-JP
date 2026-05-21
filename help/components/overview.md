---
title: コンポーネントの概要
description: Adobe Analytics オファーのコンポーネントの詳細と、Analysis Workspace でのコンポーネントの使用方法について説明します。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
TQID: https://experienceleague.adobe.com/91yF4rq5CqbAtgfY9X31FmgiCynSJFHaNF1KKsKDycg
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
  - id: e4a0bad2-b448-47f1-9fa6-222ebdb3b5b0
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 972
ht-degree: 100%

---

# コンポーネントの概要

コンポーネントは、ビジュアライゼーション（フリーフォームテーブルなど）で使用したり、レポート機能を補完したりできる Customer Journey Analytics の機能です。

Customer Journey Analytics のメインインターフェイスからコンポーネントを管理するには、次の手順に従います。

1. 上部のバーから「**[!UICONTROL コンポーネント]**」を選択します。
1. 「**[!UICONTROL コンポーネント]**」を選択して、管理できるコンポーネントの概要を表示するか、メニューから管理するコンポーネントを直接選択します。

次のコンポーネントを管理できます。

* [セグメント](segments/seg-overview.md)：強力かつ焦点を絞ったオーディエンスセグメントを作成、管理、共有し、レポートに適用します。 セグメントを使用すると、特性やインタラクションに基づいてユーザーのサブセットを特定できます。
* [計算指標](calc-metrics/calc-metr-overview.md)：レポートで使用する新しいコンポーネントとして指標と数式を使用します。
* [日付範囲](date-ranges/create.md)：Analysis Workspace が提供する日付範囲をカスタマイズおよび調整します。
* [注釈](/help/components/annotations/overview.md)：コンテキストデータのニュアンスとインサイトを組織に伝えます。
* [インテリジェントアラート](/help/components/c-intelligent-alerts/intelligent-alerts.md)：変更された割合や特定のデータポイントに基づいて通知を受信できます。
* [スケジュールされたプロジェクト](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：スケジュールされたプロジェクトを管理します。
* [環境設定](/help/analysis-workspace/user-preferences.md)：Analysis Workspace の環境設定を管理します。
* [オーディエンス](/help/components/audiences/audiences-overview.md)：Customer Journey Analytics から Experience Platform の[リアルタイム顧客データプラットフォーム](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/home)にオーディエンスを作成して公開し、ターゲティングやパーソナライゼーションを実現します。
* [書き出し](/help/components/exports/manage-export-locations.md)：書き出しアカウントと書き出し場所を管理します。


## Analysis Workspace のコンポーネント

Analysis Workspace のコンポーネントは、Workspace プロジェクトのパネルやビジュアライゼーションにドラッグ＆ドロップできる指標、ディメンション、セグメント、日付範囲で構成されています。 計算指標やカスタム日付範囲など、作成するカスタムコンポーネントがこれらのパネルに追加されます。

コンポーネントパネルにアクセスするには、ボタンパネル内の![キュレート](/help/assets/icons/Curate.svg)／**[!UICONTROL コンポーネント]**&#x200B;を選択します。

![左パネルでコンポーネントアイコンをハイライト表示する Workspace パネル](assets/components.png)

プロジェクトでのコンポーネントの使用方法について詳しくは、[プロジェクトの作成](/help/analysis-workspace/home.md)を参照してください。


## コンポーネントの管理 {#actions}

Analysis Workspace の&#x200B;**[!UICONTROL コンポーネント]**&#x200B;メニューを使用して、新しいコンポーネントをすばやく作成できます。 詳しくは、[Analysis Workspace メニュー](/help/analysis-workspace/home.md#menu)を参照してください。

コンポーネントを（個別に、または複数を選択して）管理できます。

1. 1 つまたは複数のコンポーネントを選択します。

1. コンテキストメニュー、または ![MoreVertical](/help/assets/icons/MoreVertical.svg) コンポーネントアクションボタン（コンポーネントの上部）から、次のいずれかのアクションを選択します。


   >[!TIP]
   >
   >複数のコンポーネントを選択するには、**[!UICONTROL Shift]** キーを押すか、**[!UICONTROL Command]** キー（macOS の場合）または **[!UICONTROL Ctrl]** キー（Windows の場合）を押します。


   ![タグ、お気に入り、承認、共有、削除を表示するコンポーネントアクションリスト。](assets/component-menu.gif){width=100%}

   | コンポーネントのアクション | 説明 |
   |--- |--- |
   | ![ラベル](/help/assets/icons/Label.svg)、[!UICONTROL **タグ**] | コンポーネントにタグを適用して整理したり管理したりします。 次に、「![フィルター](/help/assets/icons/Filter.svg)」を選択するか、`#` を入力して、左パネルのタグで検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
   | ![星](/help/assets/icons/Star.svg)、[!UICONTROL **お気に入り**] | コンポーネントをお気に入りのリストに追加します。 タグと同様に、左パネルのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | ![StarOutline](/help/assets/icons/StarOutline.svg)、**[!UICONTROL お気に入りを解除]** | コンポーネントをお気に入りのリストから削除します。 |
   | ![チェックマーク](/help/assets/icons/Checkmark.svg)、[!UICONTROL **承認**] | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左パネルで「承認済み」で検索してフィルタリングできます。 ![チェックマーク](/help/assets/icons/Checkmark.svg)は、承認済みのコンポーネントを識別します。 |
   | ![共有](/help/assets/icons/ShareAlt.svg)、[!UICONTROL **共有**] | 組織内のユーザーとコンポーネントを共有します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |
   | ![削除](/help/assets/icons/Delete.svg)、[!UICONTROL **削除**] | 不要になったコンポーネントを削除します。 このオプションは、セグメントや計算指標などのカスタムコンポーネントでのみ使用できます。 |

カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理することもできます。 例えば、[セグメントの管理](/help/components/segments/seg-manage.md)を参照してください。

## コンポーネントリストの管理

Analysis Workspace の左パネルにあるコンポーネントリストを検索、フィルタリング、並べ替えると、特定のコンポーネントを見つけることができます。

### 検索

1. 左パネルで「**コンポーネント**」（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

2. 検索フィールドに、プロジェクトで使用するコンポーネントの名前を入力します。

   コンポーネントのタイプは、カラーとアイコンで識別されます。 **ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**セグメント** ![セグメントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。<br/>アドビアイコン（![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg)）は、計算指標テンプレートまたはセグメントテンプレートのいずれかを示します。 電卓アイコン（![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg)）は、組織の管理者が作成した計算指標を示します。

3. ドロップダウンメニューからコンポーネントを選択します。

### フィルター

1. 左パネルで&#x200B;**コンポーネント**&#x200B;アイコン（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

2. 「**フィルター**」、![データ辞書フィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg)を選択するか、検索フィールドに `#` を入力します。

3. 次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルタリングします。

   | アイコン | フィルターオプション | 説明 |
   |---------|---|----------|
   | ![チェックマーク](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 承認済み]** | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | ![星](/help/assets/icons/Star.svg) | **[!UICONTROL お気に入り]** | お気に入りのリストにあるコンポーネントのみを表示します。 <br/>お気に入りのリストにコンポーネントを追加する方法について詳しくは、[コンポーネントの管理](#manage-components)を参照してください。 |
   | ![ディメンション](/help/assets/icons/Dimensions.svg) | **[!UICONTROL ディメンション]** | ディメンションであるコンポーネントのみを表示します |
   | ![イベント](/help/assets/icons/Event.svg) | **[!UICONTROL 指標]** | 指標であるコンポーネントのみを表示します |
   | ![セグメント化](/help/assets/icons/Segmentation.svg) | **[!UICONTROL セグメント]** | セグメントであるコンポーネントのみを表示します。 |
   | ![カレンダー](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日付範囲]** | 日付範囲であるコンポーネントのみを表示します。 |
   | ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL *タグ名&#x200B;*]** | 特定のタグが選択されているコンポーネントのみを表示します。 アドビテンプレートには専用のタグが使用できます。これは、アドビの[デフォルトの計算指標](/help/components/calc-metrics/default-calcmetrics.md)です。 |

   フィルターで「![CrossSize75](/help/assets/icons/CrossSize75.svg)」を選択して、フィルターを削除します。

4. オプションで、[コンポーネントリストの並べ替え](#sort-the-component-list)の説明に従って、コンポーネントリストを並べ替えることができます。

### 並べ替え

<!-- {{release-limited-testing-section}}-->

1. （オプション）[コンポーネントリストのフィルタリング](#filter-the-component-list)で説明しているように、コンポーネントリストにフィルターを適用します。

2. 左パネルで「**コンポーネント**」（![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg)）を選択します。

3. 「**並べ替え**」（![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg)）を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

次の並び替えオプションを使用できます。

{{components-sort-options}}

## アクセス権限

Analysis Workspace では、管理者はレポートでユーザーに公開するコンポーネントを[キュレート](/help/analysis-workspace/curate-share/curate.md)できます。
