---
description: 計算指標ビルダーは、ディメンション、指標、フィルターおよび関数をドラッグ＆ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成するためのキャンバスです。この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。
title: 指標の作成
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
source-git-commit: 7cdd81c9e38219d2d17decd5b9c3e987b814fc53
workflow-type: tm+mt
source-wordcount: '1214'
ht-degree: 48%

---

# 指標の作成

Customer Journey Analyticsは、ディメンション、指標、フィルターおよび関数をドラッグ&amp;ドロップし、コンテナ階層ロジック、ルールおよび演算子に基づいてカスタム指標を作成するためのキャンバスです。 この統合開発ツールでは、シンプルな計算指標または複雑で高度な計算指標を作成および保存できます。

## 計算指標の作成を開始

計算指標ビルダーを使用して、計算指標を作成できます。 この方法で作成した場合、計算指標はコンポーネントリストで使用できるので、組織全体のプロジェクトで使用できます。 または、[ 指標 ](/help/components/apply-create-metrics.md) の「単一プロジェクトの計算指標の作成 ](/help/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) の説明に従って、クイック計算指標を作成する [ こともできます。

計算指標ビルダーにアクセスして、コンポーネントリストで使用できる計算指標の作成を開始します。

1. 次のいずれかの方法で、計算指標ビルダーにアクセスします。

   * Analysis Workspaceで、プロジェクトを開き、**[!UICONTROL コンポーネント]**/**[!UICONTROL 指標を作成]** を選択します。
   * Analysis Workspaceでプロジェクトを開き、左パネルの **指標** セクションの横にある [!UICONTROL **プラス**] アイコンを選択します。
   * [!DNL Customer Journey Analytics] で、**[!UICONTROL コンポーネント]**/**[!UICONTROL 計算指標]** に移動し、計算指標ページの上部にある「**[!UICONTROL +追加]**」を選択します。

1. [ 計算指標ビルダーの領域 ](#areas-of-the-calculated-metrics-builder) に進みます。

## 計算指標ビルダーの領域

<!-- 

>[!CONTEXTUALHELP]
>id="cja_journeycanvas_viz_product_compatibility"
>title="Product compatibility"
>abstract="Indicates where in Customer Journey Analytics this calculated metric can be used, such as in Analysis Workspace, Report Builder, and so forth."  
>"Some calculated metrics cannot be used with experimentation. Calculated metrics that are not compatible with experimentation have the following value: "Everywhere in Customer Journey Analytics (excluding experimentation)" "
>"Various factors affect whether a calculated metric is compatible with experimentation. Learn more (https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation) ."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#use-in-experimentation" text="Use calculated metrics in experimentation"

-->

次の画像と付属の表で、計算指標ビルダーの主な領域と機能の一部を説明します。

![ この節で説明した主な領域と機能を示す新しい計算指標ウィンドウ。](assets/cm_builder_ui.png)

| フィールド | 説明 |
| --- | --- |
| タイトル | 指標には必ず名前を付ける必要があります。名前を付けていない指標は保存できません。 |
| 説明 | 指標の用途を示し、類似した指標と区別するための、ユーザーにわかりやすい説明を入力します。 <p>この説明はレポート内にも表示されます。説明には数式を記述しないことをお勧めします。その代わりに、この指標を使うべき状況と使ってはいけない状況について記述してください（数式は、指標の作成時に「概要」という見出しの下に生成されます。そのため、この説明に数式を追加する必要はありません）。 </p> |
| 形式 | 小数、時間、割合、通貨から選択できます。 |
| 小数点以下の桁数 | レポートに表示する小数点以下の桁数を示します。指定可能な小数点以下の桁数の最大値は 10 です。 |
| 上昇傾向を次の形式で表示 | この指標の両極性の設定は、Analytics が指標の上昇傾向を良い（緑）または悪い（赤）のどちらと見なすべきかを示します。そのため、レポートのグラフは、上昇傾向の場合に緑または赤で表示されます。 |
| 通貨 | このデータビューのベース通貨。 |
| タグ | タグ付けは、指標を管理するための便利な方法です。すべてのユーザーがタグを付けることができます。指標には 1 つ以上のタグを適用できます。ただし、タグを表示できるのは、自分が所有しているフィルターまたは自分と共有されているフィルターに限られます。 どのような種類のタグを作成する必要がありますか。次に、便利なタグのいくつかを示します。<ul><li>**チーム名** （ソーシャルマーケティング、モバイルマーケティングなど）。</li><li>**プロジェクト** （分析タグ）（エントリページ分析など）。</li><li>**カテゴリ** （Women&#39;s;Geography など）。</li><li>**ワークフロー** 承認待ち、キュレーション対象（特定の事業部門））</li></ul> |
| 概要 | <p>「概要」の数式は、指標の定義を変更すると更新されます。 この数式は、左側の指標レールで、指標の上にマウスポインターを置いて指標をクリックした場合にも表示されます <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> アイコン。 </p> |
| 定義 | ここに指標/計算指標、フィルター、関数などをドラッグして、計算指標を作成します。 <ul><li>計算指標をドラッグすると、指標の定義が自動的に展開されます。 </li> <li>コンテナを使用して定義をネストできます。ただし、フィルターコンテナとは異なり、これらのコンテナは数式のように機能し、操作の順序を決定します。 </li> </ul> |
| 演算子 | 除算（ <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" />）はデフォルトの演算子です。他にも、+、– および x の演算子があります。 |
| プレビュー | 可能性のあるエラーについて簡単に確認できます。プレビューには過去 90 日の情報が表示されます。これは、指標に適したコンポーネントを選択したかどうかを最初に判断するための手段です。予期しない結果が生じた場合は、指標の定義を見直す必要があります。 |
| 製品の互換性 | この計算指標をCustomer Journey Analytics内で使用できる場所を示します。 <p>使用可能な値は次のとおりです。</p><ul><li>[!UICONTROL **Customer Journey Analytics内のすべての場所**]：計算指標は、Analysis WorkspaceやReport Builderなど、すべてのCustomer Journey Analyticsで使用できます。</li><li>[!UICONTROL **Customer Journey Analyticsのすべての場所（実験を除く）**]：計算指標は、実験パネルを除くすべてのCustomer Journey Analyticsで使用できます。</li> <p>計算指標が実験で使用できるかどうかを決定する条件について詳しくは、[ 実験パネル ](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) の [ 実験パネルで計算指標を使用 ](/help/analysis-workspace/c-panels/experimentation.md) を参照してください。</p></ul> |
| 追加 | すべてのタイプの計算指標の場合、コンテナおよび静的な数値を定義に追加できます。詳細な計算指標では、フィルターと関数も追加できます。<ul><li>コンテナは数式のように機能し、演算の順序を指定します。そのため、コンテナ内の項目は、次の演算の前に処理されます。</li><li>フィルターをコンテナにドラッグすると、そのコンテナ内のすべてをフィルタリングできます。 （高度な計算指標のみ）</li><li>コンテナでは複数のフィルターを積み重ねることができます。</li></ul> |
| 歯車アイコン（指標タイプ、アトリビューション） | 指標の横にある歯車アイコンをクリックすると、指標タイプとアトリビューションモデルを指定できます。 <p>**メモ：** コンポーネントのアトリビューションをデフォルト以外のアトリビューションモデルに更新する場合は、次の点に注意してください。</p><ul><li>***単一ディメンション* でレポートでコンポーネントを使用する場合：** デフォルト以外のアトリビューションモデルが使用されている場合、コンポーネントのアトリビューションでは配分モデルが無視されます。</li><li>***複数ディメンション* を使用したレポートでコンポーネントを使用する場合：** デフォルト以外のアトリビューションモデルを使用すると、コンポーネントのアトリビューションで配分モデルが保持されます。</li><li>複数のディメンションは、[ クラウドへのデータの書き出し ](/help/analysis-workspace/export/export-cloud.md) 時にのみ使用できます。</li></ul> <p>割り当てについて詳しくは、[ 永続性コンポーネント設定 ](/help/data-views/component-settings/persistence.md) を参照してください。</p> |
| プラス（+） アイコン | 新しいフィルターなどの新しいコンポーネントを作成できます（フィルタービルダーが表示されます）。 |
| コンポーネントを検索 | この検索バーを使用すると、ディメンション、指標、フィルター（高度な計算指標のみ）および関数（高度な計算指標のみ）を検索できます。 |
| ディメンションリスト | 「ページ = ホームページ」などの簡単なフィルターを作成する場合、計算指標ビルダーから離れてフィルタービルダーで作成しなくても、計算指標ビルダーから直接ページをドラッグしてホームページを選択できます。 これにより、フィルタリングされた計算指標を作成するワークフローを効率化できます。 |
| 指標リスト | 指標は次の 3 つのカテゴリに分かれています。<ul><li>標準指標</li><li>計算指標</li><li>指標テンプレート - リストの一番下</li></ul>指標の上にカーソルを移動すると、右側に情報アイコンが表示されます。このアイコンをクリックすると、次の情報が表示されます。<ul><li>指標の計算を行うための数式。</li><li>指標の傾向のプレビュー</li><li>右上の編集（鉛筆）アイコンをクリックすると、計算指標ビルダーに移動し、この計算指標を編集できます。</li></ul> |
| フィルターのリスト | （詳細な計算指標のみ）管理者の場合、ログイン会社で作成されたすべてのフィルターがこのリストに表示されます。管理者でないユーザーの場合、自分が所有するフィルターと自分に共有されたフィルターがこのリストに表示されます。 |
| 関数リスト | （高度な計算指標のみ）関数は、基本（最も頻繁に使用される）と詳細の 2 つのリストに分かれています。 |
| データビューセレクター | 右上のこのセレクターを使用すると、別のデータビューに切り替えることができます。 |
