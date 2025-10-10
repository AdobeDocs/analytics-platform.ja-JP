---
title: セグメント化の概要
description: セグメントの用途と、単純なセグメントの作成方法を理解します。
exl-id: 21183e98-6593-4b22-99c7-4a03231acfe9
feature: Filters, Segments
role: User
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '1474'
ht-degree: 100%

---


# セグメント化の概要

Customer Journey Analytics を使用すると、的を絞った強力なオーディエンスセグメントを作成、管理、共有し、レポートに適用できます。セグメントを使用すると、特性やインタラクションに基づいて、ユーザー、セッションまたはイベントのサブセットを識別できます。セグメントは特定のニーズに合わせて作成し、他のチームメンバーと検証、編集、および共有できる、体系化されたオーディエンスインサイトとして設計されています。

セグメントは、以下に基づいて作成できます。

- 属性（ブラウザータイプ、デバイス、訪問回数、国、性別）
- インタラクション（キャンペーン、キーワード検索、検索エンジン）
- 離脱とエントリ（Facebook のユーザー、定義済みのランディングページ、参照ドメイン、ジオフェンスイベント）
- カスタム変数（フォームフィールド、定義済みのカテゴリ、顧客 ID）
- その他の条件。

セグメントの作成に使用できる様々なオプションについては、[セグメントの作成](/help/components/segments/seg-create.md)を参照してください。次に、[セグメントビルダー](seg-builder.md)でセグメントの定義を作成、変更および保存します。または、[クイックセグメントビルダー](seg-quick.md)を使用してクイックセグメントを作成できます。また、[フォールアウト](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md#context-menu)ビジュアライゼーションなどを使用して、Workspace 内のビジュアライゼーションからセグメントを生成することもできます。

セグメントを管理するには、[セグメントマネージャー](seg-manage.md)を使用します。

## セグメントの計画

特に、管理者としては、セグメントを適切に計画することで、セグメントが使用される可能性が高くなります。セグメントを計画する際は、次の点を考慮してください。

- **オーディエンス**：セグメントを使用するのは誰か？オーディエンスが次のことを理解できるように、セグメントの適切な説明を必ず入力します。
   - このセグメントはどのような分野で役立ちますか。

   - このセグメントはいつ使用する必要がありますか。

- **範囲**：追跡しているデータを最もよく表している[セグメントコンテナ](#segment-containers)はどれか？できるだけ小さいコンテナを使用します。

- **コンポーネント**：セグメント定義に含めるコンポーネントと条件の検証基準となる値を決定します。

- **プロセス**：セグメントの承認プロセスを検討します。Customer Journey Analytics には承認ワークフローがありませんが、それでもセグメントを承認するかどうかを判断するプロセスを編成することはできます。

- **モジュール性**：モジュール性を念頭に置いてセグメントを定義します。セグメントのユーザーは、簡単に[セグメントを積み重ね](seg-builder.md#stack-filters)て、強力な新しいセグメントを作成できる必要があります。


## セグメントタイプ

次の 3 つのタイプのセグメントを作成できます。

### クイックセグメント

クイックセグメントを使用すると、[セグメントビルダー](/help/components/segments/seg-create.md)でセグメントを作成しなくても、特定の Workspace プロジェクト内でデータを簡単に探索できます。セグメントは、Workspace インターフェイス内で直接定義します。詳しくは、[クイックセグメント](seg-quick.md)を参照してください。

### 標準セグメント

標準セグメントを使用すると、1 つ以上の条件に基づいてデータ（人物、セッション、イベント）を識別できます。複数の条件がある場合は、And や Or などの論理演算子を使用してセグメントをさらに定義します。コンテナを使用して条件をグループ化し、より複雑なセグメントを作成することができます。詳しくは、[セグメントビルダー](seg-builder.md)を参照してください。

### 順次セグメント

>[!IMPORTANT]
>
>クロスチャネルの順次セグメントを作成するには、**Select** パッケージが必要です。どの Customer Journey Analytics パッケージを使用しているかが不明な場合は、管理者にお問い合わせください。

順次セグメントを使用すると、ナビゲーション（サイト全体のページビュー、モバイルアプリのシーンとのインタラクション、セットトップボックスのメニューの使用）に基づいてデータ（人物、セッション、イベント）を識別できます。順次セグメントは、例えば、ユーザーが好むものとそうでないものを識別するのに役立ちます。順次セグメントを定義するには、Then 論理演算子を使用します。詳しくは、[順次セグメント](seg-sequential-build.md)を参照してください。


<!--
An example of a complex sequential segment if you want to find the persons that 

| Session One | Session Two | Session Three |
| --- | --- | --- |
| The person went to the main landing page A, excluded the campaign page B, and then viewed the Product page C.| The person again went to the main landing page A, excluded the campaign page B, and went again to the Product page C, and then to a new page D. | The person entered and followed that same path as in the first and second visits, then excluded page F to go directly to a targeted product on page G. |
-->

## セグメントコンテナ {#containers}

セグメントは、ネストされたコンテナモデルを使用して、ユーザー、セッション、イベントレベルの階層に基づいています。ネストされたコンテナを使用すると、コンテナ間およびコンテナ内で条件を定義できます。


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
> - Adobe Analytics では、**ユーザー**&#x200B;コンテナは&#x200B;**訪問者**&#x200B;コンテナと呼ばれます。
> - Adobe Analytics では、**セッション**&#x200B;コンテナは&#x200B;**訪問**&#x200B;コンテナと呼ばれます。
> - Adobe Analytics では、**イベント**&#x200B;コンテナは&#x200B;**ヒット**&#x200B;コンテナと呼ばれます。
>

セグメントは、条件に基づいてユーザー、セッションまたはイベントをセグメント化するための条件を設定します。例えば、ユーザーをセグメント化する条件は、ユーザーの特徴とナビゲーション特性に基づいています。データをさらに分類するには、特定のセッション、ページビューイベント、画面のタップ、セットトップボックスのメニュー選択肢などに基づいてセグメント化できます。また、CRM またはロイヤルティシステムから取り込んだ属性に基づいてセグメント化することもできます。[セグメントビルダー](/help/components/segments/seg-builder.md)は、これらのサブセットを作成するためのシンプルなインターフェイスで、ネストされた階層的なユーザー、セッション、イベントコンテナで条件を適用します。

[セグメントビルダー](/help/components/segments/seg-builder.md)で使用されるコンテナアーキテクチャでは、ユーザーが最も外側のコンテナとして定義されています。このコンテナには、ページビュー、モバイルアプリケーション画面、セットトップボックスのメニュー画面など、セッションやイベントをまたいでユーザーに固有の包括的なデータが含まれています。ネストされたセッションコンテナを使用すると、セッションに基づいてユーザーのデータを分類するルールを設定できます。ネストされたイベントコンテナを使用すると、個々のインタラクションに基づいてユーザー情報を分類できます。各コンテナでは、ユーザーの履歴全体で、セッションごとに分類されたインタラクションのレポートを作成したり、個々のイベントを分類したりできます。

### ユーザーコンテナ

ユーザーコンテナには、コンテナで指定された条件に該当するユーザーのすべてのセッションとすべてのイベントが含まれます。`Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、ユーザーコンテナは次のように解決されます。

- `Checkout` という名前でページにアクセスしたすべてのユーザー。
- これらのユーザーのすべてのセッション。
- これらのユーザーに関するすべてのイベントデータ。

最も広く定義されたコンテナとして、ユーザーコンテナレベルで生成されたレポートは、セグメントに適格なすべてのユーザーのイベントとセッションを返します。ユーザーコンテナは、定義された日付範囲に基づく変化の影響を最も受けやすくなります。ユーザーコンテナには、ユーザーの履歴全体に基づく値が含まれます。

- 初回購入までの日数。
- オリジナルの入口ページまたはモバイルアプリのホーム画面。
- オリジナルの参照ドメイン。

### セッションコンテナ

セッションコンテナでは、特定のセッションでのページインタラクション、モバイルアプリインタラクション、キャンペーンまたはコンバージョンを識別できます。セッションコンテナは、ルールに合致するとセッション全体の行動を取り込むので、最も一般的に使用されるコンテナです。セッションコンテナでは、セグメントの作成と適用に含めるセッションと除外するセッションを定義できます。`Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、セッションコンテナは次のように解決されます。

- `Checkout` という名前でページが訪問されるすべてのセッション。
- これらのセッションのすべてのイベントデータ。

セッションコンテナは、次の質問に答えるのに役立ちます。

- Web とコールセンターの両方のデータソースに関与したセッションはいくつありますか？
- 購入へのコンバージョンにつながったページが何ページありましたか？

セッションコンテナには、1 回のセッションあたりのイベントに基づく値が含まれます。

- セッションタイプ。
- 入口ページ。
- 再来訪頻度。
- パーティシペーション指標。
- 線形的に割り当てられた指標。

Customer Journey Analytics のデータビューを使用すると、セッションの持続時間と新しいセッションを作成するタイミングを決定できます。例えば、ユーザーがモバイルアプリを起動するたびに、新しいモバイルアプリセッションを定義できます。詳しくは、[セッション設定](/help/data-views/session-settings.md)を参照してください。

### イベントコンテナ

イベントコンテナは、セグメントに含めるまたはセグメントから除外するページ、モバイルアプリケーション、その他のイベントタイプを定義します。これは、利用可能なコンテナの中で最も範囲の狭いものです。モバイルアプリで、条件に当てはまる特定のクリック数、ページビュー数、ボタンのタップ数を特定できます。イベントコンテナを使用すると、単一のトラッキングコードを表示したり、モバイルアプリの特定の領域内の動作を分離したりできます。また、アクションが発生したときの特定の値（注文が発生したときのマーケティングチャネルなど）を把握することもできます。`Page Name equals Checkout` のような単純な条件を持つセグメントを定義すると、イベントコンテナは次のように解決されます。

- ページ名が `Checkout` に等しいすべてのページビューイベント。

イベントコンテナには、以下に対応する値ベースの単一ページ分類が含まれています。

- 製品
- リスト prop
- リストディメンション
- マーチャンダイジングディメンション（イベントのコンテキスト内）



### B2B コンテナ

[!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}

[Customer Journey Analytics B2B Edition](/help/getting-started/cja-b2b-edition.md) にアクセスできる場合は、追加のコンテナをセグメントで使用できます。これらの追加コンテナの使用について詳しくは、[B2B の概念と機能](/help/getting-started/cja-b2b-concepts-features.md)を参照してください。


### 論理グループコンテナ

論理グループを使用すると、条件を単一の順次セグメントチェックポイントにグループ化できます。シーケンスの一部として、[!UICONTROL 論理グループ]として識別されたコンテナ内で定義されたロジックは、先行する順次チェックポイントの後と後続の順次チェックポイントの前で評価されます。詳しくは、[論理グループ](seg-sequential-build.md#logic-group)を参照してください。

### コンテナのネスト

コンテナを他のコンテナ内に作成する場合、実際には、セグメントを他のセグメント内に作成しています。ネストされたコンテナには、次のロジックが適用されます。

1. どのようなデータが含まれているかを、最も外側にあるコンテナによって調べます。この外部ルールと一致しないデータは、レポートですべて削除されます。
2. ネストされたセグメント定義を残りのデータに適用します。ネストされたセグメント定義は、最初の定義で破棄されたデータには適用されません。
3. ネストされたコンテナセグメント定義がすべて計算されるまで繰り返します。残りのデータは結果に含まれ、レポートに使用されます。

>[!NOTE]
>
>セグメント内にセグメントをネストする場合（例えば、コンポーネントパネルからセグメント定義にセグメントをドラッグする場合）、ドラッグしたセグメント定義の（参照ではなく）コピーを使用してコンテナが作成されます。

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
>[セグメントの作成](seg-create.md)
>>[セグメントビルダー](seg-builder.md)
>>[クイックセグメント](seg-quick.md)
>>[順次セグメント](seg-sequential-build.md)
>>[セグメントの管理](seg-manage.md)
