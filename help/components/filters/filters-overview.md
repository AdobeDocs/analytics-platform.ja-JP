---
title: フィルターの概要
description: フィルターの用途と、単純なフィルターの作成方法を理解します。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters
role: User
source-git-commit: 392ba2b9cfe090901c3dac12459f9bd8d51fdca7
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 8%

---


# フィルターの概要

Customer Journey Analytics を使用すると、強力で重要なオーディエンスフィルターを作成、管理、共有し、レポートに適用できます。フィルターを使用すると、特性やインタラクションに基づいて人物、セッションまたはイベントのサブセットを識別できます。 フィルターは、特定のニーズに合わせて作成し、他のチームメンバーと検証、編集、および共有できる、体系化されたオーディエンスインサイトとして作られています。

フィルターは以下に基づくことができます。

- 属性（ブラウザータイプ、デバイス、訪問回数、国、性別）
- インタラクション（キャンペーン、キーワード検索、検索エンジン）、
- 出口およびエントリ（Facebook のユーザー、定義されたランディングページ、参照ドメイン、ジオフェンスイベント）
- カスタム変数（フォームフィールド、定義されたカテゴリ、顧客 ID）、
- とその他の条件。

フィルターの作成に使用できる様々なオプションについては、[ フィルターの作成 ](/help/components/filters/create-filters.md) を参照してください。 その後、[ フィルタービルダー ](filter-builder.md) でフィルターの定義を作成、変更および保存します。 または、[ クイックフィルタービルダー ](quick-filters.md) を使用してクイックフィルターを作成できます。 また、[ フォールアウト ](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu) ビジュアライゼーションなどを使用して、Workspaceのビジュアライゼーションからフィルターを生成することもできます。

フィルターを管理するには、[ フィルターマネージャー ](manage-filters.md) を使用します。

## プランフィルター

特に、管理者として、フィルターを適切に計画すると、フィルターが使用される可能性が高くなります。 フィルターを計画する際は、次の点を考慮してください。

- **オーディエンス**：フィルターを使用するユーザー オーディエンスが次のことを理解できるよう、適切なフィルターの説明を入力します。
   - このフィルターはどのような分野で役立ちますか。

   - このフィルターはいつ使用する必要がありますか。

