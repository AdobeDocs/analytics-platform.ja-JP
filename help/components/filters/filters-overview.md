---
title: セグメント化の概要
description: の使用目的とシンプルなセグメントの作成方法について説明します。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: d0268ce9ba22228c5c42d600c173f39cd1001638
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 5%

---


# セグメント化の概要

Customer Journey Analyticsでは、焦点を当てた強力なオーディエンスセグメントを作成、管理、共有し、レポートに適用できます。 セグメントを使用すると、特性やインタラクションに基づいて人物、セッションまたはイベントのサブセットを識別できます。 セグメントは、特定のニーズに合わせて作成し、検証、編集して他のチームメンバーと共有できる、成文化されたオーディエンスインサイトとして設計されています。

セグメントは、以下に基づいて作成できます。

- 属性（ブラウザータイプ、デバイス、訪問回数、国、性別）
- インタラクション（キャンペーン、キーワード検索、検索エンジン）、
- 出口およびエントリ（Facebook のユーザー、定義されたランディングページ、参照ドメイン、ジオフェンスイベント）
- カスタム変数（フォームフィールド、定義されたカテゴリ、顧客 ID）、
- とその他の条件。

セグメントの作成に使用できる様々なオプションについては、[ セグメントの作成 ](/help/components/filters/create-filters.md) を参照してください。 その後、[ セグメントビルダー ](filter-builder.md) でセグメントの定義を作成、変更および保存します。 または、[ クイックセグメントビルダー ](quick-filters.md) を使用してクイックセグメントを作成できます。 また、[ フォールアウト ](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) ビジュアライゼーションなどを使用して、Workspaceのビジュアライゼーションからセグメントを生成することもできます。

セグメントの管理には、[ セグメントマネージャー ](manage-filters.md) を使用します。

## セグメントの計画

特に、管理者は、セグメントを適切に計画することで、セグメントが使用される可能性が高くなります。 セグメントを計画する際は、次の点を考慮してください。

- **オーディエンス**：セグメントを使用するのは誰ですか？ オーディエンスが次のことを理解できるように、適切なセグメントの説明を入力します。
   - このセグメントはどのような分野で役立ちますか。

   - このセグメントはいつ使用する必要がありますか。

