---
title: Customer Journey Analytics におけるコンポーネントとは
description: Customer Journey Analytics オファーのコンポーネントの詳細と、レポートでの使用方法について説明します。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: e07197325e992cd85b852899c2f7cef60637f532
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 33%

---

# コンポーネントの概要

コンポーネントは、ビジュアライゼーション （フリーフォームテーブルなど）で使用できる、またはレポート機能を補完するCustomer Journey Analyticsの機能です。

メインCustomer Journey Analyticsインターフェイスからコンポーネントを管理するには：

1. 上部バーの **[!UICONTROL コンポーネント]** を選択します。
1. **[!UICONTROL コンポーネント]** を選択して、管理できるコンポーネントの概要を表示するか、メニューから管理するコンポーネントを直接選択します。

次のコンポーネントを管理できます。

* [フィルター](filters/filters-overview.md)：強力かつ焦点を絞ったオーディエンスフィルターを作成、管理、共有し、レポートに適用します。フィルターを使用すると、特性やインタラクションに基づいてユーザーのサブセットを特定できます。
* [計算指標](calc-metrics/calc-metr-overview.md)：レポートで使用する新しいコンポーネントとして指標と数式を使用します。
* [日付範囲](date-ranges/create.md)：Analysis Workspace が提供する日付範囲をカスタマイズおよび調整します。
* [注釈](/help/components/annotations/overview.md)：コンテキストデータのニュアンスとインサイトを組織に伝えます。
* [ インテリジェントアラート ](/help/components/c-intelligent-alerts/intelligent-alerts.md)：変更された割合または特定のデータポイントに基づいて通知を受け取ることができます。
* [ スケジュールされたプロジェクト ](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager)：スケジュールされたプロジェクトを管理します。
* [ 環境設定 ](/help/analysis-workspace/user-preferences.md):Analysis Workspaceの環境設定を管理します。
* [ オーディエンス ](/help/components/audiences/audiences-overview.md)：ターゲティングやパーソナライゼーションにExperience Platformして、Customer Journey Analyticsから [Real-time Customer Data Platform](https://experienceleague.adobe.com/en/docs/experience-platform/profile/home) にオーディエンスを作成して公開します。
* [ 書き出し ](/help/components/exports/manage-export-locations.md)：書き出しアカウントと場所を管理します。


## Analysis Workspace のコンポーネント

Analysis Workspaceのコンポーネントは、Workspace プロジェクトのパネルおよびビジュアライゼーションにドラッグ&amp;ドロップできる指標、ディメンション、フィルターおよび日付範囲で構成されています。 作成したカスタムコンポーネントは、計算指標やカスタム日付範囲など、これらのパネルに追加されます。

コンポーネントパネルにアクセスするには、ボタンパネル内の ![Curate](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** を選択します。

![左パネルでコンポーネントアイコンをハイライト表示する Workspace パネル](assets/components.png)

プロジェクトでのコンポーネントの使用方法については、[ プロジェクトの作成 ](/help/analysis-workspace/home.md) を参照してください。


+++ コンポーネントの可能性を示すビデオを視聴してください。

>[!VIDEO](https://video.tv.adobe.com/v/23979)

+++

## コンポーネントの管理 {#actions}

Analysis Workspaceの **[!UICONTROL コンポーネント]** メニューを使用して、新しいコンポーネントをすばやく作成できます。 詳しくは、[Analysis Workspace メニュー ](/help/analysis-workspace/home.md#menu) を参照してください。

コンポーネントを（個別に、または複数を選択して）管理できます。

1. 1 つ以上のコンポーネントを選択します。

1. コンテキストメニュー、または ![ その他の垂直方向 ](/help/assets/icons/MoreVertical.svg) コンポーネントアクションボタン（コンポーネントの上部）から、次のいずれかのアクションを選択します。


   >[!TIP]
   >
   >複数のコンポーネントを選択するには、**[!UICONTROL Shift]** キーを押すか、**[!UICONTROL Command]** キー（macOSの場合）または **[!UICONTROL Ctrl]** キー（Windows の場合）を押します。


   ![ タグ、お気に入り、承認、共有、削除を表示するコンポーネントアクションリスト。](assets/component-menu.gif){width=100%}

   | コンポーネントのアクション | 説明 |
   |--- |--- |
   | ![Label](/help/assets/icons/Label.svg) [!UICONTROL **Tag**] | コンポーネントにタグを適用して整理したり管理したりします。その後、![ フィルター ](/help/assets/icons/Filter.svg) フィルターを選択するか `#` を入力して、左側のパネルのタグで検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
   | ![ スター ](/help/assets/icons/Star.svg) [!UICONTROL **お気に入り**] | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のパネルのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | ![StarOutline](/help/assets/icons/StarOutline.svg)**[!UICONTROL お気に入りから外す]** | コンポーネントをお気に入りのリストから削除します。 |
   | ![ チェックマーク ](/help/assets/icons/Checkmark.svg)[!UICONTROL **承認**] | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左側のパネルで「承認済み」を検索してフィルタリングできます。 ![ チェックマーク ](/help/assets/icons/Checkmark.svg) は、承認済みのコンポーネントを識別します。 |
   | ![Share](/help/assets/icons/ShareLight.svg) [!UICONTROL **Share**] | 組織内のユーザーとコンポーネントを共有します。このオプションは、フィルターや計算指標などのカスタムコンポーネントでのみ使用できます。 |
   | ![Delete](/help/assets/icons/Delete.svg)[!UICONTROL **Delete**] | 不要になったコンポーネントを削除します。このオプションは、フィルターや計算指標などのカスタムコンポーネントでのみ使用できます。 |

また、カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理できます。例えば、[ フィルターの管理 ](/help/components/filters/manage-filters.md) を参照してください。

## コンポーネントリストの管理

Analysis Workspaceの左側のパネルにあるコンポーネントリストを検索、フィルタリング、並べ替えて、特定のコンポーネントを見つけることができます。

### 検索

1. 左側のパネルで **コンポーネント** ![ コンポーネントアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

2. 検索フィールドに、プロジェクトで使用するコンポーネントの名前を入力します。

   コンポーネントのタイプは、カラーとアイコンで識別されます。 **Dimension** ![Dimensionアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) オレンジ色、**フィルター** ![ フィルターアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) 青色、**日付範囲** ![ 日付範囲アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 紫色、**指標** ![ 指標アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) 緑色です。<br/>Adobeアイコン ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) は、計算指標テンプレートまたはフィルターテンプレートのいずれかを示します。 電卓アイコン ![ 電卓アイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は、組織の管理者が作成した計算指標を示します。

3. ドロップダウンリストからコンポーネントを選択します。

### フィルター

1. 左側のパネルで「**コンポーネント**」アイコン ![ コンポーネントアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

2. **フィルター**![ データ要素のフィルターアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択するか、検索フィールドに `#` を入力します。

3. 次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルタリングします。

   | アイコン | フィルターオプション | 説明 |
   |---------|---|----------|
   | ![ チェックマーク ](/help/assets/icons/Checkmark.svg) | **[!UICONTROL 承認済み]** | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | ![ 星 ](/help/assets/icons/Star.svg) | **[!UICONTROL お気に入り]** | お気に入りのリストにあるコンポーネントのみを表示します。<br/> お気に入りのリストにコンポーネントを追加する方法については、[ コンポーネントの管理 ](#manage-components) を参照してください。 |
   | ![ディメンション](/help/assets/icons/Dimensions.svg) | **[!UICONTROL ディメンション]** | ディメンションであるコンポーネントのみを表示します。 |
   | ![イベント](/help/assets/icons/Event.svg) | **[!UICONTROL 指標]** | 指標であるコンポーネントのみを表示します。 |
   | ![セグメント化](/help/assets/icons/Segmentation.svg) | **[!UICONTROL フィルター]** | フィルターであるコンポーネントのみを表示します。 |
   | ![カレンダー](/help/assets/icons/Calendar.svg) | **[!UICONTROL 日付範囲]** | 日付範囲であるコンポーネントのみを表示します |
   | ![ラベル](/help/assets/icons/Label.svg) | **[!UICONTROL *タグ名&#x200B;*]** | 特定のタグが選択されているコンポーネントのみを表示します。 Adobeテンプレートには専用のタグが使用できます。これは、Adobeの [ デフォルトの計算指標 ](/help/components/calc-metrics/default-calcmetrics.md) です。 |

   フィルターで ![CrossSize75](/help/assets/icons/CrossSize75.svg) を選択して、フィルターを削除します。

4. オプションで、「コンポーネントリストの並べ替え [ の説明に従って、コンポーネントリストを並べ替えること ](#sort-the-component-list) できます。

### 並べ替え

<!-- {{release-limited-testing-section}}-->

1. （オプション）[コンポーネントリストのフィルタリング](#filter-the-component-list)で説明しているように、コンポーネントリストにフィルターを適用します。

2. 左側のパネルで **コンポーネント** ![ コンポーネントアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

3. **並べ替え**![ コンポーネントを並べ替えアイコン ](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

次の並べ替えオプションを使用できます。

{{components-sort-options}}

## アクセス権限

Analysis Workspaceでは、管理者は、レポートでユーザーに公開されるコンポーネントを [ キュレーション ](/help/analysis-workspace/curate-share/curate.md) できます。