- **範囲**：後のデータを最もよく表す [ フィルターコンテナ ](#filter-containers) はどれですか？ できるだけ小さいコンテナを使用します。

- **コンポーネント**：フィルター定義に含めるコンポーネントと、条件で検証する値を決定します。

- **プロセス**：フィルターの承認プロセスを検討します。 Customer Journey Analyticsには承認ワークフローはありませんが、フィルターを承認するかどうかを判断するプロセスを整理することはできます。

- **モジュール性**：モジュール性を考慮してフィルターを定義します。 したがって、フィルターのユーザーは、簡単に [ フィルターを積み重ねて ](filter-builder.md#stack-filters)、強力な新しいフィルターを作成できます。


## フィルターのタイプ

次の 3 種類のフィルターを作成できます。

### クイックフィルター

クイックフィルターを使用すると、[ フィルタービルダー ](/help/components/filters/create-filters.md) でフィルターを作成しなくても、特定のWorkspace プロジェクト内でデータを簡単に調べることができます。 フィルターはWorkspace インターフェイス内で直接定義できます。 詳しくは、[ クイックフィルター ](quick-filters.md) を参照してください。

### 標準フィルター

通常のフィルターを使用すると、1 つ以上の条件に基づいてデータ（人物、セッション、イベント）を識別できます。 複数の条件がある場合は、And や Or などの論理演算子を使用してフィルターをさらに定義します。 コンテナを使用して条件をグループ化し、より複雑なフィルターを作成できます。 詳しくは、[ フィルタービルダー ](filter-builder.md) を参照してください。

### 順次フィルター

>[!IMPORTANT]
>
>クロスチャネルの順次フィルターを作成するには、**選択** パッケージが必要です。 使用しているCustomer Journey Analytics パッケージが不明な場合は、管理者にお問い合わせください。

順次フィルターを使用すると、ナビゲーション（サイト全体のページビュー、モバイルアプリのシーンとのインタラクション、セットトップボックスのメニューの使用）に基づいてデータ（人物、セッション、イベント）を識別できます。 順次フィルターは、ユーザーが好きなものや避けているものを識別するのに役立ちます。 THEN 論理演算子を使用して、順次フィルターを定義します。 詳しくは、[ 順次フィルター ](seg-sequential-build.md) を参照してください。


<!--
An example of a complex sequential filter if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## フィルターコンテナ {#containers}

フィルターは、ネストされたコンテナモデルを使用した、ユーザーレベル、セッションレベル、イベントレベルの階層に基づいています。 ネストされたコンテナを使用すると、コンテナ間およびコンテナ内で条件を定義できます。


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

フィルターは、条件に基づいてユーザー、セッションまたはイベントをフィルタリングする条件を設定します。 例えば、人物の特徴やナビゲーション特性に基づいて人物をフィルタリングするための条件などです。 データをさらに分類するには、特定のセッション、ページビューイベント、画面のタップ、セットトップボックスのメニューの選択肢などに基づいてフィルタリングできます。 ただし、CRM またはロイヤルティシステムから取り込んだ属性に基づいてフィルタリングすることもできます。 [ フィルタービルダー ](/help/components/filters/filter-builder.md) は、これらのサブセットを作成し、ネストされた階層的な Person、Session または Event コンテナに条件を適用するためのシンプルなインターフェイスを提供します。

[ フィルタービルダー ](/help/components/filters/filter-builder.md) で使用されるコンテナアーキテクチャでは、人物を最も外側のコンテナとして定義します。 コンテナには、ページビュー、モバイルアプリケーション画面、セットトップボックスのメニュー画面など、セッションやイベントをまたいでユーザーに固有の包括的なデータが含まれています。 ネストされたセッションコンテナを使用すると、セッションに基づいてユーザーのデータを分類するルールを設定できます。 ネストされたイベントコンテナを使用すると、個々のインタラクションに基づいて人物情報を分類できます。 各コンテナを使用すると、個人の履歴、セッションごとに分類されたインタラクション、または個々のイベントの分類についてレポートできます。

### ユーザーコンテナ

人物コンテナには、コンテナで指定された条件に該当する人物のすべてのセッションとイベントが含まれます。 `Page Name equals Checkout` のような単純な条件でフィルターを定義すると、ユーザーコンテナは次のように解決されます。

- `Checkout` という名前でページにアクセスしたすべてのユーザー。
- これらのユーザーのすべてのセッション。
- これらのユーザーに関するすべてのイベントデータ。

最も広く定義されたコンテナとして、人物コンテナレベルで生成されたレポートは、フィルターに該当するすべての人物のイベントとセッションを返します。 個人コンテナは、定義された日付範囲に基づいて最も変更されやすい要素です。
人物コンテナには、人物の全体的な履歴に基づく値を含めることができます。

- 初回購入までの日数。
- オリジナルの入口ページまたはモバイルアプリのホーム画面。
- オリジナルの参照ドメイン。

### セッションコンテナ

セッションコンテナでは、特定のセッションのページインタラクション、モバイルアプリインタラクション、キャンペーンまたはコンバージョンを識別できます。 セッションコンテナは、ルールに合致するとセッション全体の動作をキャプチャするので、最も一般的に使用されるコンテナです。 セッション コンテナでは、フィルターの作成と適用に含める、または除外するセッションを定義することもできます。  `Page Name equals Checkout` のような単純な条件でフィルターを定義すると、セッションコンテナは次のように解決されます。

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

イベントコンテナは、フィルターに含めたりフィルターから除外したりするページ、モバイルアプリケーションまたはその他のタイプのイベントを定義します。 これは、条件が true のモバイルアプリで特定のクリック数、ページビュー数、ボタンのタップ数を識別するために使用できる最も狭いコンテナです。 イベントコンテナを使用すると、単一のトラッキングコードを表示したり、モバイルアプリの特定の領域内の動作を分離したりできます。 また、注文時のマーケティングチャネルなど、アクションが発生した場合に特定の値を特定することもできます。 `Page Name equals Checkout` のような単純な条件を持つフィルターを定義すると、イベント コンテナは次のように解決されます。

- ページ名が `Checkout` と等しいすべてのページビューイベント。

イベントコンテナには、値ベースの単一ページ分類が含まれています。

- 製品
- リスト prop
- リストディメンション
- マーチャンダイジングディメンション （イベントのコンテキスト内）


### 論理グループコンテナ

論理グループを使用すると、条件を単一の順次フィルターチェックポイントにグループ化できます。 シーケンスの一部として、[!UICONTROL  論理グループ ] として識別されるコンテナ内で定義されるロジックは、先行する順次チェックポイントの後、後続の順次チェックポイントの前に評価されます。 詳しくは、[ 論理グループ ](seg-sequential-build.md#logic-group) を参照してください。

### コンテナをネスト

他のコンテナ内にコンテナを作成する場合、実際にはフィルター内にフィルターを作成していることになります。 ネストされたコンテナには、次のロジックが適用されます。

1. どのようなデータが含まれているかを、最も外側にあるコンテナによって調べます。この外部ルールに一致しないデータは、レポート内で破棄されます。
2. ネストされたフィルター定義を残りのデータに適用します。 ネストされたフィルター定義は、最初の定義が破棄されたデータには適用されません。
3. ネストされたすべてのコンテナフィルター定義が計算されるまで繰り返します。 残りのデータは結果に含まれ、レポートに使用されます。

>[!NOTE]
>
>フィルター内にフィルターをネストする場合（例えば、コンポーネント パネルからフィルター定義にフィルターをドラッグする場合）、コンテナは、ドラッグしたフィルター定義のコピー（参照ではなく）と共に作成されます。

<!--
You can use nesting between containers and between conditions within a container. Here is what you can nest in each container:


| Container | What container you can nest inside |
| Event | Only event conditions |
| Session | Session


## Out-of-the-box filter template {#template}

Traditional Analytics comes with numerous out-of-the-box templates and calculated metrics. Many of them do not apply in Customer Journey Analytics, or have to be renamed or recreated. Others depend on a solution for context-aware variables in Customer Journey Analytics.

| Filter Name | Description |
| --- | --- |
| All Data | All Data is a required filter that gets dynamically added to reporting when a metric is added to the row of a Freeform table. |
-->

>[!MORELIKETHIS]
>
>[ フィルターの作成 ](create-filters.md)
>[フィルタービルダー ](filter-builder.md)
>[クイックフィルター ](quick-filters.md)
>[順次フィルター ](seg-sequential-build.md)
>[フィルター ](manage-filters.md) 管理
>