- **範囲**：後のデータを最もよく表す [ セグメントコンテナ ](#segment-containers) はどれですか？ できるだけ小さいコンテナを使用します。

- **コンポーネント**：セグメント定義に含めるコンポーネントと、条件で検証する値を決定します。

- **プロセス**：セグメントの承認プロセスを検討します。 Customer Journey Analyticsには承認ワークフローがありませんが、セグメントを承認するかどうかを判断するプロセスを引き続き編成できます。

- **モジュール性**：モジュール性を念頭に置いてセグメントを定義します。 セグメントのユーザーは、簡単に [ セグメントを積み重ねて ](filter-builder.md#stack-filters)、強力な新しいセグメントを作成できます。


## セグメントタイプ

次の 3 種類のセグメントを作成できます。

### クイックセグメント

クイックセグメントを使用すると、[ セグメントビルダー ](/help/components/filters/create-filters.md) でセグメントを作成しなくても、特定のWorkspace プロジェクト内でデータを簡単に調べることができます。 セグメントは、Workspace インターフェイス内で直接定義します。 詳しくは、[ クイックセグメント ](quick-filters.md) を参照してください。

### 標準セグメント

標準セグメントを使用すると、1 つ以上の条件に基づいてデータ（人物、セッション、イベント）を識別できます。 複数の条件がある場合は、And や Or などの論理演算子を使用してセグメントをさらに定義します。 コンテナを使用して条件をグループ化し、より複雑なセグメントを作成できます。 詳しくは、[ セグメントビルダー ](filter-builder.md) を参照してください。

### 順次セグメント

>[!IMPORTANT]
>
>クロスチャネルの順次セグメントを作成するには、**選択** パッケージが必要です。 使用している Customer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

順次セグメントを使用すると、ナビゲーション（サイト全体のページビュー、モバイルアプリのシーンとのインタラクション、セットトップボックスのメニューの使用）に基づいてデータ（人物、セッション、イベント）を識別できます。 順次セグメントは、人物が好きなものや避けているものを識別するのに役立ちます。 THEN 論理演算子を使用して、順次セグメントを定義します。 詳しくは、[ 順次セグメント ](seg-sequential-build.md) を参照してください。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## セグメントコンテナ {#containers}

セグメントは、ネストされたコンテナモデルを使用した、ユーザーレベル、セッションレベルおよびイベントレベルの階層に基づいています。 ネストされたコンテナを使用すると、コンテナ間およびコンテナ内で条件を定義できます。


<table style="table-layout: fixed; border: none;" width="100%">

<tr>
<td style="background-color: #E5E4E2;" colspan="3" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg"/> ユーザー</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200"></td>
<td style="background-color: #D3D3D3;" colspan="2" width="200" height="100"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Visit_18_N.svg"/> セッション</td>
</tr>

<tr>
<td style="background-color: #E5E4E2;" width="200" height="100"></td>
<td style="background-color: #D3D3D3;" width="200" height="100"></td>
<td style="background-color: #C0C0C0;" width="200" height="100" colspan="1"><img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg"/> イベント</td>
</tr>
</table>

>[!NOTE]
>
>Adobe Analytics ユーザーの場合：
> 
> - **ユーザー** コンテナは、Adobe Analyticsでは **訪問者** コンテナと呼ばれます。
> - Adobe Analyticsでは、**セッション** コンテナは **訪問** コンテナと呼ばれます。
> - Adobe Analyticsでは、**イベント** コンテナは **ヒット** コンテナと呼ばれます。
>

セグメントは、条件に基づいて個人、セッションまたはイベントをセグメント化するための条件を設定します。 例えば、人物をセグメント化する条件は、人物の特徴とナビゲーション特性に基づいています。 データをさらに分類するには、特定のセッション、ページビューイベント、画面のタップ、セットトップボックスのメニュー選択肢などでセグメント化できます。 また、CRM またはロイヤルティシステムから取り込んだ属性に基づいてセグメント化することもできます。 [ セグメントビルダー ](/help/components/filters/filter-builder.md) は、これらのサブセットを作成し、ネストされた階層的なユーザー、セッションまたはイベント コンテナに条件を適用するためのシンプルなインターフェイスを提供します。

[ セグメントビルダー ](/help/components/filters/filter-builder.md) で使用されるコンテナアーキテクチャでは、人物が最も外側のコンテナとして定義されています。 このコンテナには、ページビュー、モバイルアプリケーション画面、セットトップボックスのメニュー画面など、セッションやイベントをまたいでユーザーに固有の包括的なデータが含まれています。 ネストされたセッションコンテナを使用すると、セッションに基づいてユーザーのデータを分類するルールを設定できます。 ネストされたイベントコンテナを使用すると、個々のインタラクションに基づいて人物情報を分類できます。 各コンテナを使用すると、個人の履歴、セッションごとに分類されたインタラクション、または個々のイベントの分類についてレポートできます。

### ユーザーコンテナ

人物コンテナには、コンテナで指定された条件に該当する人物のすべてのセッションとイベントが含まれます。 `Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、人物コンテナは次のように解決されます。

- `Checkout` という名前でページにアクセスしたすべてのユーザー。
- これらのユーザーのすべてのセッション。
- これらのユーザーに関するすべてのイベントデータ。

最も広く定義されたコンテナとして、個人コンテナレベルで生成されたレポートは、セグメントに適格なすべての個人のイベントとセッションを返します。 個人コンテナは、定義された日付範囲に基づいて最も変更されやすい要素です。
人物コンテナには、人物の全体的な履歴に基づく値を含めることができます。

- 初回購入までの日数。
- オリジナルの入口ページまたはモバイルアプリのホーム画面。
- オリジナルの参照ドメイン。

### セッションコンテナ

セッションコンテナでは、特定のセッションのページインタラクション、モバイルアプリインタラクション、キャンペーンまたはコンバージョンを識別できます。 セッションコンテナは、ルールに合致するとセッション全体の動作をキャプチャするので、最も一般的に使用されるコンテナです。 セッションコンテナでは、セグメントの作成と適用に含める、または除外するセッションを定義することもできます。  `Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、セッションコンテナは次のように解決されます。

- `Checkout` という名前のページが訪問されるすべてのセッション。
- これらのセッションのすべてのイベントデータ。

セッションコンテナは、次の質問に答えるのに役立ちます。

- Web とコールセンターの両方のデータソースに関係するセッションの数
- 購入へのコンバージョンにつながったページが何ページありましたか？

セッションコンテナには、セッションごとのイベントに基づく値が含まれます。

- セッションタイプ。
- 入口ページ。
- 再来訪頻度。
- パーティシペーションの指標。
- 線形に割り当てられた指標。

Customer Journey Analyticsのデータビューを使用すると、セッションの持続時間と、新しいセッションを作成するタイミングを決定できます。 例えば、ユーザーがモバイルアプリを起動するたびに基づいて、新しいモバイルアプリセッションを定義できます。 詳しくは、[ セッション設定 ](/help/data-views/session-settings.md) を参照してください。

### イベントコンテナ

イベントコンテナは、セグメントに含めたりセグメントから除外したりするページ、モバイルアプリケーションまたはその他のタイプのイベントを定義します。 これは、利用可能なコンテナの中で最も狭いものです。 条件が true の場合に、モバイルアプリで特定のクリック数、ページビュー数、ボタンのタップ数を識別できます。 イベントコンテナを使用すると、単一のトラッキングコードを表示したり、モバイルアプリの特定の領域内の動作を分離したりできます。 また、注文時のマーケティングチャネルなど、アクションが発生した場合に特定の値を特定することもできます。 `Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、イベントコンテナは次のように解決されます。

- ページ名が `Checkout` と等しいすべてのページビューイベント。

イベントコンテナには、値ベースの単一ページ分類が含まれています。

- 製品
- リスト prop
- リストディメンション
- マーチャンダイジングディメンション （イベントのコンテキスト内）



### B2B コンテナ

[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey AnalyticsB2B edition"}

[Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) にアクセスできる場合は、セグメントで使用するその他のコンテナを使用できます。 これらの追加コンテナの使用について詳しくは、[B2B の概念と機能 ](/help/getting-started/cja-b2b-concepts-features.md) を参照してください。


### 論理グループコンテナ

論理グループを使用すると、条件を 1 つの順次セグメントチェックポイントにグループ化できます。 シーケンスの一部として、[!UICONTROL &#x200B; 論理グループ &#x200B;] として識別されるコンテナ内で定義されるロジックは、先行する順次チェックポイントの後、後続の順次チェックポイントの前に評価されます。 詳しくは、[ 論理グループ ](seg-sequential-build.md#logic-group) を参照してください。

### コンテナをネスト

他のコンテナ内にコンテナを作成する場合、実際にはセグメント内にセグメントを作成していることになります。 ネストされたコンテナには、次のロジックが適用されます。

1. どのようなデータが含まれているかを、最も外側にあるコンテナによって調べます。この外部ルールに一致しないデータは、レポート内で破棄されます。
2. ネストされたセグメント定義を残りのデータに適用します。 ネストされたセグメント定義は、最初の定義が破棄されたデータには適用されません。
3. ネストされたコンテナセグメント定義がすべて計算されるまで繰り返します。 残りのデータは結果に含まれ、レポートに使用されます。

>[!NOTE]
>
>セグメント内にセグメントをネストする場合（例えば、コンポーネント パネルからセグメント定義にセグメントをドラッグする場合）、コンテナは、ドラッグしたセグメント定義のコピー（参照ではなく）を使用して作成されます。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box segment template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Segment Name | Description |
| --- | --- |
| All Data | All Data is a required segment that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[セグメントの作成](create-filters.md)
>[セグメントビルダー ](filter-builder.md)
>[クイックセグメント ](quick-filters.md)
>[順次セグメント ](seg-sequential-build.md)
>[セグメント ](manage-filters.md) 管理
>
