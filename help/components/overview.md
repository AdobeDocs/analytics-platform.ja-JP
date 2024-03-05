---
title: Customer Journey Analytics におけるコンポーネントとは
description: Customer Journey Analytics オファーのコンポーネントの詳細と、レポートでの使用方法について説明します。
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: ht
source-wordcount: '1068'
ht-degree: 100%

---

# コンポーネントの概要

コンポーネントは、レポートで使用したり、レポート機能を補完したりできる、Customer Journey Analytics の機能です。これらのコンポーネントは、次の手順で管理できます。

1. Adobe ID の資格情報を使用して [analytics.adobe.com](https://analytics.adobe.com) にログインします。
2. ヘッダーメニューで[!UICONTROL コンポーネント]／[!UICONTROL コンポーネント]に移動します。

次のコンポーネントを管理できます。

* [**注釈**](/help/components/annotations/overview.md)：コンテキストデータのニュアンスとインサイトを組織に伝えます。
* [**オーディエンス**](/help/components/audiences/audiences-overview.md)：Customer Journey Analytics で検出されたオーディエンスを作成して Adobe Experience Platform の[リアルタイム顧客プロファイル](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=ja)（RTCDP）に公開し、顧客のターゲティングやパーソナライゼーションを実現します。
* [**フィルター**](filters/filters-overview.md)：強力かつ焦点を絞ったオーディエンスフィルターを作成、管理、共有し、レポートに適用します。フィルターを使用すると、特性やインタラクションに基づいてユーザーのサブセットを特定できます。
* [**計算指標**](calc-metrics/calc-metr-overview.md)：レポートで使用する新しいコンポーネントとして指標と数式を使用します。
* [**データ辞書**](/help/components/data-dictionary/data-dictionary-overview.md)：ユーザーと管理者の両方にとって、Analytics 環境のコンポーネントを追跡したり理解を深めたりするのに役立ちます。
* [**日付範囲**](date-ranges/create.md)：Analysis Workspace が提供する日付範囲をカスタマイズおよび調整します。
* [**ディメンション**](/help/components/dimensions/view-dimensions.md)：ディメンションは、通常、文字列値を含んでいる変数です。一般的なディメンションには、ページや参照ドメインなどがあります。
* [**指標**](/help/components/apply-create-metrics.md)：Analysis Workspace でデータポイントを数量化できます。
* [**プロジェクト**](/help/analysis-workspace/home.md)：Analysis Workspace でプロジェクトを整理し維持管理します。

## Analysis Workspace のコンポーネント

Analysis Workspace のコンポーネントは、プロジェクトにドラッグ＆ドロップできる指標、ディメンション、フィルターおよび時間精度で構成されています。カスタム日付範囲などの、作成したカスタムコンポーネントがこれらのパネルに追加されます。

コンポーネントパネルにアクセスするには、左側のパネルで&#x200B;**[!UICONTROL コンポーネント]**&#x200B;アイコンをクリックします。左側のパネルのアイコンを使用するか、[ホットキー](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)を使用して、パネル（空白パネル、[フリーフォームパネル](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)、[クイックインサイトパネル](/help/analysis-workspace/c-panels/quickinsight.md)、[Attribution IQ](/help/analysis-workspace/c-panels/attribution.md) パネルのいずれか）、[ビジュアライゼーション](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)、コンポーネントを切り替えることができます。

![左パネルでコンポーネントアイコンをハイライト表示する Workspace パネル](assets/components.png)

プロジェクトでのコンポーネントの使用については、[ワークスペースプロジェクトの作成](/help/analysis-workspace/home.md)を参照してください。

## コンポーネントのアクション

コンポーネントは、様々な方法で（個別に、または複数選択して同時に）管理できます。コンポーネントを右クリックするか、コンポーネントリストの上部にある「**[!UICONTROL アクション]**」をクリックします。

>[!NOTE]
>
>これらのアクションは、時間コンポーネントには適用されません。

| コンポーネントのアクション | 説明 |
| --- | --- |
| タグ | コンポーネントにタグを適用して整理したり管理したりします。これらは、[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL フィルター]や[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL プロジェクト]などの各コンポーネントマネージャーに表示されます。 |
| お気に入り | コンポーネントをお気に入りのリストに追加します。これらは、[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL フィルター]や[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL プロジェクト]などの各コンポーネントマネージャーに表示されます。 |
| 承認 | コンポーネントを正規のものとして承認します。これらは、[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL フィルター]や[!UICONTROL 分析]／[!UICONTROL コンポーネント]／[!UICONTROL プロジェクト]などの各コンポーネントマネージャーに表示されます。 |
| 共有 | フィルターにのみ適用されます。 |
| 削除 | フィルターにのみ適用されます。 |

指標、フィルター、日付の作成に関するビデオを視聴してください。

>[!VIDEO](https://video.tv.adobe.com/v/23979)

## コンポーネントの管理 {#actions}

左側のパネルでコンポーネントを直接管理できます。

1. コンポーネントを右クリックします。

   または

   コンポーネントを選択し、コンポーネントリストの上部にある「**アクション**」（3 ドット）アイコンを選択します。

   >[!TIP]
   >
   >   複数のコンポーネントを選択するには、Shift キーを押すか、Command キー（Mac の場合）または Ctrl キー（Windows の場合）を押します。


   ![タグ、お気に入り、承認、共有、削除を表示するコンポーネントアクションリスト。](assets/component-actions.png)

   | コンポーネントのアクション | 説明 |
   |--- |--- |
   | [!UICONTROL **タグ**] | コンポーネントにタグを適用して整理したり管理したりします。次に、フィルターをクリックするか「#」を入力して、左側のレールのタグで検索できます。 タグは、コンポーネントマネージャーのフィルターとしても機能します。 |
   | [!UICONTROL **お気に入り**] | コンポーネントをお気に入りのリストに追加します。タグと同様に、左側のレールのお気に入りで検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | [!UICONTROL **承認**] | コンポーネントを「承認済み」とマークして、コンポーネントが組織で承認されていることをユーザーに知らせます。 タグと同様に、左側のレールで「承認済み」を検索し、コンポーネントマネージャーでフィルタリングできます。 |
   | [!UICONTROL **共有**] | 組織内のユーザーとコンポーネントを共有します。このオプションは、フィルターや計算指標などのカスタムコンポーネントでのみ使用できます。 |
   | [!UICONTROL **削除**] | 不要になったコンポーネントを削除します。このオプションは、フィルターや計算指標などのカスタムコンポーネントでのみ使用できます。 |

また、カスタムコンポーネントは、それぞれのコンポーネントマネージャーを通じて管理できます。[フィルターの管理](/help/components/filters/manage-filters.md)などです。

## コンポーネントリストの検索、フィルタリング、並べ替え

Analysis Workspace の左側のパネルにあるコンポーネントリストを検索、フィルタリング、並べ替えて、特定のコンポーネントを素早く見つけることができます。

### コンポーネントリストの検索

1. 左側のパネルで「**コンポーネント**」アイコン ![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

2. 検索フィールドに、プロジェクトで使用するコンポーネントの名前を入力します。

   コンポーネントのタイプは、カラーとアイコンの両方で識別できます。**ディメンション** ![ディメンションアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) はオレンジ色、**フィルター** ![フィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) は青色、**日付範囲** ![日付範囲アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) は紫色、**指標** ![指標アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) は緑色です。アドビアイコン ![アドビアイコン](assets/default-calc-metric-icon.png) は計算指標テンプレートまたはフィルターテンプレートのいずれか、電卓アイコン ![電卓アイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) は組織の Analytics 管理者によって作成された計算指標を示します。

3. ドロップダウンリストに表示される場合に、コンポーネントを選択します。

### コンポーネントリストのフィルタリング

1. 左側のパネルにある「**コンポーネント**」アイコン ![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

2. **フィルター**&#x200B;アイコン ![データ辞書フィルターアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) を選択します。

   または

   検索フィールドにシャープ記号（#）を入力します。

3. 次のいずれかのフィルターオプションを選択して、コンポーネントのリストをフィルタリングします。

   | オプション | 関数 |
   |---------|----------|
   | [!UICONTROL **承認済み**] | 管理者が承認済みとしてマークしたコンポーネントのみを表示します。 |
   | [!UICONTROL **お気に入り**] | お気に入りのリストにあるコンポーネントのみを表示します。お気に入りのリストにコンポーネントを追加する方法については、[コンポーネントの管理](#manage-components)を参照してください。 |
   | [!UICONTROL **ディメンション**] | ディメンションであるコンポーネントのみを表示します。 |
   | [!UICONTROL **指標**] | 指標であるコンポーネントのみを表示します。 |
   | [!UICONTROL **フィルター**] | フィルターであるコンポーネントのみを表示します。 |
   | [!UICONTROL **日付範囲**] | 日付範囲であるコンポーネントのみを表示します。 |
   | [!UICONTROL **すべてを表示**] | すべてのコンポーネントの表示。 このオプションは、管理者のみが使用できます。 |
   | [!UICONTROL **未承認**] | 管理者が承認済みとしてまだマークしていないコンポーネントのみを表示します。レビューと承認が必要なコンポーネントを管理者が識別する際に役立ちます。このオプションは、管理者のみが使用できます。 |

4. （オプション）リストをさらに絞り込むには、[コンポーネントリストの並べ替え](#sort-the-component-list)で説明しているように、コンポーネントリストを並べ替えます。

### コンポーネントリストを並べ替え

{{release-limited-testing-section}}

1. （オプション）[コンポーネントリストのフィルタリング](#filter-the-component-list)で説明しているように、コンポーネントリストにフィルターを適用します。

2. 左側のパネルにある「**コンポーネント**」アイコン ![コンポーネントアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) を選択します。

3. 「**並べ替え**」アイコン ![コンポーネントを並べ替えアイコン](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) を選択し、次のフィルターオプションのいずれかを選択してコンポーネントのリストを並べ替えます。

   {{components-sort-options}}

## コンポーネントのアクセス権限

Analysis Workspace では、管理者はレポートでユーザーに公開するコンポーネントを[キュレート](/help/analysis-workspace/curate-share/curate.md)できます。
